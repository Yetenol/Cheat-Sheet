# [⌂](../../README.md) › [PowerShell](../../README.md) › IO

### [Input ❯](input.md)
### [Output ❯](output.md)
### [Links ❯](links.md)
### [File attributes ❯](file-attributes.md)
### [Web ❯](web.md)

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



- 2022-04-25: [windows - How to create a Run As Administrator shortcut using Powershell - Stack Overflow](https://stackoverflow.com/questions/28997799/how-to-create-a-run-as-administrator-shortcut-using-powershell)
- 2022-04-25: [PowerShell- Running Executables - TechNet Articles - United States (English) - TechNet Wiki](https://social.technet.microsoft.com/wiki/contents/articles/7703.powershell-running-executables.aspx)