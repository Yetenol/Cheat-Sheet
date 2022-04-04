# [⌂](../README.md) › [Powershell](../README.md#powershell) › Input Handling

# User input

### Read keyboard input
```powershell
$User = Get-Host "Username"
```

# .Net formatted file

> _Use xml files to keep PowerShells Object formatting._

- import an object from an .xml file

  ```powershell
  $object = Import-Clixml -Path ".\example.xml"
  ```

- count its number of items

  ```powershell
  $object = Import-Clixml -Path ".\example.xml"
  $object.Count
  ```

  ```powershell
  ($object = Import-Clixml -Path ".\example.xml").Count
  ```

- find all items whose name starts with _user_

  > Quick [**Regular Expression**](../languages/regex.md) Reference for `-match` and `[RegEx]::`  
  > `(?ENABLE-DISABLE)` [Interpretation Options](../languages/regex.md#engine-interpretation-options):  `i` IgnoreCase;  `n` ExplicitCapture;  `x` IgnorePatternWhitespace;  `m` Multiline;  `s` Singleline;  
  > `^` Start of line;  `$` End of line;  `.*` ≥0 character(s);  `.+` ≥0 character(s);  `\w*` Any word;  `\S*` Any non-whitespace;
  > `\s*` Any whitespace;  `(.*)` Unnamed group;     `(?<user>.*)` Named group called user

  ```powershell
  $pattern = "(?i)^user"
  foreach ($_ in $object) {
    if ($_.Name -match $pattern) {
      Write-Output $_
    }
  }
  ```


# Plain text file

- import all lines from a plain text file

  ```powershell
  $lines = Get-Content -Path ".\example.txt"
  ```

- only import (a) specific line(s)

  ```powershell
  $line26      = (Get-Content -Path ".\example.txt")[25]
  $line23til26 = (Get-Content -Path ".\example.txt")[22..25]
  ```

  > `-TotalCount` speeds up the commands by only loading the first 26 lines.

  ```powershell
  $line26      = (Get-Content -Path ".\example.txt" -TotalCount 26)[25]
  $line23til26 = (Get-Content -Path ".\example.txt" -TotalCount 26)[22..25]
  ```

- count number of lines

  ```powershell
  $lines = Get-Content -Path ".\example.txt"
  $lines.Count
  ```

  ```powershell
  ($lines = Get-Content -Path ".\example.txt").Count
  ```

## Find Occurrences Of A Pattern

> Quick [**Regular Expression**](../languages/regex.md) Reference for `-match` and `[RegEx]::`  
> `(?ENABLE-DISABLE)` [Interpretation Options](../languages/regex.md#engine-interpretation-options):  `i` IgnoreCase;  `n` ExplicitCapture;  `x` IgnorePatternWhitespace;  `m` Multiline;  `s` Singleline;  
> `^` Start of line;  `$` End of line;  `.*` ≥0 character(s);  `.+` ≥0 character(s);  `\w*` Any word;  `\S*` Any non-whitespace;
> `\s*` Any whitespace;  `(.*)` Unnamed group;     `(?<user>.*)` Named group called user

Example: search for lines starting with _user_
```powershell
$pattern = "(?i)^user"
```

- find the lines of **all** occurrences of the pattern

  ```powershell
  $captures = foreach ($_ in $lines) {
    if ($_ -match $pattern) {
      Write-Output $_
    }
  }
  ```

  > `-ReadCount` speeds up the search when using large files as it sends the lines in 1k batches through the pipeline. Beware of slightly different formatting.

  ```powershell
  $captures = Get-Content -Path ".\example.txt" -ReadCount 1000 | foreach {
    $_ -match $pattern
  }
  ```


- **count** occurrences of the pattern

  ```powershell
  $captures.Count
  ```

- find the line of the **first** occurrence of the pattern

  ```powershell
  $capture = $captures[0]
  ```

  ```powershell
  $capture = foreach ($_ in $lines) {
    if ($_ -match $pattern) {
      Write-Output $_
      break # stop further searching
    }
  }
  ```

  > `-ReadCount` is difficult to use here.

## Extract Data Using A Pattern

> Quick [**Regular Expression**](../languages/regex.md) Reference for `-match` and `[RegEx]::`  
> `(?ENABLE-DISABLE)` [Interpretation Options](../languages/regex.md#engine-interpretation-options):  `i` IgnoreCase;  `n` ExplicitCapture;  `x` IgnorePatternWhitespace;  `m` Multiline;  `s` Singleline;  
> `^` Start of line;  `$` End of line;  `.*` ≥0 character(s);  `.+` ≥0 character(s);  `\w*` Any word;  `\S*` Any non-whitespace;
> `\s*` Any whitespace;  `(.*)` Unnamed group;     `(?<user>.*)` Named group called user

- Extract a **single** datum from the **first** occurrence of the pattern.
  
  Get the username from lines that start with the listing of a user name.

  ```powershell
  $pattern = '(?i)^\s*username:\s*(\w*)'
  # line example   ···Username:···anna····[...] 

  $lines = Get-Content -Path ".\example.txt"

  $capture = foreach ($_ in $lines) {
    $regex = [RegEx]::Match($_, $pattern)
    if ($regex.Success) {
      Write-Output $regex.Groups[1].value # matched groups start at index 1
      break # stop further searching
    }
  }

  if ($capture) {Write-Output $capture} else {Write-Error "Nothing found!"}
  ```

- Extract **multiple** data from **each** occurrence of the pattern.
  
  Get the credentials from lines that list a username and password.

  > Use option `n` (ExplicitCapture) to ignore all unnamed groups.

  ```powershell
  $pattern = '(?in)^\s*username:\s*(?<user>\S*)\s*password:\s*(?<pwd>\S*)\s*$'
  # line example    ···Username:···annaSchmidt···Password:···turtles_48··· 

  $lines = Get-Content -Path ".\example.txt"

  $captures = foreach ($_ in $lines) {
    $regex = [RegEx]::Match($_, $pattern)
    if ($regex.Success) {
      Write-Output ([PSCustomObject]@{ 
        Username = $regex.Groups["user"].value
        Password = $regex.Groups["pwd"].value
      })
    }
  }

  if ($captures) {Write-Output $captures} else {Write-Error "Nothing found!"}
  ```

- Extract from occurrences of a **multiline** pattern.

  Get the title key pairs of listings in consecutive lines.

  > Use `[RegEx]::Matches` for **all** and `[RegEx]::Match` for the **first** occurrence of the pattern.

  > Import file using `-Raw` to save it as a **single string** instead of an array of lines.  
  > Use option `m` (multiline) to let `^` and `$` match the beginning and end of **each line** instead of the entire input string. 

  ```powershell
  $pattern = '(?inm)^name\s*:\s*(?<title>.*)\nvalue\s*:\s*(?<key>.*)$'
  # lines example    Name···:···ProgramFiles 
  #                  Value··:···C:\Program Files (x86)

  $text = Get-Content -Path ".\example.txt" -Raw

  $regex = [RegEx]::Matches($text, $pattern)
  $captures = foreach ($_ in $regex) {
    Write-Output ([PSCustomObject]@{
      Title = $_.Groups["title"].value
      Key   = $_.Groups["key"].value
    })
  }

  if ($captures) {Write-Output $captures} else {Write-Error "Nothing found!"}
  ```

# Sensitive input

- <b> Don't save passwords as plain text </b>
- Instead save them as a secure string and encrypt them locally.

## Enter sensitive input in console

```powershell
$Secure = Read-Host "Password" -AsSecureString
```

## Decrypt locally

- Only the <b>SAME INSTANCE</b> can decrypt. 

> _The last line prevents memory leaks._

```powershell
$bstr = [System.Runtime.InteropServices.Marshal]::SecureStringToBSTR($Secure)
$Plaintext [System.Runtime.InteropServices.Marshal]::PtrToStringAuto($bstr)
[System.Runtime.InteropServices.Marshal]::ZeroFreeBSTR($bstr)
```