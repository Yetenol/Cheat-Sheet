<h1> Getting Started </h1>

[⌂](../../README.md) › [PowerShell](../../README.md#powershell) ›

Table of Contents
- **[Data Types ›](data-types.md)**  
    Hashtable | `[DateTime]::Now`
- **[Modify data ›](modify.md)**  
    Add calculated property | `$list[	(0..1;-3..-1)]`
- **[Bash equivalents ›](bash-equivalents.md)**  
    While Loop | `read name` <-> `$name = Read-Host -Prompt "Name"`
- [Make executable](#make-executable)
- [Help yourself](#help-yourself)
- [Parameter AutoComplete](#parameter-autocomplete)
- [Apps in PATH locations](#apps-in-path-locations)

## Make executable
Make a PowerShell script a standalone executable script by  
pasting the following snippets at the beginning of a script and by  
adding `.bat` to the file extension like `script.ps1.bat`  
Script cannot be started relatively like `modules\script.ps1.bat`  
This bypasses the _Execution Policy_ for PowerShell scripts.

- **Make** script executable  
    ```cmd
    # & cls & powershell -Command "Invoke-Command -ScriptBlock ([ScriptBlock]::Create(((Get-Content """%0""") -join """`n""")))" & exit
    # Script is executable when renamed *.cmd or *.bat
    ```
- **Make** script executable and **persistent**
    ```cmd
    # & cls & powershell -NoExit -Command "Invoke-Command -ScriptBlock ([ScriptBlock]::Create(((Get-Content """%0""") -join """`n""")))" & exit
    # Script is executable and persistent when renamed *.cmd or *.bat
    ```

- **Make** script executable and **self-elevating**  
    ```cmd
    # & cls & powershell -Command Start-Process wt -Verb RunAs -ArgumentList """PowerShell.exe -Command Invoke-Command -ScriptBlock ([ScriptBlock]::Create(((Get-Content %0) -join [Environment]::NewLine)))""" & exit
    # Script is executable and self-elevating when renamed *.cmd or *.bat
    ```
- **Make** script executable, **self-elevating** and **persistent**
    ```cmd
    # & cls & powershell -Command Start-Process wt -Verb RunAs -ArgumentList """PowerShell.exe -NoExit -Command Invoke-Command -ScriptBlock ([ScriptBlock]::Create(((Get-Content %0) -join [Environment]::NewLine)))""" & exit
    # Script is executable, self-elevating and persistent when renamed *.cmd or *.bat
    ```

## Help yourself

- **Update help** files by  
	running as Administrator
    ```powershell
    Update-Help
    ```

- Discover **available commands**
	```powershell
	Get-Command | where {$_.Name -Match "vpn"}
	```
	> Dirty version:  
	> `gcm | where Name -Match "vpn"`


- Show **syntax**
	```powershell
	(Get-Process -?).syntax
	```

- Open **help page** in browser
	```powershell
	Get-Help Get-Process -Online
	```
	> Dirty version:  
	> `help Get-Process -Online`


## Parameter AutoComplete

- **Valide a parameter** to a specific list of option  
    Define a list of possibilities. This enables AutoComplete as well.

    ```powershell
    function Show-Hello {
        param (
            [ValidateSet("World", "Galaxy", "Universe")]
            [String]$noun
        )
        $greetingString = "Hello, " + $noun + "!"
        Write-Host "`t=>`t" $greetingString "`t<="
    }
    ```

## Apps in PATH locations

- List **all applications** in the **PATH** locations
    ```powershell
    $paths = [String[]] @($env:path -split ";") 
    $paths = $paths[0..($paths.Length-2)]
    $paths = $paths.ForEach({"$_\*"})
    Get-ChildItem -Path $paths -Include *.exe, *.msc `
        | Select -Property `
        @{Label="Type"; Expression={($_.Extension.toUpper() -replace "\`.","")}}, `
        @{Label="Command"; Expression={($_.Name -replace ".exe", "")}}, `
        @{Label="Description"; Expression={[System.Diagnostics.FileVersionInfo]::GetVersionInfo($_).FileDescription}}, `
        @{Label="Version"; Expression={[System.Diagnostics.FileVersionInfo]::GetVersionInfo($_).FileVersion}}, `
        @{Label="Size|KB"; Expression={[math]::Round($_.Length / 1KB)}}, `
        @{Label="Location"; Expression={$_.Directory}} `
        | Sort-Object -Property `
        @{Expression="Location"; Descending=$False}, `
        @{Expression="Extension"; Descending=$True}, `
        @{Expression="Description"; Descending=$False} `
        | Export-Csv -Path "$env:temp\path-apps.csv" -NoType -Delimiter ";"
    start "$env:temp\path-apps.csv"
    ```