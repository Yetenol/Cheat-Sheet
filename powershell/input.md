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
  $object = Import-Clixml -Path <#XML-File#>
  ```

- count its number of items

  ```powershell
  $object = Import-Clixml -Path <#XML-File#>
  $object.Count
  ```

  ```powershell
  ($object = Import-Clixml -Path <#XML-File#>).Count
  ```

- find all items whose name starts with _user_

  > _-match_ uses [regular expression](../languages/regex.md) syntax  
  > `^` Start of line;  `$` End of line;  `.*` $\geq 0$ character(s);  `.+` $\geq 1$ character(s);  `\w*` Any word;  
  > `\s*` Any whitespace;  `(.*)` Unnamed group;     `(?<user>.*)` Named group called user

  ```powershell
  $object | foreach {
    if ($_.Name -match "^user") {
      Write-Output $_
    }
  }
  ```


# Plain text file

- import all lines from a plain text file

  ```powershell
  $lines = Get-Content -Path <#File#>
  ```

- only import (a) specific line(s)

  ```powershell
  $line26      = (Get-Content -Path <#File#>)[25]
  $line23til26 = (Get-Content -Path <#File#>)[22..25]
  ```

  > `-TotalCount` speeds up the commands by only loading the first 26 lines.

  ```powershell
  $line26      = (Get-Content -Path <#File#> -TotalCount 26)[25]
  $line23til26 = (Get-Content -Path <#File#> -TotalCount 26)[22..25]
  ```

- count number of lines

  ```powershell
  $lines = Get-Content -Path <#File#>
  $lines.Count
  ```

  ```powershell
  ($lines = Get-Content -Path <#File#>).Count
  ```

## Find Occurrences

> `-match` uses [regular expression](../languages/regex.md) syntax  
> `^` Start of line;  `$` End of line;  `.*` $\geq 0$ character(s);  `.+` $\geq 1$ character(s);  `\w*` Any word;  
> `\s*` Any whitespace;  `(.*)` Unnamed group;     `(?<user>.*)` Named group called user

- find **all** lines starting with _user_

  ```powershell
  $captures = $lines | foreach {
    if ($_ -match "^user") {
      Write-Output $_
    }
  }
  ```

  > `-ReadCount` speeds up the search when using large files as it sends the lines in 1k batches through the pipeline. Beware of slightly different formatting.

  ```powershell
  $captures = Get-Content -Path .\env.txt -ReadCount 1000 | foreach {
    $_ -match "^user"
  }
  ```


- count occurrences

  ```powershell
  $captures.Count
  ```

- find **first** line starting with _user_ 

  ```powershell
  $lines | foreach {
    if ($_ -match "^user") {
      $capture = $_
      break # stop further searching
    }
  }
  ```


Get first line with <i>User: \<username\> </i>

```powershell
# LineFormat =   ···Username:···anna···Password:···turles1987·· 
$regexFormat = "^\s*Username:\s*(.*)\s*Password:\s*(?<pwd>.*)\s*$"
# ^: Start of line      $: End of line      \s*: Whitespace
# (.*) Unnamed entry    (?<pwd>.*) Named entry called pwd

$validLines = Get-Content -Path <#File#>text.txt -ReadCount 1000 `
  | foreach {$_ -match $regexFormat}

if($validLines.Count -le 0) {
  Write-Host -Object "No entries found!"
} elseif($validLines.Count -eq 1) {
  # Use this code if you only want one entry
  $regex = [RegEx]::Match($validLines[0], $regexFormat) # Only use first entry
  $Username = $regex.Groups[1].value # Matches start at index 1
  $Password = $regex.Groups["pwd"].value
  Write-Output -InputObject @("Successfully extracted:", $Username, $Password)
} else {
  # Use this code if you want multiple entries
  $credentials = @{}
  foreach ($line in $validLines) {
    $regex = [RegEx]::Match($line, $regexFormat)
    $Username = $regex.Groups[1].value # Matches start at index 1
    $Password = $regex.Groups["pwd"].value
    $credentials[$Username] = $Password
  }
  Write-Host -Object "Successfully extracted:"
  Write-Output -InputObject $credentials
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