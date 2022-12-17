<h1> Export data </h1>

[⌂](../../README.md) › [PowerShell](../../README.md) › [FileSystem](File%20system.md) ›

Table of Contents
- [Visualize](#visualize)
- [File export](#file-export)

Example content
```powershell
$c = Get-Command
```

# Visualize

- **PAGES**:  
  Split output into console-sized pages
	```powershell
	$c | more
	```

- **GUI**:  
  Launch table GUI
	```powershell
	$c | Out-GridView
	```

- **PLAINTEXT TABLE**:  
  Show plaintext table
	> Discards object structure.
	```powershell
	$c | Format-Table
	```


# File export
- **XML object**  
  &#127775; Lossless (Keeps entire .NET object data)
	```powershell
	$c | Export-Clixml -Path "object.xml"
	```

- **Spreadsheet**  
  Can be displayed in programs like Excel.
	```powershell
	$c | Export-Csv -Delimiter "," -NoTypeInformation -Path ".\text.csv"
	```

- **Plaintext table**  
  Values are seperated by spaces.
	```powershell
	$c | Format-Table -AutoSize -Wrap |
		Out-File -FilePath ".\text.txt"
	```

- **Plaintext list**:  
  Each property appears on a new line.
	```powershell
	$c | Format-List |
		Out-File -FilePath ".\text.txt"
	```

- **Encrypted standard string**  
  read further [Encryption](../Encryption.md)
	```powershell
	$c | ConvertTo-SecureString -AsPlainText -Force |
		ConvertFrom-SecureString |
		Out-File -FilePath ".\key.bin"
	```