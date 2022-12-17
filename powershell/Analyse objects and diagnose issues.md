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