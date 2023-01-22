---
dg-publish: false
example: Run as Administrator
command: 'Out-File -FilePath $file'
---

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


---


Sources:
- 2022-04-25: [windows - How to create a Run As Administrator shortcut using Powershell - Stack Overflow](https://stackoverflow.com/questions/28997799/how-to-create-a-run-as-administrator-shortcut-using-powershell)

Related:

Tags:
[Operate on the file system](Operate%20on%20the%20file%20system.md)