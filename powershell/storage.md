# [⌂](../README.md) › [PowerShell](../README.md#powershell) › Storage, Shell Links

## Windows Explorer

- Open current folder
    ```powershell
    Invoke-Item -Path .
    ```
    ```powershell
    explorer (Resolve-Path .) # can only open one folder
    ```
    > DIRTY CODE: `ii .`

- Select one file or folder
    ```powershell
    explorer "/select,`"$(Resolve-Path $file)`""
    ```

## Create empty file

```powershell
Out-File -FilePath ".\example.txt"
```
> DIRTY CODE: `Out-File <#File#>`


## Create a shell link (shortcut)

- Create a shortcut in Startup
    ```powershell
    $env:Startup = (New-Object -ComObject Shell.Application).NameSpace('shell:Startup').Self.Path

    $WshShell = New-Object -comObject WScript.Shell
    $Shortcut = $WshShell.CreateShortcut("$env:Startup\example.lnk")
    $Shortcut.TargetPath = "powershell.exe"
    $Shortcut.WorkingDirectory = $env:TEMP
    $Shortcut.Arguments = '-NoExit -Command "date"'
    $Shortcut.IconLocation = "$env:SystemRoot\System32\notepad.exe"
    $Shortcut.WindowStyle = [System.Diagnostics.ProcessWindowStyle]::Maximized
    $Shortcut.Hotkey = "ALT+CTRL+F"
    $Shortcut.Description = "Hover tooltip"
    $Shortcut.Save()
    ```

## Run as administrator

- Enable elevated execution
    ```powershell
    $bytes = [System.IO.File]::ReadAllBytes((Resolve-Path $file))
    $bytes[0x15] = $bytes[0x15] -bor 0x20 #set byte 21 (0x15) bit 6 (0x20) ON
    [System.IO.File]::WriteAllBytes((Resolve-Path $file), $bytes)
    ```

- Disable elevated execution
    ```powershell
    $bytes = [System.IO.File]::ReadAllBytes((Resolve-Path $file))
    $bytes[0x15] = $bytes[0x15] -bxor 0x20 #set byte 21 (0x15) bit 6 (0x20) ON
    [System.IO.File]::WriteAllBytes((Resolve-Path $file), $bytes)
    ```


## Symbolic links

- Create a symbolic link
    ```powershell
    New-Item -ItemType SymbolicLink `
        -Name <# Filename or Foldername #> `
        -Target <# Target Path #>
    ```

- Create a hard link
    ```powershell
    New-Item -ItemType HardLink `
        -Name <# Filename #> `
        -Target <# Target Path #>
    ```

- Create a junction
    ```powershell
    New-Item -ItemType Junction `
        -Name <# Folder name #> `
        -Target <# Target Path #>
    ```


# Sources

- 2022-04-25: [Create a desktop shortcut with Windows Script Host - Windows Client - Microsoft Docs](https://docs.microsoft.com/en-us/troubleshoot/windows-client/admin-development/create-desktop-shortcut-with-wsh)
- 2022-04-25: [windows - How to create a Run As Administrator shortcut using Powershell - Stack Overflow](https://stackoverflow.com/questions/28997799/how-to-create-a-run-as-administrator-shortcut-using-powershell)
- 2022-04-25: [PowerShell- Running Executables - TechNet Articles - United States (English) - TechNet Wiki](https://social.technet.microsoft.com/wiki/contents/articles/7703.powershell-running-executables.aspx)