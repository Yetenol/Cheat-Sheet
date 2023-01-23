---
dg-publish: true
example: Download and extract ZIP containers
command: 
---

# Download files

Example web content
```powershell
$url = "https://newsfeed.zeit.de"
$filename = "example.xml"
```

- **download and reveal** a file to _Downloads_  
    _Downloads_ is a [[Retrieve and modify user folder locations|user-specific folder]]. 
    Aborts on failure or reveals in _File Explorer_.
    ```powershell
    $env:Downloads = (New-Object -ComObject Shell.Application).NameSpace('shell:::{374DE290-123F-4565-9164-39C4925E467B}').Self.Path
    if (-not $env:Downloads) {throw "Cannot find Downloads folder!"}
    $path = "$env:Downloads\$filename"
    
    # download and reveal file
    Invoke-WebRequest -Uri $url -OutFile $path -ErrorAction Stop
    explorer "/select,`"$(Resolve-Path $path)`""
    ```

- **download** a file to a **specific location**  
    Create destination if it does not exist yet.
    ```powershell
    $path = ".\$filename"
    New-Item -Path $path -Force -ErrorAction Stop
    Invoke-WebRequest -Uri $url -OutFile $path -ErrorAction Stop
    ```

- **download** a file to _Temp_  
    _Temp_ is a [[Retrieve and modify user folder locations|common-user folder]]. 
    Aborts on failure.
    ```powershell
    $path = "$env:Temp\$filename"
    Invoke-WebRequest -Uri $url -OutFile $path -ErrorAction Stop
    ```
- **reveal** in _File Explorer_
    ```powershell
    explorer "/select,`"$(Resolve-Path $path)`""
    ```


## Extract zip archive

Example web archive
```powershell
$url = "https://www.autohotkey.com/download/ahk-v2.zip"
$foldername = "AutoHotkey 2"
```

- **download and extract** an **archive** to _Downloads_  
    _Downloads_ is a [[Retrieve and modify user folder locations|user-specific folder]]. 
    Aborts on failure or reveals in _File Explorer_.
    ```powershell
    $env:Downloads = (New-Object -ComObject Shell.Application).NameSpace('shell:::{374DE290-123F-4565-9164-39C4925E467B}').Self.Path
    if (-not $env:Downloads) {throw "Cannot find Downloads folder!"}
    $archive = "$env:Downloads\$foldername.zip"
    $folder = "$env:Downloads\$foldername"

    # download, extract and reveal archive
    Invoke-WebRequest -Uri $url -OutFile $archive -ErrorAction Stop
    Expand-Archive -Path $archive -DestinationPath $folder -Force -ErrorAction Stop
    Invoke-Item -Path $folder
    ```

# Execute web script

Example web script
```powershell
$url = "https://raw.githubusercontent.com/Yetenol/Setup-Computer/main/script/test.ps1.bat"
```

- **execute** remote script  
    Download script and run in current console.
    ```powershell
    Invoke-Command -ScriptBlock ([ScriptBlock]::Create((Invoke-WebRequest -Uri $url)))
    ```

- **execute** remote script **elevated**  
    Download script and run in new elevated console.
    ```powershell
    $command = "Invoke-Command -ScriptBlock ([ScriptBlock]::Create((Invoke-WebRequest -Uri $url)))"
    Start-Process wt -Verb RunAs -ArgumentList "PowerShell.exe -NoExit -Command $command"
    ```


---
#obsidian/improveSectioning 

Sources:

Related:

Tags:
[[Operate on the file system]]