# [⌂] › (../README.md) [Powershell](../README.md#powershell) › Output Handling

- Knowledge requirements: [Pipeline](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_pipelines)

Everything in PowerShell is already or becomes a .NET object. Therefore, you should be familiar with how to handle and analyze them. Objects are easiest to visualize as text tables, but keep in mind that the entries themselves can also be objects.

- PowerShell modules return objects of a specific type
- external programs return an array of lines `Object[]`  (Array von Textzeilen) zurück.
1. Objekttyp und Eigenschaften analysieren
	```powershell
	| Get-Member
	```

# Visualisiere Ausgabe
1. ...als Seite-für-Seite Textansicht
	```powershell
	| more
	```
1. ...als GUI mit Tabellenformat
	```powershell
	| Out-GridView
	```
1. ...als reine Text-Tabelle
	- verwirft Objectstruktur
	```powershell
	| Format-Table
	```

# Ausgabe analysieren
1. Einträge / Zeilen zählen
	```powershell
	$o.Count
	```

# Eingabedatensatz eingrenzen
1. Einträge abzählen: Wähle die ersten 2 Einträge und die letzten 3
	```powershell
	| select -First 2 -Last 3
	```
1. Einträgespanne auswählen: Wähle den 5. bis 27. Eintrag
	```powershell
	$objects[5..27]
	```
1. Eine Bedingung
	```powershell
	| where {$_.BaseName -like "*anton*"}
	```
1. Verknüpfte Bedingungen
	``` powershell
	| where { `
		{ $_.Extension -like ".mkv" -or $_.Extension -like ".mp4" } `
		-and 
		$_.LastWriteTime -ge [DateTime]::"2000-12-31" `
	}
	```
# Spalten auswählen
1. Alle Spalten anzeigen
	```powershell
	| select -Property *
	```
1. (Mehrere) Spalten auswählen
	```powershell
	| select -Property BaseName, Extension
	```
1. Spalte umbenennen
	```powershell
	| select -Property `
		@{Label="Bytesize"; Expression={ $_.Length }}
1. Eigene Spalte erzeugen
	```powershell
	| select -Property `
		@{Label="Size in MB"; Expression={ $_.Length / 1GB}}
	```
# Sortieren
1. Nur aufsteigende Sortierung
	```powershell
	| sort -Property Extension, BaseName
	```
1. Sortierung
	```powershell
	| sort -Property `
		@{Expression="Length"; Descending=$True}, `
		Name
	```
# Exportieren
1. ...als XML-Objektdatei
	- **EMPFOHLEN**
	- **VERLUSTFREI** (behält gesamte `.NET`-Information)
	```powershell
	| Export-Clixml -Path "object.xml"
	```
1. ...als Excel-Tabelle
	```powershell
	| Export-Csv -Delimiter ";" -NoTypeInformation -Path ".\text.csv"
	```
1. ...als tabellarische Textdatei
	```powershell
	| Format-Table -AutoSize -Wrap `
	| Out-File -FilePath ".\text.txt
	```
1. ...als auflistende Textdatei
	```powershell
	| Format-List `
	| Out-File -FilePath ".\text.txt
	```
1. ...als verschlüsselte Textdatei
	- siehe [Verschlüsselung](encryption.md)
	```powershell
	| ConvertTo-SecureString -AsPlainText -Force `
	| ConvertFrom-SecureString `
	| Out-File -FilePath ".\key.bin"
	```
1. ...als sicherer Text
	```powershell
	| ConvertTo-SecureString -AsPlainText -Force
	```
___

# Interesting information
```powershell
Get-ChildItem -Path $env:SystemRoot\* -Include *.exe, *.dll | Format-Table -Property `
	BaseName, Extension, `
	@{Label="Description"; Expression={[System.Diagnostics.FileVersionInfo]::GetVersionInfo($_).FileDescription}}, `
	@{Label="Version"; Expression={[System.Diagnostics.FileVersionInfo]::GetVersionInfo($_).FileVersion}}
```