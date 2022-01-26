# Documentation
- Various documentations and tips I have accumulated over the years
- Cheat sheets

### Windows

Topic | Example Component | Example Code
--- | --- | ---
[Components](windows/components.md) | Certificates | `certmgr.msc`
[Settings app pages](windows/settings.md) | Display | `ms-settings:display`
[Special locations (GUID)](windows/guids.md) | Recycle Bin | `shell:::{...}`
[Dll commands](windows/dll.md) | Neue Verknüpfung anlegen | `rundll32 appwiz.cpl,NewLinkHere`
[Troubleshooters](windows/troubleshooters.md) | Printer Troubleshooter | `msdt -id PrinterDiagnosticmsdt`
[Icon libraries](windows/icons.md) | Imageres Library | `shell32.dll`


### Powershell

Topic | Example Component | Example Code
--- | --- | ---
[Getting Started](powershell/getting-started.md) | Help cmdlets | `script.ps1.bat`
[Data Types](powershell/data-types.md) | Hashtable | `[DateTime]::Now`
[Input](powershell/input.md) | File Parsing | `[RegEx]::Match($line, $regexFormat).Groups[1].value`
[Output](powershell/output.md) | Custom Table View | `Export-Clixml`
[Bash equivalents](powershell/bash-equivalents.md) | While Loop | `read name` <-> `$name = Read-Host "Name"`
[Applications](powershell/applications.md) | Update store apps | `$wmiObj.UpdateScanMethod()`
[Interactive Menu](powershell/menu.md) | Select option 1, 2, 3 | `$Choice = Read-Host "Select ..."`
[Encryption](powershell/encryption.md) | Passwords | `ConvertTo-SecureString`
[Bluetooth](powershell/bluetooth.md) | List devices | `Get-PnpDevice -Class Bluetooth`
[File attributes](powershell/file-attributes.md) | make read-only | `function Set-FileAttribute{}`


### Languages, Encodings

Topic | Example Component | Example Code
--- | --- | ---
[Unicode](languages/unicode.md) | Character sorting | `!` `+` `Ξ`
[Git](languages/git.md)
[AutoHotkey v1](languages/autohotkey.md) | Get program stdout |  `Shell := ComObjCreate("WScript.Shell")`
Regular Expression (RegEx)
→➝ [🗎 PDF Overview](languages/regex.pdf)
→➝ [🔗Quick Reference (MS Docs)](https://docs.microsoft.com/en-us/dotnet/standard/base-types/regular-expression-language-quick-reference)
→➝ [🔗Visual Studio (MS Docs)](https://docs.microsoft.com/en-us/visualstudio/ide/using-regular-expressions-in-visual-studio)
C › [GNU Debugger](languages/gdb.md)
Minecraft › [Datapacks](languages/minecraft.md)


### Apps

- [Excel](apps/excel.md)


