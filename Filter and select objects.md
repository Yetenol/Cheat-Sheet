---
dg-publish: true
example: Add calculated property
command: select -First 2 -Last 3
---

Everything in PowerShell is already or becomes a .NET object. Therefore, you should be familiar with how to handle and analyze them. Objects are easiest to visualize as text tables, but keep in mind that the entries themselves can also be objects.

- PowerShell modules return objects of a specific type
- external programs return an array of lines `Object[]`  (Array von Textzeilen) zurück.

An understanding of [pipelines](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_pipelines)is required. 

```powershell
$c = Get-Command
$f = Get-ChildItem
```


# Inspect result object

See object's [[Strongly type variables to ensure correct content and members|type]] and properties
```powershell
$c | Get-Member -MemberType Properties
```
- abbreviate dirty `| gm`

Count elements or file lines
```powershell
$c.Count
```

# Narrow down a result

Select **specific indexes**
```powershell
$c | select -Index 2, 4, 7 
```
```powershell
$c[2 + 4 + 7]
$c[@(2; 4; 7)]
```

Select a **range** at the beginning, end or with specific indexes at the beginning
```powershell
$c | select -First 2 -Last 3
```
```powershell
$c[0..1 + -3..-1]
$c[@(0..1; -3..-1)]
```

Select **duplicates** only once
```powershell
$c.Noun | select -Unique
```

Condition expression(s) to be selected
- Learn operators using: `Get-Help about_Comparison_Operators`
```powershell
$c | where {$_.Name -match "vpn"}
```
``` powershell
$f | where { `
    ( $_.Extension -eq ".xml" -or $_.Name -like "example*" ) `
    -and 
    $_.LastWriteTime -ge [DateTime]::"2000-12-31" `
}
```
- abbreviate dirty `$c | where Name -match "vpn"`


# Select specific members of a result

View all properties
```powershell
$c | select -Property *
```

Select properties
```powershell
$c | select -Property @("Verb"; "Noun")
```
- abbreviate dirty `$c | select Verb, Noun`

Add calculated property
```powershell
$f | select -Property @(
	"Name";
	@{Label="Size in MB"; Expression={  [Math]::Round($_.Length / 1MB, 2)  }};
)
```
```powershell
$f | % { Write-Output ([PSCustomObject]@{
	Name = $_.Name;
	"Size in MB" = [Math]::Round($_.Length / 1MB, 2);
})}
```

# Sort a result

Sort ascending / default direction
```powershell
$c | sort -Property @("Version"; "Name")
```
- abbreviate dirty `$c | sort Version, Name`

Specify sorting direction
```powershell
$c | sort -Property @(
	@{Expression="Version"; Descending=$True};
	"Name";
)
```


---
Sources:

Related:
[Pipelines](Pipelines),

Tags:
[[Handle objects]]