---
dg-publish: true
example: [ Recycle Bin, Downloads folder ]
command: 'shell:My Pictures'
priority: 1
---
```dynamic-embed
[[Map of Content]]
```

<ul class="dataview list-view-ul"><li><span><a aria-label-position="top" aria-label="Retrieve and modify user folder locations.md" data-href="Retrieve and modify user folder locations.md" href="Retrieve and modify user folder locations.md" class="internal-link" target="_blank" rel="noopener">Retrieve and modify user folder locations</a></span>: <ul class="dataview dataview-ul dataview-result-list-ul"><li class="dataview-result-list-li"><span>This PC, Desktop, Downloads</span></li><li class="dataview-result-list-li"><span><code>shell:My Pictures</code></span></li></ul></li><li><span><a aria-label-position="top" aria-label="Access panels and folders of Windows.md" data-href="Access panels and folders of Windows.md" href="Access panels and folders of Windows.md" class="internal-link" target="_blank" rel="noopener">Access panels and folders of Windows</a></span>: <ul class="dataview dataview-ul dataview-result-list-ul"><li class="dataview-result-list-li"><span>Recycle Bin</span></li><li class="dataview-result-list-li"><span><code>shell:::{}</code></span></li></ul></li><li><span><a aria-label-position="top" aria-label="See deprecated built-in panels and folders.md" data-href="See deprecated built-in panels and folders.md" href="See deprecated built-in panels and folders.md" class="internal-link" target="_blank" rel="noopener">See deprecated built-in panels and folders</a></span>: <ul class="dataview dataview-ul dataview-result-list-ul"><li class="dataview-result-list-li"><span>3D Objects, Cookies</span></li><li class="dataview-result-list-li"><span><code>shell:::{}</code></span></li></ul></li></ul>

# Import all user folders as environment variables

- define user folder macros
    ```powershell
    @{
        AppData = 'AppData'; IECache = 'Cache'; IECookies = 'Cookies'; Desktop = 'Desktop'; Favorites = 'Favorites'; History = 'History'; LocalAppData = 'Local AppData'; Music = 'My Music'; Pictures = 'My Pictures'; Videos = 'My Video'; Documents = 'Personal'; Downloads = '{374DE290-123F-4565-9164-39C4925E467B}'; NetworkShortcuts = 'NetHood'; PrinterShortcuts = 'PrintHood'; Programs = 'Programs'; Recent = 'Recent'; SendTo = 'SendTo'; StartMenu = 'Start Menu'; Startup = 'Startup'; Templates = 'Templates'; CloudRoot = '{A52BBA46-E9E1-435F-B3D9-28DAA648C0F6}';
        SavedPictures = '{3B193882-D3AD-4EAB-965A-69829D1FB59F}'; CameraRoll = '{AB5FB87B-7CE2-4F83-915D-550846C9537B}'; Screenshots = '{B7BEDE81-DF94-4682-A7D8-57A52620B86F}'; LocalDocuments = '{F42EE2D3-909F-4907-8871-4C22FC0BF756}'; LocalDownloads = '{7D83EE9B-2244-4E70-B1F5-5393042AF1E4}'; LocalMusic = '{A0C69A99-21C8-4671-8703-7934162FCF1D}'; LocalPictures = '{0DDD015D-B06C-45D5-8C4C-F59713854639}'; LocalVideos = '{35286A68-3C57-41A1-BBB1-0EAE73D76C95}';
        CommonDownloads = '{3D644C9B-1FB8-4f30-9B45-F670235F79C0}'; CommonAppData = 'Common AppData'; CommonDesktop = 'Common Desktop'; CommonDocuments = 'Common Documents'; CommonPrograms = 'Common Programs'; CommonStartMenu = 'Common Start Menu'; CommonStartup = 'Common Startup'; CommonTemplates = 'Common Templates'; CommonMusic = 'CommonMusic'; CommonPictures = 'CommonPictures'; CommonVideos = 'CommonVideo';
    } | 
    % GetEnumerator | 
    % { 
        $namespace = if ($_.Value -like '{*}') {"shell:::" + $_.Value} else {"shell:" + $_.Value}
        try { 
            [Environment]::SetEnvironmentVariable($_.Name, (New-Object -ComObject Shell.Application).NameSpace($namespace).Self.Path)
        } catch {}
    }
    ```

- reveal folder in *File Explorer*    
    ```powershell
    Invoke-Item -Path $env:Pictures
    ```

- list available macros
    ```powershell
    Get-ChildItem env:
    ```



---


Sources:
- 2022-04-24: [Known Folder GUIDs for File Dialog Custom Places - Windows Forms .NET Framework - Microsoft Docs](https://docs.microsoft.com/en-us/dotnet/desktop/winforms/controls/known-folder-guids-for-file-dialog-custom-places?view=netframeworkdesktop-4.8)

Related:

Tags:
[Windows](../Windows.md)