---
dg-publish: false
example: 
command: 
priority: 
---

- **Resolve** path for **existing** files or folders
    ```powershell
    Resolve-Path $file
    ```

- **Resolve** path files and folders that might **not exist**
    ```powershell
    $ExecutionContext.SessionState.Path.GetUnresolvedProviderPathFromPSPath($file)
    ```


---


Sources:
- 2022-04-25: [PowerShell- Running Executables - TechNet Articles - United States (English) - TechNet Wiki](https://social.technet.microsoft.com/wiki/contents/articles/7703.powershell-running-executables.aspx)

Related:

Tags:
[[Operate on the file system]]