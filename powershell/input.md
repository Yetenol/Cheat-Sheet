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

  > _-match_ uses [regular expression](../languages/regex.md) syntax  
  > `^` Start of line;  `$` End of line;  `.*` $\geq 0$ character(s);  `.+` $\geq 1$ character(s);  `\w*` Any word;  
  > `\s*` Any whitespace;  `(.*)` Unnamed group;     `(?<user>.*)` Named group called user

  ```powershell
  $pattern = "(?i)^user"
  $object | foreach {
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

## Find Pattern

> Quick [**Regular Expression**](../languages/regex.md) Reference for `-match` and `[RegEx]::`  
> `(?ENABLE-DISABLE)` [Interpretation Options](../languages/regex.md#engine-interpretation-options):  `i` IgnoreCase;  `n` ExplicitCapture;  `x` IgnorePatternWhitespace;  `m` Multiline;  `s` Singleline;  
> `^` Start of line;  `$` End of line;  `.*` $\geq 0$ character(s);  `.+` $\geq 1$ character(s);  `\w*` Any word;  `\S*` Any non-whitespace;
> `\s*` Any whitespace;  `(.*)` Unnamed group;     `(?<user>.*)` Named group called user

- find **all** lines starting with _user_

  ```powershell
  $pattern = "(?i)^user"
  $captures = $lines | foreach {
    if ($_ -match $pattern) {
      Write-Output $_
    }
  }
  ```

  > `-ReadCount` speeds up the search when using large files as it sends the lines in 1k batches through the pipeline. Beware of slightly different formatting.

  ```powershell
  $pattern = "(?i)^user"
  $captures = Get-Content -Path ".\example.txt" -ReadCount 1000 | foreach {
    $_ -match $pattern
  }
  ```


- count occurrences

  ```powershell
  $captures.Count
  ```

- find **first** line starting with _user_ 

  ```powershell
  $capture = $captures[0]
  ```

  ```powershell
  $pattern = "(?i)^user"
  $capture = $null
  $lines | foreach {
    if ($_ -match $pattern) {
      $capture = $_
      break # stop further searching
    }
  }
  ```

  > `-ReadCount` is difficult to use here.

- extract the username from the **first** line starting like: _Username: anna_

  > Quick [**Regular Expression**](../languages/regex.md) Reference for `-match` and `[RegEx]::`  
  > `(?ENABLE-DISABLE)` [Interpretation Options](../languages/regex.md#engine-interpretation-options):  `i` IgnoreCase;  `n` ExplicitCapture;  `x` IgnorePatternWhitespace;  `m` Multiline;  `s` Singleline;  
  > `^` Start of line;  `$` End of line;  `.*` $\geq 0$ character(s);  `.+` $\geq 1$ character(s);  `\w*` Any word;  `\S*` Any non-whitespace;
  > `\s*` Any whitespace;  `(.*)` Unnamed group;     `(?<user>.*)` Named group called user

  ```powershell
  $pattern = '(?i)^\s*username:\s*(\w*)\s*'
  # line example   ···Username:···anna····[...] 

  $lines = Get-Content -Path ".\example.txt"

  $capture = $null
  $lines | foreach {
    if ($_ -match $pattern) {
      $capture = $_
      break # stop further searching
    }
  }

  if (-not $capture) {
    Write-Error "No matching line found!"
  } else {
    $regex = [RegEx]::Match($capture, $pattern)
    $username = $regex.Groups[1].value # matched groups start at index 1
    Write-Output @("Successfully extracted:", $username)
  }
  ```

- extract the credentials from **all** lines like: _User: anna Password: turtles\_48_

  > to ignore all unnamed groups, set option `n`

  ```powershell
  $pattern = '(?in)^\s*username:\s*(?<user>.*)\s*password:\s*(?<pwd>.*)\s*$'
  # line example    ···Username:···annaSchmidt···Password:···turtles_48··· 

  $lines = Get-Content -Path ".\example.txt"

  $captures = $lines | foreach {
    if ($_ -match $pattern) {
      Write-Output $_
    }
  }

  if (-not $captures) {
    Write-Error "No matching line found!"
  } else {
    $credentials = @()
    $captures | foreach {
      $regex = [RegEx]::Match($_, $pattern, "IgnoreCase")
      $username = $regex.Groups["user"].value
      $password = $regex.Groups["pwd"].value
      $credentials += [PSCustomObject]@{ 
        Username = $username
        Password = $password
      }
    }
    Write-Output @("Successfully extracted:", $credentials)
  }
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