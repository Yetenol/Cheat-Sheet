# Powershell Cheat Sheet
## Export to excel
```
Get-Process | Export-Csv <FILE> -NoType -Delimiter ";"
```

# Tables
## Create table
```
dir | ft Name, Length
```
```
Get-ChildItem | Format-Table -Property Name, Length
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
## Export to excel
```
dir | Export-Csv table.csv -NoType -Delimiter ";"
```
```
Get-ChildItem | Export-Csv -File table.csv -NoTypeInformation -Delimiter ";"
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

Read further
- [Invoke command, item or strings](https://social.technet.microsoft.com/wiki/contents/articles/7703.powershell-running-executables.aspx)