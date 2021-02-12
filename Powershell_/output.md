# Powershell - Input / Output Handling

# Your best buddies / Analyse an output
Since everything in PowerShell already is or becomes an object you should know how to analyse and handle them. Objects are most easily visualised as text tables but keep in mind that each value can be an object itself.
What <b>type of object</b> am I working with <br>
- Most return type are Object[]: Array of Objects
- External programs return an Object[] containing Strings
```powershell
# You can often replace $o with a command directly
# Sometimes you have to surround it in brackets
$o = <# command e.g: Get-Process #>

# Display object in GUI
$o | Out-GridView                      # Display main properties
$o | Select-Object * | Out-GridView           # Display all properties
$o | Get-Member -MemberType Properties # List property names (table header)

# Access member properties or methods()
$o | Get-Member | Select -First 1    # Show object type
$o | Get-Member -MemberType Method   # List method names
$o.<# member name #>                 # Access members
$o[<# range[] # e.g: $o[0..5+7] #>]  # Access range of indexes or lines
$o.Count                             # If array: Get number of elements
$o[0].GetType()                      # If array: Get element's type

# Working with objects
$o | Select-Object <# Properties e.g: Name, ID #>
$o | Where-Object {$_.<# member #> <# operator #> <# value #>}
<#  $_: Current entry (line)    Examples:
$o | Where-Object {$_.Company}                   # Require value for Company
$o | Where-Object {$_.Company -match "^Microsoft"}        # Regular Expression
$o | Where-Object {$_.Path -eq "C:\WINDOWS\Explorer.exe"}
$o | Where-Object {$_.WorkingSet -gt 250MB -and $_.StartTime -le [DateTime]"8:00"}
#>
$o | Group-Object <# Property #>
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