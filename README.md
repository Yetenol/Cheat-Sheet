<h1> Documentation <img alt="GitHub last commit" src="https://img.shields.io/github/last-commit/yetenol/doc?color=white"></h1>

[⌂](README.md) Home

> This project contains all my documentations of my developer life. 
> This includes code templates, tips and tricks, cheat sheets and glossaries.

Table of Contents
- [Windows](#windows)
- [Powershell](#powershell)
- [LaTeX](#latex)
- [Languages, Encodings](#languages-encodings)
- [Applications](#applications)
- [Discussions](#discussions)

## Windows

- **[Components ›](windows/components.md)**  
    Certificates | `certmgr.msc`

- **[Settings app pages ›](windows/settings.md)**  
    Display | `ms-settings:display`

- **[Known Folders ›](windows/known-folders/known-folders.md)**  

    - **[User Folders ›](windows/known-folders/user-folders.md)**  
        Downloads Folder | `shell:My Pictures`

    - **[OS Panels, Folders ›](windows/known-folders/guids.md)**  
        Recycle Bin | `shell:::{�}`

    - **[GUIDs Archive ›](windows/known-folders/guids-archive.md)**  
        3D Objects | `shell:::{�}`

- **[Dll commands ›](windows/dll.md)**  
    Neue Verknüpfung anlegen | `rundll32 appwiz.cpl,NewLinkHere`

- **[Troubleshooters ›](windows/troubleshooters.md)**  
    Printer Troubleshooter | `msdt -id PrinterDiagnosticmsdt`

- **[Icon libraries ›](windows/icons.md)**  
    Images Library | `shell32.dll`

- **[Context menu ›](windows/context-menu.md)**  
    Open in VS Code


## Powershell

- **[Getting Started ›](powershell/basics/basics.md)**  
    Help Cmdlets | `script.ps1.bat`

    - **[Data Types ›](powershell/basics/data-types.md)**  
        Hashtable | `[DateTime]::Now`

    - **[Modify data ›](powershell/basics/modify.md)**  
        Add calculated property | `$list[	(0..1;-3..-1)]`

    - **[Bash equivalents ›](powershell/basics/bash-equivalents.md)**  
        While Loop | `read name` ⟷ `$name = Read-Host -Prompt "Name"`

- **[File System Interactions ›](powershell/filesystem/filesystem.md)**  
    Run as administrator | ``explorer "/select,`"$(Resolve-Path $file)`""``

    - **[Import ›](powershell/filesystem/import.md)**  
        File Parsing | `[RegEx]::Match(�, $pattern).Groups[1].value`

    - **[Export ›](powershell/filesystem/export.md)**  
        Export spreadsheet | `Export-Clixml`

    - **[Links ›](powershell/filesystem/links.md)**  
        Create symbolic link | `New-Item -ItemType SymbolicLink -Name � -Target �`

    - **[Attributes ›](powershell/filesystem/attributes.md)**  
        Make ReadOnly | `$item.Attributes = $item.Attributes -bor 0x080000`

    - **[Meta data ›](powershell/filesystem/metadata.md)**  
        Get meta data | _Function_

    - **[Web ›](powershell/filesystem/web.md)**  
        Download, extract ZIPs | `Invoke-WebRequest -Uri $url -OutFile $file`

- **[Applications ›](powershell/applications.md)**  
    Update Store Apps | `$wmiObj.UpdateScanMethod()`

- **[Interactive Menu ›](powershell/menu.md)**  
    Select option 1, 2, 3 | `$Choice = Read-Host -Prompt "Select ..."`

- **[Encryption ›](powershell/encryption.md)**  
    Passwords | `ConvertTo-SecureString`

- **[Bluetooth ›](powershell/bluetooth.md)**  
    List Devices | `Get-PnpDevice -Class Bluetooth`

- **[Win+X Menu ›](windows/win-x.md)**  
    Add Win+X entries


## LaTeX

- **[Getting Started ›](latex/latex.md)**  
    Project Structure | `texdoc PACKAGE_NAME`

- **[Floating Bodies ›](latex/floats.md)**  
    Images | `\begin{figure}[htbp]`

    - **[Tables ›](latex/tables.md)**  
        Auto-Stretching Columns | `S[table-format = -3.0e-1]`

- **[Symbols ›](latex/symbols.md)**  
    Arrows | `\mathbb{NR}` → ℕℝ

- **[Mathematics ›](latex/math.md)**  
    Norm | 

- **[Layout ›](latex/layout.md)**  
    Hyphenation | `\!` `\,` `\:` `\;` `\quad` `\qquad`

- **[Useful Packages ›](latex/packages.md)**  
    Lipsum Text | `\usepackage[utf8]{inputenc}`

- **[Modify Environments ›](latex/environments.md)**  
    Modify Existing Environments | `\usepackage{etoolbox}`


## Languages, Encodings

- **[Regular Expression ›](languages/regex.md)**  
    Quantifiers | `(?in)user:(?<name>\S*)\s*key:(?<pwd>\S*)`

- **[Java ›](languages/java.md)**  

- **[Git ›](languages/git.md)**  
    Delete binary from history | `git clone git@github.com:Yetenol/�.git`

- **[Unicode ›](languages/unicode.md)**  
    Character Sorting | `!` `+` `Ξ`

- **[Markdown ›](languages/markdown.md)**  
    LaTeX Render | `$e^{i\pi}=-1$` → <img src="https://render.githubusercontent.com/render/math?math=e^{i\pi}=-1">

- **C › [GNU Debugger ›](languages/gdb.md)**  
    Examinate Variables | `break`


- **[AutoHotkey v1 ›](languages/autohotkey.md)**  
    Get Program stdout | `Shell := ComObjCreate("WScript.Shell")`

- **Minecraft › [Datapacks ›](languages/minecraft.md)**  
    Leash Decorations | `kill 	e[type=item,nbt={Item:{id:"minecraft:wool"}}]`


## Applications

- **[Excel ›](apps/excel.md)**  
    Empty Range? | `=IF(SUMPRODUCT(--(A1:C4<>""))<>0,"not empty","empty")`

- **[OneNote ›](apps/onenote.md)**  
    Mathematical Typesetting | `\displaystyle\bmatrix(1&2@a&b) `


## Discussions

- **[Indentation: Tabs vs Spaces ›](discussion/indentation.md)**  