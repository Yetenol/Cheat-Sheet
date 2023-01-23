---
storeId: 
wingetId: Overwolf.CurseForge
githubUser: 
githubRepo: 
githubBinary: 
website: https://download.curseforge.com/
priority: 10
---

# CurseForge

CurseForge is a modding platform for Minecraft, among others. Both vanilla and modded instances are launched via the official launcher, which is installed with CurseForge to be more compatible. CurseForge is primarily used to download and update mods.

- launch CurseForge and skip intro
- install Minecraft with *Standard* modding folder
- link remote config using elevated [script](../scripts/Sync-MinecraftJava.ps1)
  ```powershell
  $url = 'https://raw.githubusercontent.com/Yetenol/Setup-Computer/main/scripts/Sync-MinecraftJava.ps1'
  $command = "Invoke-Command -ScriptBlock ([ScriptBlock]::Create((Invoke-WebRequest -Uri $url)))"
  Start-Process wt -Verb RunAs -ArgumentList "PowerShell.exe -NoExit -Command $command"
  ```
    ```powershell
    Link-RemoteConfig `
    -cloudPath "D:\OneDrive\Gaming\Minecraft Java" `
    -localPath "$env:UserProfile\curseforge\minecraft\Install" `
    -syncItems @( '.\saves'; '.\resourcepacks'; '.\screenshots'; '.\config'; '.\shaderpacks'; '.\hotbar.nbt'; '.\options.txt'; '.\servers.dat' )
    ```
- add Minecraft shortcut to StartMenu
    ```powershell
    $installPath = "$env:UserProfile\curseforge\minecraft\Install"
    $installBin = "$installPath\minecraft.exe"
    $shortcutName = "Minecraft.lnk"
    
    $env:Startup = (New-Object -ComObject Shell.Application).NameSpace('shell:Startup').Self.Path
    $WshShell = New-Object -comObject WScript.Shell
    $Shortcut = $WshShell.CreateShortcut("$env:Startup\$shortcutName")
    $Shortcut.TargetPath = $installBin
    $Shortcut.WorkingDirectory = $installPath
    $Shortcut.Arguments = "--workDir=`"$installPath`""
    $Shortcut.Save()
    ```
- open Minecraft from Start Menu
- sign in and launch lastest release
- close Minecraft

## Usage

-  to **play** vanilla or modded Minecraft launch `Minecraft Launcher`  
-  to **manage modpacks** launch `CurseForge`  

# Modpacks

## Setup Vanilla Modpack

```dataview
TABLE WITHOUT ID
    "[" +
    choice(
        thumbnail,
        "<img src=\"" + thumbnail + "\" width=\"80\">",
        null
    ) + "](" +
    choice(
        modrinthId,
        "https://modrinth.com/mod/" + modrinthId,
        choice(
            curseForgeId,
            "https://www.curseforge.com/minecraft/mc-mods/" + curseForgeId,
            choice(
                edgeId,
                "https://microsoftedge.microsoft.com/addons/detail/" + edgeId,
                choice(
                    chromeId,
                    "https://chrome.google.com/webstore/detail/" + chromeId,
                    ""   
                )
            )
        )
    ) + ")"
    as "Website",
    file.link + " <br> " +
    choice(
        curseForgeId,
        "[![](https://img.shields.io/badge/CurseForge-install-blue)](" + 
        "https://www.curseforge.com/minecraft/mc-mods/" + curseForgeId + "/download?client=y" + ")",
        ""
    )
    as "Extension",
    Synopsis as "Synopsis"
FROM
    "apps" and [[]] and [[See extension]]
SORT
    choice(priority,priority,99)
```

- add **profile to vanilla launcher** using elevated [script](../scripts/Link-MinecraftFabric.ps1)
  ```powershell
  $url = 'https://raw.githubusercontent.com/Yetenol/Setup-Computer/main/scripts/Link-MinecraftFabric.ps1'
  $command = "Invoke-Command -ScriptBlock ([ScriptBlock]::Create((Invoke-WebRequest -Uri $url)))"
  Start-Process wt -Verb RunAs -ArgumentList "PowerShell.exe -NoExit -Command $command"
  ```

## Custom Modpacks

- **Import** a custom modpack (_optional_)  
  using a CurseForge export file
  - Click `Create Custom Profile`
  - Click `Import a previously created profile`
- **Add** a custom modpack (_optional_)  
  - Click `Create Custom Profile`
  - Enter a name and the version configuration
  - Right click profile and click `Open Folder`
  - Import and override all modpack files

## External editors

```dataview
LIST
    nonnull(list(
        choice(
            any(list(storeId,website,githubUser)),
            join(nonnull(list(
                choice(
                    any(storeId),
                    choice(
                        startswith(upper(storeId), "XP"),
                        "&#128279;",
                        elink("https://microsoft.com/store/apps/" + storeId, "Microsoft Store")
                    ),
                    null
                ),
                choice(
                    githubUser,
                    elink(
                        "https://github.com/" + githubUser + "/" + 
                        githubRepo + "/releases/latest" + 
                        choice(
                            githubBinary,
                            "/download/" + githubBinary,
                            ""
                        ),
                        "Github"
                    ),
                    null
                ),
                choice(
                    website,
                    elink(website, "Website"),
                    null
                )
            ))),
            null
        ),
        choice(
            storeId,
            "`winget install -e " + upper(storeId) + " --accept-package-agreements`",
            null
        ),
        choice(
            wingetId,
            "`winget install -e " + wingetId + "`",
            null
        )
    ))
FROM
    "apps" and [[]] and ![[See extension]]
SORT
    choice(priority,priority,99)
```



---


Sources:

Related:

Tags:
[Install games](../notes/Install%20games.md)