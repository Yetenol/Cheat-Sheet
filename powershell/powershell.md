# [⌂](../README.md) › [PowerShell](../README.md#powershell) › Getting Started

# Make a powershell script executable
- Attach .bat at the end of your script filename e.g: `script.ps1.bat`
- Add this as the first line of code
```cmd
# & cls & powershell -Command "Invoke-Command -ScriptBlock ([ScriptBlock]::Create(((Get-Content """%0""") -join """`n""")))" & exit
# The above line makes the script executable when renamed .cmd or .bat
```

# Help Yourself

## Discover available commands[ᴰ](glossary.md#command)
```powershell
Get-Command | where {$_.Name -Match "vpn"}
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


## Function[ᴰ](glossary.md#function): Set parameter AutoComplete

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

## Download file

```powershell
Invoke-WebRequest http://www.het.brown.edu/guide/UNIX-password-security.txt -OutFile .\newname.txt
# shorter syntax
iwr http://www.het.brown.edu/guide/UNIX-password-security.txt -o newname.txt
```