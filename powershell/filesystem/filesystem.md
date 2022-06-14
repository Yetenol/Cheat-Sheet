# FileSystem - Interactions
[⌂](../../README.md) › [PowerShell](../../README.md) ›

- **[Import ›](import.md)**  
    extract data from files  
    parse using regular expressions  

- **[Export ›](export.md)**  
    visualize date  
    export to different filetypes  

- **[Links ›](links.md)**  
    create shell, symbolic or hard links and junctions  

- **[Attributes ›](attributes.md)**  
    get, set and test file, folder attributes  
    set ReadOnly, Archived, OneDrive AlwaysOnDevice, ...  

- **[Meta data ›](metadata.md)**  
    get additional file metadata  

- **[Web ›](web.md)**  
    download files, archives  
----------

```powershell
$file = ".\example.txt"
$tool = "$env:SystemRoot\System32\notepad.exe"
```

# Windows Explorer

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


# File modification

## Set 0 KB or Create empty file

```powershell
Out-File -FilePath $file
```
> DIRTY CODE: `Out-File $file`


## Run as administrator

Flag is stored in byte `0x15` (= 21) at bit `0x20` (= 6).

- Enable elevated execution
    ```powershell
    $bytes = [System.IO.File]::ReadAllBytes((Resolve-Path $file))
    $bytes[0x15] = $bytes[0x15] -bor 0x20 
    [System.IO.File]::WriteAllBytes((Resolve-Path $file), $bytes)
    ```

- Disable elevated execution
    ```powershell
    $bytes = [System.IO.File]::ReadAllBytes((Resolve-Path $file))
    $bytes[0x15] = $bytes[0x15] -bxor 0x20
    [System.IO.File]::WriteAllBytes((Resolve-Path $file), $bytes)
    ```


# File Information

- [Get attributes](attributes.md)
- [Get meta data](metadata.md)

- Get version data of Windows components
    ```powershell
    [System.Diagnostics.FileVersionInfo]::GetVersionInfo($tool) | select *
    ```


# Sources

- 2022-04-25: [windows - How to create a Run As Administrator shortcut using Powershell - Stack Overflow](https://stackoverflow.com/questions/28997799/how-to-create-a-run-as-administrator-shortcut-using-powershell)
- 2022-04-25: [PowerShell- Running Executables - TechNet Articles - United States (English) - TechNet Wiki](https://social.technet.microsoft.com/wiki/contents/articles/7703.powershell-running-executables.aspx)
- 2022-04-27: [Getting file metadata with PowerShell similar to what Windows Explorer provides - Evotec](https://evotec.xyz/getting-file-metadata-with-powershell-similar-to-what-windows-explorer-provides/)