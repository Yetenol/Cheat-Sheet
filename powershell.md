# Powershell Cheat Sheet

# Help yourself

## Find the right cmdlet
```powershell
Get-Command | Where-Object -Property Name -Match "vpn"
```

## Help-Files
Update Help Files (Run as admin)
```powershell
Update-Help
```

## Get syntax help
```powershell
(Get-Process -?).syntax
```

Browser help page
```powershell
help Get-Process -online
```

Specific parameter help
```powershell
help Get-Process -Parameter Id
```

# Analyse an object / output
```powershell
Get-ChildItem | Get-Member -MemberType Property
```
## Display output / export to Microsoft Excel
```powershell
Get-ChildItem | Export-Csv -File .\table.csv -NoTypeInformation -Delimiter ";"
.\table.csv
```
> DIRTY CODE: `Get-ChildItem | Export-Csv .\table.csv -NoType -Delimiter ";"`



# Variables - Common data types
Examples | .GetType()-Names
--- | ---
42 | Integers (Convert automatically to larger types) <br> <b>Int32, Int (32-bit signed integer)</b> <br> Int64, Long (64-bit signed integer)
3.65 | Decimal numbers <br> <b>Double (Double-precision 64-bit floating point number)</b> <br> Single, Float (Single-precision 32-bit floating point number)
$True <br> $False | <b>Boolean</b>
"Hello" <br> 'Raw &%\Text' <br> "$env:temp\Trash" <br> "Hi " + $a + "!`n"| Text or single characters <br> <b>String (Fixed-length string of Unicode characters)</b> <br> Char (A Unicode 16-bit character)
[DateTime]::Now <br> [DateTime]::UtcNow <br> [DateTime]"1999-12-31" <br> [DateTime]"23:45:33" <br> [DateTime]"1.1.07 12:30" | Timestamp as date and time <br> <b>DateTime</b>
@(1; 2; 3; 7) <br> @(1..3; 7) <br> @('I'; 'am'; "here") | <b>Object[], Array</b>
@{X=12; Y=45; N="Karl"} | Dictionary of key/value pairs <br> <b>Hashtable</b>
[ordered]@{X=12; Y=45} | Ordered dictionary of key/value pairs <br> <b>OrderedDictionary</b>


# Get user input

### Enter plaintext input in console
```powershell
$User = Get-Host "Username"
```

### Get plaintext input from file at specific line
TotalCount speeds up the commands by only loading the first 26 lines.
```powershell
$Line26 = (Get-Content -Path <#File#>)[25]
```

```powershell
$Line26 = (Get-Content -Path <#File#> -TotalCount 26)[25]
```

Get first line starting with <i>User</i>
```powershell
$Lines_User = Get-Content -Path <#File#> -ReadCount 1000 # Load in shunks of 1k lines
  | foreach {$_ -match "^User"} # ^: Beginning of line (regex)
$Lines_User[0]                  # Only use first line
```

Get first line with <i>User: \<username\> </i>
```powershell
# LineFormat =   ···Username:···theo···Password:···turles1987·· 
$regexFormat = "^\s*Username:\s*(.*)\s*Password:\s*(?<pwd>.*)\s*$"
# ^: Start of line      $: End of line      \s*: Whitespace
# (.*) Unnamed entry    (?<pwd>.*) Named entry called pwd

$validLines = Get-Content -Path <#File#>text.txt -ReadCount 1000 `
  | foreach {$_ -match $regexFormat}

if($validLines.Count -le 0) {
  Write-Host -Object "No entries found!"
} elseif($validLines.Count -eq 1) {
  # Use this code if you only want one entry
  $regex = [RegEx]::Match($validLines[0], $regexFormat) # Only use first entry
  $Username = $regex.Groups[1].value
  $Password = $regex.Groups["pwd"].value
  Write-Output -InputObject @("Successfully extracted:", $Username, $Password)
} else {
  # Use this code if you want multiple entries
  $credentials = @{}
  foreach ($line in $validLines) {
    $regex = [RegEx]::Match($line, $regexFormat) # Only use first entry
    $Username = $regex.Groups[1].value
    $Password = $regex.Groups["pwd"].value
    $credentials[$Username] = $Password
  }
  Write-Host -Object "Successfully extracted:"
  Write-Output -InputObject $credentials
}
```


# Get sensitive input
<b> Don't save passwords as plain text </b> <br>
Instead save them as a secure string and encrypt them locally.

## Enter sensitive input in console
```powershell
$Secure = Read-Host "Password" -AsSecureString
```

## Decrypt locally
Only the <b>SAME INSTANCE</b> can decrypt. The last line prevents memory leaks.
```powershell
$bstr = [System.Runtime.InteropServices.Marshal]::SecureStringToBSTR($Secure)
$Plaintext [System.Runtime.InteropServices.Marshal]::PtrToStringAuto($bstr)
[System.Runtime.InteropServices.Marshal]::ZeroFreeBSTR($bstr)
```

## Save / export to file
The data is encrypted using the Windows Data Protection API (DPAPI). <br>
Only the <b>SAME USER ON THE SAME MASHINE</b> can decrypt.
```powershell
$Secure = Read-Host "Password" -AsSecureString
ConvertFrom-SecureString $Secure | Out-File "${Env:AppData}\Credential.bin"
```

## Import from file
Only the <b>SAME USER ON THE SAME MASHINE</b> can decrypt.
```powershell
$Secure = Get-Content "${Env:AppData}\Sec.bin" | ConvertTo-SecureString
```

## Ask a question once / until answered
```powershell
do {
  $Choice = Read-Host -Prompt "=== Select from: ===`n0 blue`ny yellow`n"
  switch ($Choice) {
    0 {
      Write-Host -Object "Painting in blue"
      break
    } 
    "y" {
      Write-Host -Object "Painting in yellow"
      return
    }
    default {
      $Choice = $null
      Write-Host -Object "=== Invalid choice! ==="
      break
    }
  }
} while ($Choice -eq $null)
```

## Ask a question repeatedly until canceled
```powershell
while ($true) {
  $Choice = Read-Host -Prompt "=== Select from: ===`n0  Sleep`n9+ Shutdown in _s`nq  Quit`n"
  $n = -1 # Choice parsed to number
  switch ($Choice) {
    0 {
      Write-Host -Object "Falling asleep"
      break
    } 
    {<#isNumber#>[double]::TryParse($_,[ref]$n) -and <# >8 #>($n -gt 8)} {
      Write-Host -Object @("Shutdown in", [math]::floor($_), "seconds")
      break
    }
    "q" {
      Write-Host -Object "=== Quit ==="
      return
    }
    default {
      $Choice = $null
      Write-Host -Object "=== Invalid choice! ==="
      break
    }
  }
}
```

## Function: Set parameter AutoComplete

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






# Tables
## Display table
```powershell
Get-ChildItem | Format-Table -Property Name, Length
```
> DIRTY CODE: `dir | ft Name, Length`

## Export object as table to Microsoft Excel
```powershell
Get-Process | Export-Csv -Path <#File#>table.csv -NoTypeInformation -Delimiter ";"
```
> DIRTY CODE: `Get-Process | Export-Csv <#File#>table.csv -NoType -Delimiter ";"`


## Rename table columns
```powershell
Get-ChildItem | Format-Table -Property Name, `
@{Label="Size|Byte"; Expression={$_.Length}}
```

## Custom table columns
```powershell
Get-ChildItem | Format-Table -Property Name, `
@{Label="Size|KB"; Expression={[math]::Round($_.Length / 1KB, 2)}}
```
## Interesting information
```powershell
Get-ChildItem -Path $env:SystemRoot\* -Include *.exe, *.dll | Format-Table -Property `
  BaseName, Extension, `
  @{Label="Description"; Expression={[System.Diagnostics.FileVersionInfo]::GetVersionInfo($_).FileDescription}}, `
  @{Label="Version"; Expression={[System.Diagnostics.FileVersionInfo]::GetVersionInfo($_).FileVersion}}
```

## Get path apps
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

# Random stuff

## Open location in Windows Explorer
```powershell
Invote-Item -Path .
```
> DIRTY CODE: `ii .`

## Create empty file
```powershell
Out-File -FilePath <#File>
```
> DIRTY CODE: Out-File <#File#>

## Open Powershell from Windows Explorer
Press `Shift + Right click` and select `Open Powershell window here`

Read further
- [Invoke command, item or strings](https://social.technet.microsoft.com/wiki/contents/articles/7703.powershell-running-executables.aspx)