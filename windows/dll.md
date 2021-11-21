# [⌂](../README.md) › Windows › Dll commands
- Dynamic Link Library (dll) components
- Control Panel tabs (cpl tab)

Command | Description
--- | ---
`rundll32 advpack.dll,LaunchINFSection \<INF-Datei\>,\<Section\>` | Installation aus INF-Files
`rundll32 appwiz.cpl,NewLinkHere \<Verzeichnis\>` | `Neue Verknüpfung anlegen`
`rundll32 desk.cpl,InstallScreenSaver \<saver.scr\>` | Screensaver installieren
`rundll32 diskcopy.dll,DiskCopyRunDLL \<0 oder 1\>` | Ruft Diskcopy auf
`rundll32 keymgr.dll,KRShowKeyMgr` | `Stored User Names and Passwords`
`rundll32 setupapi.dll,InstallHinfSection 132 \<.inf-Datei\>` | Installation aus einer INF-Datei
`rundll32 Shell32.dll,Control_RunDLL` | **Systemsteuerung**
`rundll32 shell32.dll,Control_FillCache_RunDLL` | Systemsteuerungs-Applets neu einlesen
`rundll32 Shell32.dll,Control_RunDLL main.cpl,@0` | Mouse Settings # ThinkPad (TrackPoint / `TouchPad`)
`rundll32 Shell32.dll,Control_RunDLL main.cpl,@1` | Keyboard Properties
`rundll32 shell32.dll,Control_RunDLL access.cpl` | Erleichterte Bedienung
`rundll32 shell32.dll,Control_RunDLL appwiz.cpl,null,0` | Control Panel > `Uninstall or change a program`
`rundll32 shell32.dll,Control_RunDLL appwiz.cpl,null,1` | Control Panel > Install a program from the network
`rundll32 shell32.dll,Control_RunDLL appwiz.cpl,null,2` | Control Panel > `Windows Features`
`rundll32 Shell32.dll,Control_RunDLL desk.cpl` | Settings > Display
`rundll32 shell32.dll,Control_RunDLL desk.cpl,null,0` | Control Panel > `Desktop Icon Settings`
`rundll32 shell32.dll,Control_RunDLL desk.cpl,null,1` | Control Panel > Screen Saver Settings
`rundll32 shell32.dll,Control_RunDLL desk.cpl,null,2` | Settings > Background
`rundll32 shell32.dll,Control_RunDLL intl.cpl,null,0` | Control Panel > Region # `Formats`
`rundll32 shell32.dll,Control_RunDLL intl.cpl,null,1` | Control Panel > Region # Administrative
`rundll32 shell32.dll,Control_RunDLL joy.cpl` | Game Controllers
`rundll32 shell32.dll,Control_RunDLL mmsys.cpl` | Control Panel > Sound
`rundll32 shell32.dll,Control_RunDLL mmsys.cpl,null,0` | Control Panel > Sound # `Playback`
`rundll32 shell32.dll,Control_RunDLL mmsys.cpl,null,1` | Control Panel > Sound # `Recording`
`rundll32 shell32.dll,Control_RunDLL mmsys.cpl,null,2` | Control Panel > Sound # `Sounds`
`rundll32 shell32.dll,Control_RunDLL sysdm.cpl,null,1` | Control Panel > System Properties # Computer Name
`rundll32 shell32.dll,Control_RunDLL sysdm.cpl,null,2` | Control Panel > System Properties # Hardware
`rundll32 shell32.dll,Control_RunDLL sysdm.cpl,null,3` | Control Panel > System Properties # Advanced <br> (Performance, `User Profiles`, Startup and Recovery, Environment Variables)
`rundll32 shell32.dll,Control_RunDLL sysdm.cpl,null,4` | Control Panel > System Properties # System Protection <br> (`Restore Point`)
`rundll32 shell32.dll,Control_RunDLL timedate.cpl,null,0` | Control Panel > Date and Time # Date and Time
`rundll32 shell32.dll,Control_RunDLL timedate.cpl,null,1` | Control Panel > Date and Time # Additional Clocks
`rundll32 shell32.dll,OpenAs_RunDLL` | Open with dialog
`rundll32 shell32.dll,OpenAs_RunDLL \<Datei\>` | `Open with dialog for a specific file`
`rundll32 Shell32.dll,ShellAboutA <br> winver` | About MZ/Windows (Version, `OS Build`)
`rundll32 shell32.dll,SHHelpShortcuts_RunDLL AddPrinter` | `Add a printer` dialog
`rundll32 shell32.dll,SHHelpShortcuts_RunDLL PrintersFolder <br> explorer shell:printersfolder` | `Printers Folder`
`rundll32 printui.dll,PrintUIEntry \<Optionen\> \<@Befehlsdatei\>` | Drucker direkt ohne Assistent hinzufügen, [Details](http://www.winfaq.de/faq_html/Content/tip2000/onlinefaq.php?h=tip2028.htm)
`rundll32 printui.dll,PrintUIEntry /q /in /n \\\\ServerName\Freigabename` | z.B. Netzwerkdrucker hinzufügen
`rundll32 shell32.dll,SHHelpShortcuts_RunDLL FontsFolder` | Schriftarten anzeigen
`rundll32 shell32.dll,SHHelpShortcuts_RunDLL Connect` | Netzwerklaufwerk verbinden, Dialog öffnen
`rundll32 url.dll,TelnetProtocolHandler \<IP-Adresse bzw. Hostname\>` | Telnet-Verbindung öffnen
`rundll32 url.dll,FileProtocolHandler \<URL\>` | Startet die URL
`rundll32 url.dll,MailToProtocolHandler mailto:\<E-Mail Adresse\>` | E-Mail erzeugen
`rundll32 url.dll,MailToProtocolHandler "mailto:0?cc=1&?bcc=2&subject=3"` | z.B. E-Mail Vorlage, nutze %20 als Leerzeichen
`rundll32 user32.dll,LockWorkStation` | Rechner sperren
`rundll32 shell32.dll,Control_RunDLL hotplug.dll` | Hardware sicher entfernen, Ist es möglich die Ansicht "Unplug or Eject Hardware" zu öffnen
`rundll32 Keymgr.dll,KRShowKeyMgr` | Gespeicherte Benutzernamen und Kennwörter
`rundll32 powrprof.dll,SetSuspendState` | Rechner wird in den Ruhezustand gefahren
`rundll32 shell32.dll,Control_RunDLL wscui.cpl,Security Center` | Windows Sicherheitscenter
`rundll32 shell32.dll, Options_RunDLL 0` | Ordneroptionen


### Sources
- 2021-09-02: [Funktionen-Befehle der Dateien RUNDLL.EXE und RUNDLL32.EXE](http://www.winfaq.de/faq_html/Content/tip0500/onlinefaq.php?h=tip0564.htm)