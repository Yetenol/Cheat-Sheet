# Create a shell link (shortcut)

- **Enable** _run at startup_
    ```powershell
    $path = "C:\Windows\system32\notepad.exe"
    $shortcutName = "example.lnk"

    $env:Startup = (New-Object -ComObject Shell.Application).NameSpace('shell:Startup').Self.Path
    $WshShell = New-Object -comObject WScript.Shell
    $Shortcut = $WshShell.CreateShortcut("$env:Startup\$shortcutName")
    $Shortcut.TargetPath = $path
    $Shortcut.Save()
    ```

- Create a shortcut in _Startup_
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

# Symbolic links

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


---
Sources:
- 2022-04-25: [Create a desktop shortcut with Windows Script Host - Windows Client - Microsoft Docs](https://docs.microsoft.com/en-us/troubleshoot/windows-client/admin-development/create-desktop-shortcut-with-wsh)

Related:
[Interact with the File System](Interact%20with%20the%20File%20System.md)

Tags:
