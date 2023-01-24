---
dg-publish: false
example: [ CSV Tables, Plaintext files ]
command: 'Export-Csv -Delimiter "," -NoTypeInformation -Path ".\text.csv"'
---

Example content
```powershell
$c = Get-Command
```

# Visualize

Split output into console-sized **pages**
```powershell
$c | more
```

Launch table **GUI**
```powershell
$c | Out-GridView
```

Show plaintext **table**  
```powershell
$c | Format-Table
```


# File export

Export **lossless** .NET object
```powershell
$c | Export-Clixml -Path "object.xml"
```

Export **spreadsheet table** separated by commas for programs like Excel.
```powershell
$c | Export-Csv -Delimiter "," -NoTypeInformation -Path ".\text.csv"
```

Export **plaintext table** seperated by spaces.
```powershell
$c | Format-Table -AutoSize -Wrap |
	Out-File -FilePath ".\text.txt"
```

Export **plaintext list** with each property on a new line.
```powershell
$c | Format-List |
	Out-File -FilePath ".\text.txt"
```

Export **encrypted standard string**  
```powershell
$c | ConvertTo-SecureString -AsPlainText -Force |
	ConvertFrom-SecureString |
	Out-File -FilePath ".\key.bin"
```


---
Sources:

Related:

Tags:
[[Handle objects]]