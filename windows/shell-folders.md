# [⌂](../README.md) › [Windows](../README.md#windows) › Shell Folders

## List per-user folders

```powershell
Get-ItemProperty "HKCU:\SOFTWARE\Microsoft\Windows\CurrentVersion\Explorer\User Shell Folders" | select * -Exclude "PS*"
```

## List per-system folders

```powershell
Get-ItemProperty "HKLM:\SOFTWARE\Microsoft\Windows\CurrentVersion\Explorer\User Shell Folders" | select * -Exclude "PS*"
```

## Current User Folders

- Value type: REG_EXPAND_SZ

| Shell Folder Name - Description                           | Default location                                                              |
| --------------------------------------------------------- | ----------------------------------------------------------------------------- |
| `AppData`                                                 | `%USERPROFILE%\AppData\Roaming`                                               |
| `Cache` <br> _Internet Explorer Cache_                    | `%USERPROFILE%\AppData\Local\Microsoft\Windows\INetCache`                     |
| `Cookies` <br> _Internet Explorer Cookies_                | `%USERPROFILE%\AppData\Local\Microsoft\Windows\INetCookies`                   |
| `Desktop`                                                 | `%USERPROFILE%\Desktop`                                                       |
| `Favorites`                                               | `%USERPROFILE%\Favorites`                                                     |
| `History`                                                 | `%USERPROFILE%\AppData\Local\Microsoft\Windows\History`                       |
| `Local AppData`                                           | `%USERPROFILE%\AppData\Local`                                                 |
| `My Music`                                                | `%USERPROFILE%\Music`                                                         |
| `My Pictures`                                             | `%USERPROFILE%\Pictures`                                                      |
| `My Video`                                                | `%USERPROFILE%\Videos`                                                        |
| `NetHood` <br> _Network Shortcuts_                        | `%USERPROFILE%\AppData\Roaming\Microsoft\Windows\Network Shortcuts`           |
| `Personal`                                                | `%USERPROFILE%\Documents`                                                     |
| `PrintHood`                                               | `%USERPROFILE%\AppData\Roaming\Microsoft\Windows\Printer Shortcuts`           |
| `Programs`                                                | `%USERPROFILE%\AppData\Roaming\Microsoft\Windows\Start Menu\Programs`         |
| `Recent`                                                  | `%USERPROFILE%\AppData\Roaming\Microsoft\Windows\Recent`                      |
| `SendTo`                                                  | `%USERPROFILE%\AppData\Roaming\Microsoft\Windows\SendTo`                      |
| `Start Menu`                                              | `%USERPROFILE%\AppData\Roaming\Microsoft\Windows\Start Menu`                  |
| `Startup`                                                 | `%USERPROFILE%\AppData\Roaming\Microsoft\Windows\Start Menu\Programs\Startup` |
| `Templates`                                               | `%USERPROFILE%\AppData\Roaming\Microsoft\Windows\Templates`                   |
| `{374DE290-123F-4565-9164-39C4925E467B}` <br> _Downloads_ | `%USERPROFILE%\Downloads`                                                     |

## Cloud Synchronization Folders

The following items do not exist in a clean install of Windows 10 and Windows 11. They’re created only if you redirect those folders to Microsoft OneDrive or DropBox. If the following values exist, the location defined in the following values takes precedence. In case of any conflict, the following values can be deleted so that the defaults (above) are used.

| Description     | Shell Folder Name                        |
| --------------- | ---------------------------------------- |
| Cloud Root      | `{A52BBA46-E9E1-435F-B3D9-28DAA648C0F6}` |
| Saved Pictures  | `{3B193882-D3AD-4EAB-965A-69829D1FB59F}` |
| Camera Roll     | `{AB5FB87B-7CE2-4F83-915D-550846C9537B}` |
| Screenshots     | `{B7BEDE81-DF94-4682-A7D8-57A52620B86F}` |
| Local Documents | `{F42EE2D3-909F-4907-8871-4C22FC0BF756}` |
| Local Downloads | `{7D83EE9B-2244-4E70-B1F5-5393042AF1E4}` |
| Local Music     | `{A0C69A99-21C8-4671-8703-7934162FCF1D}` |
| Local Pictures  | `{0DDD015D-B06C-45D5-8C4C-F59713854639}` |
| Local Videos    | `{35286A68-3C57-41A1-BBB1-0EAE73D76C95}` |

## Local Machine Folders

- Value type: REG_EXPAND_SZ

| Shell Folder Name - Description                                  | Default location                                              |
| ---------------------------------------------------------------- | ------------------------------------------------------------- |
| `{3D644C9B-1FB8-4f30-9B45-F670235F79C0}` <br> _Common Downloads_ | `%PUBLIC%\Downloads`                                          |
| `Common AppData`                                                 | `%ProgramData%`                                               |
| `Common Desktop`                                                 | `%PUBLIC%\Desktop`                                            |
| `Common Documents`                                               | `%PUBLIC%\Documents`                                          |
| `Common Programs`                                                | `%ProgramData%\Microsoft\Windows\Start Menu\Programs`         |
| `Common Start Menu`                                              | `%ProgramData%\Microsoft\Windows\Start Menu`                  |
| `Common Startup`                                                 | `%ProgramData%\Microsoft\Windows\Start Menu\Programs\Startup` |
| `Common Templates`                                               | `%ProgramData%\Microsoft\Windows\Templates`                   |
| `CommonMusic`                                                    | `%PUBLIC%\Music`                                              |
| `CommonPictures`                                                 | `%PUBLIC%\Pictures`                                           |
| `CommonVideo`                                                    | `%PUBLIC%\Videos`                                             |



## Sources

- 2022-04-23: [Windows 10-11 User Shell Folders Restore Default Paths » Winhelponline](https://www.winhelponline.com/blog/windows-10-shell-folders-paths-defaults-restore/)