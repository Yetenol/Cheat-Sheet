# Powershell - Input / Output Handling

# Analyse an output
What <b>type of object</b> am I working with <br>
- Most return type are Object[]: Array of Objects
- External programs return an Object[] containing Strings
```powershell
$o = <# command #>
$o.GetType()                         # Get return type
$o.Count                             # If array: Get number of elements
$o[0].GetType()                      # If array: Get element's type
$o | Get-Member -MemberType Property # Get properties list
$o | Get-Member -MemberType Method   # Get methods list
$o.<# member name #>                 # Access members
```

## Display output over multiple pages
```powershell
<# command #> | more
```

## Display output in Microsoft Excel
- To hide the header add -NoTypeInformation
```powershell
<# command #> | Export-Csv -Path .\table.csv -Delimiter ";"
.\table.csv
```

## Export to Microsoft Excel
Hides the type header
```powershell
<# command #> | Export-Csv -Path .\table.csv -NoTypeInformation -Delimiter ";"
```

## Export to file
The data is encrypted using the Windows Data Protection API (DPAPI). <br>
Only the <b>SAME USER ON THE SAME MASHINE</b> can decrypt.
```powershell
$Secure = Read-Host "Password" -AsSecureString
ConvertFrom-SecureString $Secure | Out-File "${Env:AppData}\Credential.bin"
```

## Import from file
Only the <b>SAME USER ON THE SAME MASHINE</b> can decrypt.
```powershell
$Secure = Get-Content "${Env:AppData}\Sec.bin" | ConvertTo-SecureString
```



# Files


# Tables
## Display table
```powershell
Get-ChildItem | Format-Table -Property Name, Length
```
> DIRTY CODE: `dir | ft Name, Length`

## Export object as table to Microsoft Excel
```powershell
Get-Process | Export-Csv -Path <#File#>table.csv -NoTypeInformation -Delimiter ";"
```
> DIRTY CODE: `Get-Process | Export-Csv <#File#>table.csv -NoType -Delimiter ";"`


## Rename table columns
```powershell
Get-ChildItem | Format-Table -Property Name, `
@{Label="Size|Byte"; Expression={$_.Length}}
```

## Custom table columns
```powershell
Get-ChildItem | Format-Table -Property Name, `
@{Label="Size|KB"; Expression={[math]::Round($_.Length / 1KB, 2)}}
```
## Interesting information
```powershell
Get-ChildItem -Path $env:SystemRoot\* -Include *.exe, *.dll | Format-Table -Property `
  BaseName, Extension, `
  @{Label="Description"; Expression={[System.Diagnostics.FileVersionInfo]::GetVersionInfo($_).FileDescription}}, `
  @{Label="Version"; Expression={[System.Diagnostics.FileVersionInfo]::GetVersionInfo($_).FileVersion}}
```