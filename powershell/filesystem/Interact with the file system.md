---
example: Run as administrator
command:
---

```dataview
TABLE
    example as "Topic example",
    ("`" + command + "`") as "Command example"
FROM "powershell/filesystem"
```
#obsidian/removeToc 
- **[Import ›](../Input%20information.md)**  
    extract data from files  
    parse using regular expressions  
- **[Export ›](Export%20to%20files%20or%20outputs.md)**  
    visualize date  
    export to different filetypes  
- **[Links ›](Create%20shortcuts%20and%20symbolic%20links.md)**  
    create shell, symbolic or hard links and junctions  
- **[Attributes](Read%20or%20write%20file%20system%20attributes.md)**  
    get, set and test file, folder attributes  
    set ReadOnly, Archived, OneDrive AlwaysOnDevice, ...  
- **[Meta data ›](../Get%20advanced%20file%20system%20meta%20data.md)**  
    get additional file metadata  
- **[Web ›](Download%20or%20invoke%20files%20from%20the%20internet.md)**  
    download files, archives  
- [Windows Explorer](#windows-explorer)
- [Resolve path for external programs](#resolve-path-for-external-programs)
- [File modification](#file-modification)
  - [Set _Run as Administrator_ flag](#set-run-as-administrator-flag)
- [File Information](#file-information)

Example content
```powershell
$file = ".\example.txt"
$tool = "$env:SystemRoot\System32\notepad.exe"
```

# Windows Explorer

- **Open current folder**
    ```powershell
    Invoke-Item -Path .
    ```
    ```powershell
    explorer (Resolve-Path .) # can only open one folder
    ```
    > Dirty version:  
    > `ii .`

- **Select** one **file** or **folder**
    ```powershell
    explorer "/select,`"$(Resolve-Path $file)`""
    ```

- **Copy** using _Windows Explorer_ UI  
    from `$source` to `$destination` with `$copyFlags`
	```powershell
	$objShell = New-Object -ComObject 'Shell.Application'    
	$objFolder = $objShell.NameSpace((Resolve-Path $destination).Path)
	$objFolder.CopyHere((Resolve-Path $source).Path, $copyFlags)
	```

    The `$copyFlags` are a bitwise combination of the following `vOptions` flags:

#obsidian/fixTable
    | Value                | Summary                | Description                                                                                                                    |
    | -------------------- | ---------------------- | ------------------------------------------------------------------------------------------------------------------------------ |
    | `0x0004` <br> = 4    | no UI                  | Do not display a progress dialog box.                                                                                          |
    | `0x0008` <br> = 8    | rename duplicates      | Give the file being operated on a new name in a move, copy, or rename operation if a file with the target name already exists. |
    | `0x0010` <br> = 16   | yes to all             | Respond with "Yes to All" for any dialog box that is displayed.                                                                |
    | `0x0040` <br> = 64   | allow undo             | Preserve undo information, if possible.                                                                                        |
    | `0x0080` <br> = 128  | require wildcard       | Perform the operation on files only if a wildcard file name like `*.*` is specified.                                           |
    | `0x0100` <br> = 256  | UI without filenames   | Display a progress dialog box but do not show the file names.                                                                  |
    | `0x0200` <br> = 512  | create directories     | Do not confirm the creation of a new directory if the operation requires one to be created.                                    |
    | `0x0400` <br> = 1024 | no error UI            | Do not display a user interface if an error occurs.                                                                            |
    | `0x0800` <br> = 2048 | no security attributes | Do not copy the security attributes of the file. (Version 4.71.)                                                               |
    | `0x1000` <br> = 4096 | no recursion           | Only operate in the local directory. Do not operate recursively into subdirectories.                                           |
    | `0x2000` <br> = 8192 | no file grouping       | Do not copy connected files as a group. Only copy the specified files. (Version 5.0.)                                          |
    
    - Example: **combine** _create directories_, _no error UI_ and _rename duplicates_
        ```powershell
        $copyFlags = 0x400 + 0x200 + 0x8
        ```
        ```powershell
        $copyFlags = 0x608
        ```

# Resolve path for external programs

- **Resolve** path for **existing** files or folders
    ```powershell
    Resolve-Path $file
    ```

- **Resolve** path files and folders that might **not exist**
    ```powershell
    $ExecutionContext.SessionState.Path.GetUnresolvedProviderPathFromPSPath($file)
    ```

# File modification

- Set 0 KB or create **empty file**
    ```powershell
    Out-File -FilePath $file
    ```
    > Dirty version:  
    > `Out-File $file`

## Set _Run as Administrator_ flag

The flag is stored in byte `0x15` (= 21) at bit `0x20` (= 6).

- **Enable** elevated execution
    ```powershell
    $bytes = [System.IO.File]::ReadAllBytes((Resolve-Path $file))
    $bytes[0x15] = $bytes[0x15] -bor 0x20 
    [System.IO.File]::WriteAllBytes((Resolve-Path $file), $bytes)
    ```

- **Disable** elevated execution
    ```powershell
    $bytes = [System.IO.File]::ReadAllBytes((Resolve-Path $file))
    $bytes[0x15] = $bytes[0x15] -bxor 0x20
    [System.IO.File]::WriteAllBytes((Resolve-Path $file), $bytes)
    ```


# File Information

- [Get **attributes**](Read%20or%20write%20file%20system%20attributes.md)
- [Get **meta data**](../Get%20advanced%20file%20system%20meta%20data.md)

- Get **version data** of Windows components
    ```powershell
    [System.Diagnostics.FileVersionInfo]::GetVersionInfo($tool) | select *
    ```



---


Sources:
- 2022-04-25: [windows - How to create a Run As Administrator shortcut using Powershell - Stack Overflow](https://stackoverflow.com/questions/28997799/how-to-create-a-run-as-administrator-shortcut-using-powershell)
- 2022-04-25: [PowerShell- Running Executables - TechNet Articles - United States (English) - TechNet Wiki](https://social.technet.microsoft.com/wiki/contents/articles/7703.powershell-running-executables.aspx)
- 2022-04-27: [Getting file metadata with PowerShell similar to what Windows Explorer provides - Evotec](https://evotec.xyz/getting-file-metadata-with-powershell-similar-to-what-windows-explorer-provides/)
- 2022-09-02: [Copying Files In PowerShell - Using Windows Explorer UI - BackSlasher](https://blog.backslasher.net/copying-files-in-powershell-using-windows-explorer-ui.html)
- 2022-09-02: [Folder.CopyHere method (Shldisp.h) - Win32 apps - Microsoft Docs](https://docs.microsoft.com/en-us/windows/win32/shell/folder-copyhere)

Related:

Tags: