# [⌂](../README.md) › › Windows › Dll commands
- Dynamic Link Library (dll) components
- Control Panel tabs (cpl tab)

## Control Panel

| Command                                                                                                | Description                                                     |
| ------------------------------------------------------------------------------------------------------ | --------------------------------------------------------------- |
| Control Panel                                                                                          | `rundll32 Shell32.dll,Control_RunDLL`                           |
| Control Panel reload Applets                                                                           | `rundll32 shell32.dll,Control_FillCache_RunDLL`                 |
| Mouse Properties &#127775; <br> _(TrackPoint, TouchPad)_                                               | `rundll32 Shell32.dll,Control_RunDLL main.cpl,@0`               |
| Keyboard Properties                                                                                    | `rundll32 Shell32.dll,Control_RunDLL main.cpl,@1`               |
| Erleichterte Bedienung                                                                                 | `rundll32 shell32.dll,Control_RunDLL access.cpl`                |
| Programs                                                                                               | `appwiz.cpl`                                                    |
| ⠀⮱ Uninstall or change a program &#127775;                                                             | `rundll32 shell32.dll,Control_RunDLL appwiz.cpl,null,0`         |
| ⠀⮱ Install a program from the network                                                                  | `rundll32 shell32.dll,Control_RunDLL appwiz.cpl,null,1`         |
| ⠀⮱ Windows Features &#127775;                                                                          | `rundll32 shell32.dll,Control_RunDLL appwiz.cpl,null,2`         |
| Display (Settings App)                                                                                 | `desk.cpl`                                                      |
| ⠀⮱ Desktop Icon Settings &#127775;                                                                     | `rundll32 shell32.dll,Control_RunDLL desk.cpl,null,0`           |
| ⠀⮱ Screen Saver Settings                                                                               | `rundll32 shell32.dll,Control_RunDLL desk.cpl,null,1`           |
| ⠀⮱ Background (Settings App)                                                                           | `rundll32 shell32.dll,Control_RunDLL desk.cpl,null,2`           |
| Region                                                                                                 | `intl.cpl`                                                      |
| ⠀⮱ Formats &#127775;                                                                                   | `rundll32 shell32.dll,Control_RunDLL intl.cpl,null,0`           |
| ⠀⮱ Administrative                                                                                      | `rundll32 shell32.dll,Control_RunDLL intl.cpl,null,1`           |
| Game Controllers                                                                                       | `joy.cpl`                                                       |
| Sound                                                                                                  | `mmsys.cpl`                                                     |
| ⠀⮱ Playback &#127775;                                                                                  | `rundll32 shell32.dll,Control_RunDLL mmsys.cpl,null,0`          |
| ⠀⮱ Recording &#127775;                                                                                 | `rundll32 shell32.dll,Control_RunDLL mmsys.cpl,null,1`          |
| ⠀⮱ Sounds                                                                                              | `rundll32 shell32.dll,Control_RunDLL mmsys.cpl,null,2`          |
| System Properties                                                                                      | `sysdm.cpl`                                                     |
| ⠀⮱ Computer Name                                                                                       | `rundll32 shell32.dll,Control_RunDLL sysdm.cpl,null,1`          |
| ⠀⮱ Hardware                                                                                            | `rundll32 shell32.dll,Control_RunDLL sysdm.cpl,null,2`          |
| ⠀⮱ Advanced &#127775; <br> _(Performance, User Profiles, Startup and Recovery, Environment Variables)_ | `rundll32 shell32.dll,Control_RunDLL sysdm.cpl,null,3`          |
| ⠀⮱ System Protection &#127775; <br> _(Restore Point)_                                                  | `rundll32 shell32.dll,Control_RunDLL sysdm.cpl,null,4`          |
| Date and Time                                                                                          | `timedate.cpl`                                                  |
| ⠀⮱ Date and Time                                                                                       | `rundll32 shell32.dll,Control_RunDLL timedate.cpl,null,0`       |
| ⠀⮱ Additional Clocks                                                                                   | `rundll32 shell32.dll,Control_RunDLL timedate.cpl,null,1`       |
| Security and Maintenance                                                                               | `wscui.cpl`                                                     |
| ⠀⮱ Windows Sicherheitscenter                                                                           | `rundll32 shell32.dll,Control_RunDLL wscui.cpl,Security Center` |


## Other commands

| Command                                                                                                                                        | Description                                                                                     |
| ---------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------- |
| Installation aus INF-Files                                                                                                                     | `rundll32 advpack.dll,LaunchINFSection \<INF-Datei\>,\<Section\>`                               |
| Neue Verknüpfung anlegen &#127775;                                                                                                             | `rundll32 appwiz.cpl,NewLinkHere \<Verzeichnis\>`                                               |
| Screensaver installieren                                                                                                                       | `rundll32 desk.cpl,InstallScreenSaver \<saver.scr\>`                                            |
| Ruft Diskcopy auf                                                                                                                              | `rundll32 diskcopy.dll,DiskCopyRunDLL \<0 oder 1\>`                                             |
| Stored User Names and Passwords &#127775;                                                                                                      | `rundll32 keymgr.dll,KRShowKeyMgr`                                                              |
| Installation aus einer INF-Datei                                                                                                               | `rundll32 setupapi.dll,InstallHinfSection 132 \<.inf-Datei\>`                                   |
| Open with dialog                                                                                                                               | `rundll32 shell32.dll,OpenAs_RunDLL`                                                            |
| Open with dialog for a specific file &#127775;                                                                                                 | `rundll32 shell32.dll,OpenAs_RunDLL \<Datei\>`                                                  |
| About MZ/Windows <br> _(Version, OS Build)_                                                                                                    | `rundll32 Shell32.dll,ShellAboutA` <br> `winver`                                                |
| Add a printer dialog &#127775;                                                                                                                 | `rundll32 shell32.dll,SHHelpShortcuts_RunDLL AddPrinter`                                        |
| Printers Folder                                                                                                                                | `rundll32 shell32.dll,SHHelpShortcuts_RunDLL PrintersFolder <br> explorer shell:printersfolder` |
| Drucker direkt ohne Assistent hinzufügen &#127775; <br> _[Details](http://www.winfaq.de/faq_html/Content/tip2000/onlinefaq.php?h=tip2028.htm)_ | `rundll32 printui.dll,PrintUIEntry \<Optionen\> \<@Befehlsdatei\>`                              |
| z.B. Netzwerkdrucker hinzufügen                                                                                                                | `rundll32 printui.dll,PrintUIEntry /q /in /n \\\\ServerName\Freigabename`                       |
| Schriftarten anzeigen                                                                                                                          | `rundll32 shell32.dll,SHHelpShortcuts_RunDLL FontsFolder`                                       |
| Netzwerklaufwerk verbinden, Dialog öffnen                                                                                                      | `rundll32 shell32.dll,SHHelpShortcuts_RunDLL Connect`                                           |
| Telnet-Verbindung öffnen                                                                                                                       | `rundll32 url.dll,TelnetProtocolHandler \<IP-Adresse bzw. Hostname\>`                           |
| Startet die URL                                                                                                                                | `rundll32 url.dll,FileProtocolHandler \<URL\>`                                                  |
| E-Mail erzeugen                                                                                                                                | `rundll32 url.dll,MailToProtocolHandler mailto:\<E-Mail Adresse\>`                              |
| z.B. E-Mail Vorlage, nutze %20 als Leerzeichen                                                                                                 | `rundll32 url.dll,MailToProtocolHandler "mailto:0?cc=1&?bcc=2&subject=3"`                       |
| Rechner sperren                                                                                                                                | `rundll32 user32.dll,LockWorkStation`                                                           |
| Hardware sicher entfernen                                                                                                                      | `rundll32 shell32.dll,Control_RunDLL hotplug.dll`                                               |
| Gespeicherte Benutzernamen und Kennwörter                                                                                                      | `rundll32 Keymgr.dll,KRShowKeyMgr`                                                              |
| Rechner wird in den Ruhezustand gefahren                                                                                                       | `rundll32 powrprof.dll,SetSuspendState`                                                         |
| Ordneroptionen                                                                                                                                 | `rundll32 shell32.dll, Options_RunDLL 0`                                                        |


# Sources
- 2021-09-02: [Funktionen-Befehle der Dateien RUNDLL.EXE und RUNDLL32.EXE](http://www.winfaq.de/faq_html/Content/tip0500/onlinefaq.php?h=tip0564.htm)