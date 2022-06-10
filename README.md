# [⌂](README.md) Documentation ![GitHub last commit](https://img.shields.io/github/last-commit/yetenol/doc?color=white)

- Various documentations and tips I have accumulated over the years
- Cheat sheets

## Windows

| Topic                                                     | Example Component        | Example Code                      |
| --------------------------------------------------------- | ------------------------ | --------------------------------- |
| [Components](windows/components.md)                       | Certificates             | `certmgr.msc`                     |
| [Settings app pages](windows/settings.md)                 | Display                  | `ms-settings:display`             |
| [Known Folders](windows/known-folders/known-folders.md)   |                          |                                   |
| ⮱ [User Folders](windows/known-folders/user-folders.md)   | Downloads Folder         | `shell:My Pictures`               |
| ⮱ [OS Panels, Folders](windows/known-folders/guids.md)    | Recycle Bin              | `shell:::{�}`                     |
| ⮱ [GUIDs Archive](windows/known-folders/guids-archive.md) | 3D Objects               | `shell:::{�}`                     |
| [Dll commands](windows/dll.md)                            | Neue Verknüpfung anlegen | `rundll32 appwiz.cpl,NewLinkHere` |
| [Troubleshooters](windows/troubleshooters.md)             | Printer Troubleshooter   | `msdt -id PrinterDiagnosticmsdt`  |
| [Icon libraries](windows/icons.md)                        | Imageres Library         | `shell32.dll`                     |
| [Context menu](windows/context-menu.md)                   | Open in VS Code          |


## Powershell

| Topic                                                          | Example Component       | Example Code                                        |
| -------------------------------------------------------------- | ----------------------- | --------------------------------------------------- |
| [Getting Started](powershell/powershell.md)                    | Help Cmdlets            | `script.ps1.bat`                                    |
| ⮱ [Data Types](powershell/data-types.md)                       | Hashtable               | `[DateTime]::Now`                                   |
| ⮱ [Modify data](powershell/filesystem/modify.md)               | Add calculated property | `$list[@(0..1;-3..-1)]`                             |
| ⮱ [Bash equivalents](powershell/bash-equivalents.md)           | While Loop              | `read name` <-> `$name = Read-Host -Prompt "Name"`  |
| [FileSystem Interactions](powershell/filesystem/filesystem.md) | Run as administrator    | ``explorer "/select,`"$(Resolve-Path $file)`""``    |
| ⮱ [Import](powershell/filesystem/import.md)                    | File Parsing            | `[RegEx]::Match(�, $pattern).Groups[1].value`       |
| ⮱ [Export](powershell/filesystem/export.md)                    | Export spreadsheet      | `Export-Clixml`                                     |
| ⮱ [Links](powershell/filesystem/links.md)                      | Create symbolic link    | `New-Item -ItemType SymbolicLink -Name � -Target �` |
| ⮱ [Attributes](powershell/filesystem/file-attributes.md)       | Make ReadOnly           | `$item.Attributes = $item.Attributes -bor 0x080000` |
| ⮱ [Meta data](powershell/filesystem/metadata.md)               | Get meta data           | _Function_                                          |
| ⮱ [Web](powershell/filesystem/web.md)                          | Download, extract ZIPs  | `Invoke-WebRequest -Uri $url -OutFile $file`        |
| [Applications](powershell/applications.md)                     | Update Store Apps       | `$wmiObj.UpdateScanMethod()`                        |
| [Interactive Menu](powershell/menu.md)                         | Select option 1, 2, 3   | `$Choice = Read-Host -Prompt "Select ..."`          |
| [Encryption](powershell/encryption.md)                         | Passwords               | `ConvertTo-SecureString`                            |
| [Bluetooth](powershell/bluetooth.md)                           | List Devices            | `Get-PnpDevice -Class Bluetooth`                    |
| [Win+X Menu](windows/win-x.md)                                 | Add Win+X entries       |                                                     |


## LaTeX

| Topic                                 | Example Component            | Example Code                                       |
| ------------------------------------- | ---------------------------- | -------------------------------------------------- |
| [Getting Started](latex/latex.md)     | Page Margins                 | `texdoc PACKAGE_NAME`                              |
| [Debugging](latex/debugging.md)       | Syntax Only                  | `\documentclass[draft]{article}`                   |
| [Environments](latex/environments.md) | Modify Existing Environments | `\usepackage{etoolbox}`                            |
| [Floats](latex/floats.md)             | Images                       | `\begin{figure}[htbp]`                             |
| [Useful Packages](latex/packages.md)  | Lipsum Text                  | `\usepackage[utf8]{inputenc}`                      |
| [Spacing](latex/spacing.md)           | Hyphenation                  | `\!` `\,` `\:` `\;` `\quad` `\qquad`               |
| [Tables](latex/tables.md)             | TABULARX                     | `\begin{tabularx}{\columnwidth}{X\|p{1.7cm}\|C\|}` |
| [Mathematics](latex/symbols.md)       | Arrows                       | $\mathbb{N\;Z\;Q\;R\;C} \iff \Psi$                 |


## Languages, Encodings

| Topic                                           | Example Component           | Example Code                                          |
| ----------------------------------------------- | --------------------------- | ----------------------------------------------------- |
| [RegEx: Regular Expression](languages/regex.md) | Quantifiers                 | `(?in)user:(?<name>\S*)\s*key:(?<pwd>\S*)`            |
| [Git](languages/git.md)                         | Commit History: Delete File | `git clone https://yetenol@github.com/yetenol/`       |
| [Unicode](languages/unicode.md)                 | Character Sorting           | `!` `+` `Ξ`                                           |
| [Markdown](languages/markdown.md)               | LaTeX Render                | $\int_0^1{f(\pi^2)}\,dx$                              |
| C › [GNU Debugger](languages/gdb.md)            | Examinate Variables         | `break`                                               |
| [Java](languages/java.md)                       |
| [AutoHotkey v1](languages/autohotkey.md)        | Get Program stdout          | `Shell := ComObjCreate("WScript.Shell")`              |
| Minecraft › [Datapacks](languages/minecraft.md) | Leash Decorations           | `kill @e[type=item,nbt={Item:{id:"minecraft:wool"}}]` |


## Applications

| Topic                      | Example Component | Example Code                                            |
| -------------------------- | ----------------- | ------------------------------------------------------- |
| [Excel](apps/excel.md)     | Empty Range?      | `=IF(SUMPRODUCT(--(A1:C4<>""))<>0,"not empty","empty")` |
| [OneNote](apps/onenote.md) | Matrices          | $\sqrt{a+b}-c\cdot\alpha$                               |