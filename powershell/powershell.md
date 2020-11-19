# Powershell Cheat Sheet

# Make a powershell script executable
- Attach .bat to your script filename e.g: `script.ps1.bat`
- Add this as the first line of code
```powershell
# & start powershell -Command "Invoke-Command -ScriptBlock ([ScriptBlock]::Create(((Get-Content %0) -join """`n""")))" & exit
# The above line makes the script executable when renamed .cmd or .bat
```

# Help yourself

## Find the right cmdlet
```powershell
Get-Command | Where-Object -Property Name -Match "vpn"
```

## Help-Files
Update Help Files (Run as admin)
```powershell
Update-Help
```

## Get syntax help
```powershell
(Get-Process -?).syntax
```

Browser help page
```powershell
help Get-Process -online
```

Specific parameter help
```powershell
help Get-Process -Parameter Id
```




# Variables - Common data types
Examples | .GetType()-Names
--- | ---
42 | Integers (Convert automatically to larger types) <br> <b>Int32, Int (32-bit signed integer)</b> <br> Int64, Long (64-bit signed integer)
3.65 | Decimal numbers <br> <b>Double (Double-precision 64-bit floating point number)</b> <br> Single, Float (Single-precision 32-bit floating point number)
$True <br> $False | <b>Boolean</b>
"Hello" <br> 'Raw &%\Text' <br> "$env:temp\Trash" <br> ("Hi " + $a + "!`n")| Text or single characters <br> <b>String (Fixed-length string of Unicode characters)</b> <br> Char (A Unicode 16-bit character)
[DateTime]::Now <br> [DateTime]::UtcNow <br> [DateTime]"1999-12-31" <br> [DateTime]"23:45:33" <br> [DateTime]"1.1.07 12:30" | Timestamp as date and time <br> <b>DateTime</b>
@(1; 2; 3; 7) <br> @(1..3; 7) <br> @('I'; 'am'; "here") | <b>Object[], Array</b>
@{X=12; Y=45; N="Karl"} | Dictionary of key/value pairs <br> <b>Hashtable</b>
[ordered]@{X=12; Y=45} | Ordered dictionary of key/value pairs <br> <b>OrderedDictionary</b>




## Function: Set parameter AutoComplete

```powershell
function Show-Hello {
  param (
    [ValidateSet("World", "Galaxy", "Universe")]
    [String]$noun
  )
  $greetingString = "Hello, " + $noun + "!"
  Write-Host "`t=>`t" $greetingString "`t<="
}
```








## Get path apps
```powershell
$paths = [String[]] @($env:path -split ";") 
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
```powershell
Invote-Item -Path .
```
> DIRTY CODE: `ii .`

## Create empty file
```powershell
Out-File -FilePath <#File>
```
> DIRTY CODE: Out-File <#File#>

## Open Powershell from Windows Explorer
Press `Shift + Right click` and select `Open Powershell window here`

Read further
- [Invoke command, item or strings](https://social.technet.microsoft.com/wiki/contents/articles/7703.powershell-running-executables.aspx)