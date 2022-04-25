# [⌂](../README.md) › [PowerShell](../README.md#powershell) › Web


## Download a file

```powershell
$env:Downloads = (New-Object -ComObject Shell.Application).NameSpace('shell:::{374DE290-123F-4565-9164-39C4925E467B}').Self.Path
if (-not $env:Downloads) {throw "Cannot find Downloads folder!"}

$url = "https://newsfeed.zeit.de"
$file = "$env:Downloads\Zeit RSS.xml"
Invoke-WebRequest -Uri $url -OutFile $file -ErrorAction Stop

explorer "/select,""$(Get-Item -Path $file)""" # show file
```

## Download a file into %TEMP%

```powershell
$url = "https://newsfeed.zeit.de"
$file = "$env:Temp\Zeit RSS.xml"
Invoke-WebRequest -Uri $url -OutFile $file -ErrorAction Stop

explorer "/select,""$(Get-Item -Path $file)""" # show file
```


## Download and unzip an archive

```powershell
$env:Downloads = (New-Object -ComObject Shell.Application).NameSpace('shell:::{374DE290-123F-4565-9164-39C4925E467B}').Self.Path
if (-not $env:Downloads) {throw "Cannot find Downloads folder!"}

$url = "https://www.autohotkey.com/download/ahk-v2.zip"
$folder = "$env:Downloads\AutoHotkey 2"
$archive = "$folder.zip"
Invoke-WebRequest -Uri $url -OutFile $archive -ErrorAction Stop

Remove-Item -Path $folder -Recurse -ErrorAction SilentlyContinue
Expand-Archive -Path $archive -DestinationPath $folder -Force

explorer $folder # show folder
```
