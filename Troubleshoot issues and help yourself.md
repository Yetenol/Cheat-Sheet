---
dg-publish: true
example: 
command: 
priority: 1
---
**Update help files** using elevated command
```powershell
Update-Help
```

# Discover commands

- Discover **all nouns** of PowerShell modules    
    ```powershell
    Get-Command -Module Microsoft.PowerShell* | group Noun | Format-Wide -AutoSize
    ```

- Discover **all commands** about a noun    
    ```powershell
    Get-Command -Noun Web* | foreach { Get-Help $_ } | Format-Table Name, Synopsis
    ```

- Discover **all modules**    
    ```powershell
    Get-Module
    ```
    ```powershell
    Get-Module -ListAvailable
    ```

# Access documentation

Example command:
```powershell
$help = Get-Help -Name Invoke-WebRequest
```

- Show help **online**    
    ```powershell
    Get-Help -Name Invoke-WebRequest -Online
    ```
    Dirty: `help Invoke-WebRequest -Online`

- Learn **syntax**    
    ```powershell
    $help.syntax
    ```
    Dirty: `(help Invoke-WebRequest).syntax` | `(Invoke-WebRequest -?).syntax`

- Learn **purpose**    
    ```powershell
    $help.Synopsis
    ```
    Dirty: `(help Invoke-WebRequest).Synopsis` | `(Invoke-WebRequest -?).Synopsis`

- Read **description**    
    ```powershell
    $help.description
    ```
    Dirty: `(help Invoke-WebRequest).description` | `(Invoke-WebRequest -?).description`  

- See **examples**    
    ```powershell
    $help.examples
    ```
    Dirty: `help Invoke-WebRequest -Examples` | `(Invoke-WebRequest -?).examples`  


---


Sources:

Related:

Tags:
[PowerShell](../PowerShell.md)