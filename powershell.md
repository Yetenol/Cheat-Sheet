# Powershell Cheat Sheet

# Help yourself

## Find the right cmdlet
```
Get-Command | Where-Object Name -Match "vpn"
```

## Help-Files
Update Help Files (Run as admin)
```
Update-Help
```
## Get syntax help
```
(Get-Process -?).syntax
```
Browser help page
```
help Get-Process -online
```
Specific parameter help
```
help Get-Process -Parameter Id
```

# Analyse an object / output
```
dir | Get-Member -MemberType Property
```
## Display output / export to Microsoft Excel
```
dir | Export-Csv .\table.csv -NoType -Delimiter ";"
.\table.csv
```
```
Get-ChildItem | Export-Csv -File .\table.csv -NoTypeInformation -Delimiter ";"
.\table.csv
```


# Variables - Common data types
Examples | .GetType()-Names
--- | ---
42 | Integers (Convert automatically to larger types) <br> <b>Int32, Int (32-bit signed integer)</b> <br> Int64, Long (64-bit signed integer)
3,65 | Decimal numbers <br> <b>Double (Double-precision 64-bit floating point number)</b> <br> Single, Float (Single-precision 32-bit floating point number)
$True <br> $False | <b>Boolean</b>
"Hello" <br> 'Raw &%\Text' <br> "$env:temp\Trash" <br> "Hi " + $a + "!"| Text or single characters <br> <b>String (Fixed-length string of Unicode characters)</b> <br> Char (A Unicode 16-bit character)
[DateTime]::Now <br> [DateTime]::UtcNow <br> [DateTime]"1999-12-31" <br> [DateTime]"23:45:33" <br> [DateTime]"1.1.07 12:30" | Timestamp as date and time <br> <b>DateTime</b>
@(1; 2; 3; 7) <br> @(1..3; 7) <br> @('I'; 'am'; "here") | <b>Object[], Array</b>
@{X=12; Y=45; N="Karl"} | Dictionary of key/value pairs <br> <b>Hashtable</b>
[ordered]@{X=12; Y=45} | Ordered dictionary of key/value pairs <br> <b>OrderedDictionary</b>


# Get user input

### Enter plaintext input in console
```
$User = Get-Host "Username"
```
### Get plaintext input from file at specific line
TotalCount speeds up the commands by only loading the first 26 lines.
```
$Line26 = (Get-Content ".\data.txt")[25]
```
```
$Line26 = (Get-Content ".\data.txt" -TotalCount 26)[25]
```
Get first line starting with <i>User</i>
```
$Lines_User = Get-Content ".\data.txt" -ReadCount 1000 | 
  foreach {$_ -match "^User"}
$Lines_User[0]
```
Get first line with <i>User: \<username\> </i>
```
$Lines_User = Get-Content ".\data.txt" -ReadCount 1000 | 
  foreach {$_ -match "^User:"}
$Username = [RegEx]::Match($Lines_User[0], "^User:\s*(.*)").Groups[1].value
```


# Get sensitive input
<b> Don't save passwords as plain text </b> <br>
Instead save them as a secure string and encrypt them locally.

## Enter sensitive input in console
```
$Secure = Read-Host "Password" -AsSecureString
```
## Decrypt locally
Only the <b>SAME INSTANCE</b> can decrypt. The last line prevents memory leaks.
```
$bstr = [System.Runtime.InteropServices.Marshal]::SecureStringToBSTR($Secure)
$Plaintext [System.Runtime.InteropServices.Marshal]::PtrToStringAuto($bstr)
[System.Runtime.InteropServices.Marshal]::ZeroFreeBSTR($bstr)
```
## Save / export to file
The data is encrypted using the Windows Data Protection API (DPAPI). <br>
Only the <b>SAME USER ON THE SAME MASHINE</b> can decrypt.
```
$Secure = Read-Host "Password" -AsSecureString
ConvertFrom-SecureString $Secure | Out-File "${Env:AppData}\Credential.bin"
```
## Import from file
Only the <b>SAME USER ON THE SAME MASHINE</b> can decrypt.
```
$Secure = Get-Content "${Env:AppData}\Sec.bin" | ConvertTo-SecureString
```

## Select input from list
```
$promt = "Select from:
1 Sleep
2 Shutdown
r Restart
"
do {
  $Choice = Read-Host "$promt"
  switch ($Choice) {
    1 {"You selected Sleep"}
    2 {"You selected Shutdown"}
    "r" {"You selected Restart"}
    default {$Choice = $null; "Invalid choice!"}
  }
} while ($Choice -eq $null)
````

function Show-Hello {
param (
    [ValidateSet("World", "Galaxy", "Universe")]
    [String]$noun
)
$greetingString = "Hello, " + $noun + "!"
Write-Host "`t=>`t" $greetingString "`t<="
 }






# Tables
## Display table
```
dir | ft Name, Length
```
```
Get-ChildItem | Format-Table -Property Name, Length
```

## Export object as table to Microsoft Excel
```
Get-Process | Export-Csv <FILE> -NoType -Delimiter ";"
```

## Rename table columns
```
Get-ChildItem | Format-Table -Property Name, `
@{Label="Size|Byte"; Expression={$_.Length}}
```
## Custom table columns
```
Get-ChildItem | Format-Table -Property Name, `
@{Label="Size|KB"; Expression={[math]::Round($_.Length / 1KB, 2)}}
```
## Interesting information
```
Get-ChildItem $env:SystemRoot\* -Include *.exe, *.dll | Format-Table -Property `
BaseName, Extension, `
@{Label="Description"; Expression={[System.Diagnostics.FileVersionInfo]::GetVersionInfo($_).FileDescription}}, `
@{Label="Version"; Expression={[System.Diagnostics.FileVersionInfo]::GetVersionInfo($_).FileVersion}}
```
## Get path apps
```
[String[]]$paths = @($env:path -split ";")
$paths = $paths[0..($paths.Length-2)]
$paths = $paths.ForEach({"$_\*"})
Get-ChildItem -Path $paths -Include *.exe, *.msc `
| Select -Property `
@{Label="Type"; Expression={($_.Extension.toUpper() -replace "\`.","")}}, `
@{Label="Command"; Expression={($_.Name -replace ".exe", "")}}, `
@{Label="Description"; Expression={[System.Diagnostics.FileVersionInfo]::GetVersionInfo($_).FileDescription}}, `
@{Label="Version"; Expression={[System.Diagnostics.FileVersionInfo]::GetVersionInfo($_).FileVersion}}, `
@{Label="Size|KB"; Expression={[math]::Round($_.Length / 1KB)}}, `
@{Label="Location"; Expression={$_.Directory}} `
| Sort-Object -Property `
@{Expression="Location"; Descending=$False}, `
@{Expression="Extension"; Descending=$True}, `
@{Expression="Description"; Descending=$False} `
| Export-Csv -Path "$env:temp\path-apps.csv" -NoType -Delimiter ";"
start "$env:temp\path-apps.csv"
```

# Random stuff

## Open location in Windows Explorer
```
ii .
```
```
Invote-Item .
```
## Create empty file
```
Out-File .\new.txt
```

## Open Powershell from Windows Explorer
Press `Shift + Right click` and select `Open Powershell window here`

Read further
- [Invoke command, item or strings](https://social.technet.microsoft.com/wiki/contents/articles/7703.powershell-running-executables.aspx)