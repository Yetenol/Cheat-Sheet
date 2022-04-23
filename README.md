# [⌂](README.md) Documentation ![GitHub last commit](https://img.shields.io/github/last-commit/yetenol/doc?color=white)

- Various documentations and tips I have accumulated over the years
- Cheat sheets

### Windows

| Topic                                                          | Example Component        | Example Code                      |
| -------------------------------------------------------------- | ------------------------ | --------------------------------- |
| [Components](windows/components.md)                            | Certificates             | `certmgr.msc`                     |
| [Settings app pages](windows/settings.md)                      | Display                  | `ms-settings:display`             |
| Known Folders                                                  |
| ⮱ [User Folders](user-windows/known-folders/user-folders.md)   | Downloads Folder         | `shell:My Pictures`               |
| ⮱ [Special locations (GUID)](windows/known-folders/guids.md)   | Recycle Bin              | `shell:::{...}`                   |
| ⮱ [GUID archive](guids-windows/known-folders/guids-archive.md) | 3D Objects               | `shell:::{...}`                   |
| [Dll commands](windows/dll.md)                                 | Neue Verknüpfung anlegen | `rundll32 appwiz.cpl,NewLinkHere` |
| [Troubleshooters](windows/troubleshooters.md)                  | Printer Troubleshooter   | `msdt -id PrinterDiagnosticmsdt`  |
| [Icon libraries](windows/icons.md)                             | Imageres Library         | `shell32.dll`                     |


### Powershell

| Topic                                              | Example Component     | Example Code                                          |
| -------------------------------------------------- | --------------------- | ----------------------------------------------------- |
| [Getting Started](powershell/powershell.md)        | Help Cmdlets          | `script.ps1.bat`                                      |
| [Data Types](powershell/data-types.md)             | Hashtable             | `[DateTime]::Now`                                     |
| [Input](powershell/input.md)                       | File Parsing          | `[RegEx]::Match($line, $regexFormat).Groups[1].value` |
| [Output](powershell/output.md)                     | Custom Table View     | `Export-Clixml`                                       |
| [Bash equivalents](powershell/bash-equivalents.md) | While Loop            | `read name` <-> `$name = Read-Host "Name"`            |
| [Applications](powershell/applications.md)         | Update Store Apps     | `$wmiObj.UpdateScanMethod()`                          |
| [Interactive Menu](powershell/menu.md)             | Select option 1, 2, 3 | `$Choice = Read-Host "Select ..."`                    |
| [Encryption](powershell/encryption.md)             | Passwords             | `ConvertTo-SecureString`                              |
| [Bluetooth](powershell/bluetooth.md)               | List Devices          | `Get-PnpDevice -Class Bluetooth`                      |
| [File attributes](powershell/file-attributes.md)   | Make ReadOnly         | `$item.Attributes = $item.Attributes -bor 0x080000`   |


### LaTeX

| Topic                                 | Example Component            | Example Code                                       |
| ------------------------------------- | ---------------------------- | -------------------------------------------------- |
| [Getting Started](latex/latex.md)     | Page Margins                 | `texdoc PACKAGE_NAME`                              |
| [Debugging](latex/debugging.md)       | Syntax Only                  | `\documentclass[draft]{article}`                   |
| [Environments](latex/environments.md) | Modify Existing Environments | `\usepackage{etoolbox}`                            |
| [Floats](latex/floats.md)             | Images                       | `\begin{figure}[htbp]`                             |
| [Useful Packages](latex/packages.md)  | Lipsum Text                  | `\usepackage[utf8]{inputenc}`                      |
| [Spacing](latex/spacing.md)           | Hyphenation                  | `\!` `\,` `\:` `\;` `\quad` `\qquad`               |
| [Tables](latex/tables.md)             | TABULARX                     | `\begin{tabularx}{\columnwidth}{X\|p{1.7cm}\|C\|}` |




### Languages, Encodings

| Topic                                            | Example Component           | Example Code                                                                      |
| ------------------------------------------------ | --------------------------- | --------------------------------------------------------------------------------- |
| [Unicode](languages/unicode.md)                  | Character Sorting           | `!` `+` `Ξ`                                                                       |
| [Git](languages/git.md)                          | Commit History: Delete File | `git clone https://yetenol@github.com/yetenol/`                                   |
| [AutoHotkey v1](languages/autohotkey.md)         | Get Program stdout          | `Shell := ComObjCreate("WScript.Shell")`                                          |
| [Regular Expression (RegEx)](languages/regex.md) | Quantifiers                 | `(?in)user:(?<name>\S*)\s*key:(?<pwd>\S*)`                                        |
| C › [GNU Debugger](languages/gdb.md)             | Examinate Variables         | `break`                                                                           |
| Minecraft › [Datapacks](languages/minecraft.md)  | Leash Decorations           | `kill @e[type=item,nbt={Item:{id:"minecraft:wool"}}]`                             |
| [Markdown](languages/markdown.md)                | LaTeX Render                | <img src="https://render.githubusercontent.com/render/math?math=\int_0^1{\pi^2}"> |


### Applications

| Topic                  | Example Component | Example Code                                            |
| ---------------------- | ----------------- | ------------------------------------------------------- |
| [Excel](apps/excel.md) | Empty Range?      | `=IF(SUMPRODUCT(--(A1:C4<>""))<>0,"not empty","empty")` |