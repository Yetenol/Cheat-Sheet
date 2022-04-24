# [⌂](../README.md) › [PowerShell](../README.md#powershell) › Web


## Download a file

```powershell
$myDownloads = (New-Object -ComObject Shell.Application).NameSpace('shell:::{374DE290-123F-4565-9164-39C4925E467B}').Self.Path
if (-not $myDownloads) {throw "Cannot find Downloads folder!"}

$url = "https://newsfeed.zeit.de"
$file = "$myDownloads\Zeit RSS.xml"
Invoke-WebRequest $url -OutFile $file -ErrorAction Stop
```

## Download a file into %TEMP%

```powershell
$url = "https://newsfeed.zeit.de"
$file = "$env:Temp\Zeit RSS.xml"
Invoke-WebRequest $url -OutFile $file -ErrorAction Stop
```


## Download and unzip an archive

```powershell
$myDownloads = (New-Object -ComObject Shell.Application).NameSpace('shell:::{374DE290-123F-4565-9164-39C4925E467B}').Self.Path
if (-not $myDownloads) {throw "Cannot find Downloads folder!"}

$url = "https://www.autohotkey.com/download/ahk-v2.zip"
$folder = "$myDownloads\AutoHotkey 2"
$archive = "$folder.zip"
Invoke-WebRequest $url -OutFile $archive -ErrorAction Stop

Remove-Item -Path $folder -Recurse -ErrorAction SilentlyContinue
Expand-Archive -Path $archive -DestinationPath $folder -Force
```
