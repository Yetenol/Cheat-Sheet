# [⌂](../../README.md) › [PowerShell](../../README.md) › [IO](io.md) › Output Handling

- Knowledge requirements: [Pipeline](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_pipelines)

Everything in PowerShell is already or becomes a .NET object. Therefore, you should be familiar with how to handle and analyze them. Objects are easiest to visualize as text tables, but keep in mind that the entries themselves can also be objects.

- PowerShell modules return objects of a specific type
- external programs return an array of lines `Object[]`  (Array von Textzeilen) zurück.

```powershell
$c = Get-Command
$f = Get-ChildItem
```

# Diagnose
- See object type, properties
	```powershell
	$c | Get-Member -MemberType Properties
	```
	> DIRTY: `| gm`

- Count elements or file lines
	```powershell
	$c.Count
	```

# Visualize

- **PAGES**: Split output into console-sized pages
	```powershell
	$c | more
	```

- **GUI**: Launch table GUI
	```powershell
	$c | Out-GridView
	```

- **PLAINTEXT TABLE**: Show plaintext table
	> Discards object structure.
	```powershell
	$c | Format-Table
	```


# Limit data set

- **LIST**: Select the 2nd 4th and 7th item
	```powershell
	$c | select -Index 3, 4
	```
	```powershell
	$c[@(2;4;7)]
	```
	> DIRTY: `$c[2,4,7]`

- **RANGE**: Select the first 2 and the last 3 items
	```powershell
	$c | select -First 2 -Last 3
	```
	```powershell
	$c[@(0..1;-3..-1)]
	```
	> DIRTY: `$c[0..1+-3..-1]`

- **HIDE DUPLICATES**: If multiple items have equal values, display it only once.
	```powershell
	$c.Noun | select -Unique
	```

- **CONDITION**  
Learn operators: `Get-Help about_Comparison_Operators`

	```powershell
	$c | where {$_.Name -match "vpn"}
	```
	> DIRTY: `$c | where Name -match "vpn"`

	``` powershell
	$f | where { `
		( $_.Extension -eq ".xml" -or $_.Name -like "example*" ) `
		-and 
		$_.LastWriteTime -ge [DateTime]::"2000-12-31" `
	}
	```


# Properties (columns)

- All properties
	```powershell
	$c | select -Property *
	```
- Select properties
	```powershell
	$c | select -Property @("Verb"; "Noun")
	```
	> DIRTY: `$c | select Verb, Noun`
- Add custom property
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


# Sortieren
1. Nur aufsteigende Sortierung
	```powershell
	$c | sort -Property Extension, BaseName
	```
1. Sortierung
	```powershell
	$c | sort -Property `
		@{Expression="Length"; Descending=$True}, `
		Name
	```
# Exportieren
1. ...als XML-Objektdatei
	- **EMPFOHLEN**
	- **VERLUSTFREI** (behält gesamte `.NET`-Information)
	```powershell
	$c | Export-Clixml -Path "object.xml"
	```
1. ...als Excel-Tabelle
	```powershell
	$c | Export-Csv -Delimiter ";" -NoTypeInformation -Path ".\text.csv"
	```
1. ...als tabellarische Textdatei
	```powershell
	$c | Format-Table -AutoSize -Wrap `
	| Out-File -FilePath ".\text.txt"
	```
1. ...als auflistende Textdatei
	```powershell
	$c | Format-List `
	| Out-File -FilePath ".\text.txt"
	```
1. ...als verschlüsselte Textdatei
	- siehe [Verschlüsselung](encryption.md)
	```powershell
	$c | ConvertTo-SecureString -AsPlainText -Force `
	| ConvertFrom-SecureString `
	| Out-File -FilePath ".\key.bin"
	```
1. ...als sicherer Text
	```powershell
	$c | ConvertTo-SecureString -AsPlainText -Force
	```

___

# Interesting information
```powershell
Get-ChildItem -Path $env:SystemRoot\* -Include *.exe, *.dll | Format-Table -Property `
	BaseName, Extension, `
	@{Label="Description"; Expression={[System.Diagnostics.FileVersionInfo]::GetVersionInfo($_).FileDescription}}, `
	@{Label="Version"; Expression={[System.Diagnostics.FileVersionInfo]::GetVersionInfo($_).FileVersion}}
```