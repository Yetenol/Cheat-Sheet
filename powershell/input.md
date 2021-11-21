# [⌂](../README.md) › [Powershell](../README.md#powershell) › Input Handling

# User input

### Enter plaintext input in console
```powershell
$User = Get-Host "Username"
```

# File input
### Get plaintext input from file at specific line
> _TotalCount speeds up the commands by only loading the first 26 lines._
```powershell
$Line26 = (Get-Content -Path <#File#>)[25]
```

```powershell
$Line26 = (Get-Content -Path <#File#> -TotalCount 26)[25]
```

Get first line starting with <i>User</i>
```powershell
$Lines_User = Get-Content -Path <#File#> -ReadCount 1000 # Load in shunks of 1k lines
  | foreach {$_ -match "^User"} # ^: Beginning of line (regex)
$Lines_User[0]                  # Only use first line
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