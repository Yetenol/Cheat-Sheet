# Documentation
- Various documentations and tips I have accumulated over the years
- Cheat sheets

### Windows

- [Components](windows/components.md) _e.g. `Certificates`,_ certmgr.msc
- [Settings app pages](windows/ms-settings.md) _e.g. `Display`,_ ms-settings:display
- [Special locations (GUID)](windows/guids.md) _e.g. `Recycle Bin`,_ shell:::{...}
- [Dll commands](windows/dll.md) _e.g. `Neue Verknüpfung anlegen`,_ rundll32 appwiz.cpl,NewLinkHere
- [Troubleshooters](windows/troubleshooters.md) _e.g. `Printer Troubleshooter`,_ msdt -id PrinterDiagnosticmsdt
- [Icon libraries](windows/icons.md) _e.g. `Imageres Library`,_ shell32.dll


### Powershell

- [Getting Started](powershell/getting-started.md) _e.g. _`Help cmdlets`,_ script.ps1.bat
- [Data Types](powershell/data-types.md) _e.g. `Hashtable`,_ [DateTime]::Now
- [Input](powershell/input.md) _e.g. `File Parsing`,_ [RegEx]::Match($line, $regexFormat).Groups[1].value
- [Output](powershell/output.md) _e.g. `Custom Table View`,_ Export-Clixml
- [Interactive Menu](powershell/menu.md) _e.g. `Select option 1, 2, 3`,_ $Choice = Read-Host "Select ..."
- [Encryption](powershell/encryption.md) _e.g. `Passwords`,_ ConvertTo-SecureString
- [Bluetooth](powershell/bluetooth.md) _e.g. `List devices`,_ Get-PnpDevice -Class Bluetooth
- [File attributes](powershell/file-attributes.md) _e.g. `make read-only`,_ function Set-FileAttribute{}


### Languages

- `[AutoHotkey]` [AutoHotkey](languages/autohotkey.md)
- `[RegEx]` Regular Expression
    - [🗎 PDF Overview](languages/regex.pdf)
    - [🔗Quick Reference (MS Docs)](https://docs.microsoft.com/en-us/dotnet/standard/base-types/regular-expression-language-quick-reference)
    - [🔗Visual Studio (MS Docs)](https://docs.microsoft.com/en-us/visualstudio/ide/using-regular-expressions-in-visual-studio) 
- `[C]` [GNU Debugger](languages/gdb.md)
- `[Git]` [Git](languages/git.md)
- `[Minecraft]` [Datapacks](languages/minecraft.md)


### Apps

- [Excel](apps/excel.md)


