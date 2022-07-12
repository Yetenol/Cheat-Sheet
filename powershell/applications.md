<h1> Applications </h1>

[⌂](../README.md) › [PowerShell](../README.md#powershell) ›

## Update all Microsoft Store apps

```powershell
$namespaceName = "root\cimv2\mdm\dmmap"
$className = "MDM_EnterpriseModernAppManagement_AppManagement01"
$wmiObj = Get-WmiObject -Namespace $namespaceName -Class $className
$result = $wmiObj.UpdateScanMethod()
```


## Upgrade all winget apps

```powershell
winget upgrade --all
```