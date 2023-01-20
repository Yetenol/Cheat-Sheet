# Registry roots

| Drive | Root                            |
| ---------- | ------------------------------- |
| `HKCU:\`   | `Registry::HKEY_CURRENT_USER\`  |
| `HKLM:\`   | `Registry::HKEY_LOCAL_MACHINE\` |
| `HKCR:\`¹⁾ | `Registry::HKEY_CLASSES_ROOT\`               |

- ¹⁾provide `HKCR:` drive    
    ```powershell
    New-PSDrive -PSProvider registry -Root HKEY_CLASSES_ROOT -Name HKCR
    ```

# Modify keys

The registry consist out of nested keys and their entires.

- list **entries**    
    ```powershell
    $key = "HKLM:\SOFTWARE\Microsoft\Windows\CurrentVersion"
    Get-ItemProperty -Path $key
    ```

- **get** entry    
    ```powershell
    $key = "HKLM:\SOFTWARE\Microsoft\Windows\CurrentVersion"
    Get-ItemProperty -Path $key -Name DevicePath
    ```

- **write** entry    
    ```powershell
    $key = "HKLM:\SOFTWARE\Microsoft\Windows\CurrentVersion"
    "test" | Set-ItemProperty -Path $key -Name DevicePath -Value $_
    ```

---
Sources:
- 2022-12-18: [Working with registry entries - PowerShell - Microsoft Learn](https://learn.microsoft.com/en-us/powershell/scripting/samples/working-with-registry-entries?view=powershell-7.3)

Related:

Tags:
[Windows](../Windows.md)