---
example: Update Store Apps
command: '$wmiObj.UpdateScanMethod()'
---

# Update all Microsoft Store apps

```powershell
$namespaceName = "root\cimv2\mdm\dmmap"
$className = "MDM_EnterpriseModernAppManagement_AppManagement01"
$wmiObj = Get-WmiObject -Namespace $namespaceName -Class $className
$result = $wmiObj.UpdateScanMethod()
```


# Upgrade all winget apps

```powershell
winget upgrade --all
```

# Update all git repositories

- [shortcutFox-gitUpdateAll.ps1](https://github.com/Yetenol/shortcutFox/blob/main/source/scripts/gitUpdateAll.ps1)


---


Sources:

Related:
[autohotkey](../autohotkey.md)

Tags:
[PowerShell](../PowerShell.md)