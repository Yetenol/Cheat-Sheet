# Commands
- see [RunDll32](http://www.winfaq.de/faq_html/Content/tip0500/onlinefaq.php?h=tip0564.htm)

Command | Description
- | -
rundll32 advpack.dll,LaunchINFSection \<INF-Datei\>,\<Section\> | Installation aus INF-Files
rundll32 appwiz.cpl,NewLinkHere \<Verzeichnis\> | Neue Verknüpfung anlegen
rundll32 desk.cpl,InstallScreenSaver \<saver.scr\> | Screensaver installieren
rundll32 diskcopy.dll,DiskCopyRunDLL \<0 oder 1\> | Ruft Diskcopy auf
rundll32 keymgr.dll,KRShowKeyMgr | Dialog "Gespeicherte Benutzernamen und Kennwörter"
rundll32 setupapi.dll,InstallHinfSection 132 \<.inf-Datei\> | Installation aus einer INF-Datei
rundll32 Shell32.dll,Control_RunDLL | Systemsteuerung
rundll32 shell32.dll,Control_FillCache_RunDLL | Systemsteuerungs-Applets neu einlesen
rundll32 Shell32.dll,Control_RunDLL main.cpl,@\<Zahl\> | Einstellung "Einstellung" aufrufen, 0 Maus, 1 Tastatur, 2 Drucker, 3 Schriftarten, 4 Energie
rundll32 shell32.dll,Control_RunDLL access.cpl | Erleichterte Bedienung
rundll32 shell32.dll,Control_RunDLL appwiz.cpl,null,0 | Software (Entfernen/Hinzufügen neuer Programme)
rundll32 shell32.dll,Control_RunDLL appwiz.cpl,null,1 | Software (Neue Programme vom Netzwerk hinzufügen)
rundll32 shell32.dll,Control_RunDLL appwiz.cpl,null,2 | Software (Windows Assistenten für Windows Komponenten, Windows Features)
rundll32 Shell32.dll,Control_RunDLL desk.cpl | Einstellung "Anzeigeeinstellungen" aufrufen
rundll32 shell32.dll,Control_RunDLL desk.cpl,null,0 | Desktop-Symboleinstellungen
rundll32 shell32.dll,Control_RunDLL desk.cpl,null,1 | Eigenschaften von Anzeige (Bildschirmschoner-Einstellungen)
rundll32 shell32.dll,Control_RunDLL desk.cpl,null,2 | Eigenschaften von Anzeige (Darstellung)
rundll32 shell32.dll,Control_RunDLL intl.cpl,null,0 | Regions-und Sprachoptionen - Tabreiter: Formate
rundll32 shell32.dll,Control_RunDLL intl.cpl,null,1 | Regions-und Sprachoptionen - Tabreiter: Verwaltung
rundll32 shell32.dll,Control_RunDLL joy.cpl | Gamecontroller
rundll32 shell32.dll,Control_RunDLL main.cpl @0 | Eigenschaften von Maus - Tabreiter: Tasten
rundll32 shell32.dll,Control_RunDLL main.cpl @1 | Eigenschaften von Tastatur - Tabreiter: Geschwindigkeit
rundll32 shell32.dll,Control_RunDLL mmsys.cpl,null,0 | Sound - Tabreiter: Wiedergabe
rundll32 shell32.dll,Control_RunDLL mmsys.cpl,null,1 | Sound - Tabreiter: Aufnahme
rundll32 shell32.dll,Control_RunDLL mmsys.cpl,null,2 | Sound - Tabreiter: Sounds
rundll32 shell32.dll,Control_RunDLL modem.cpl | Telefon- und Modemoptionen (Modems)
rundll32 shell32.dll,Control_RunDLL sysdm.cpl,null,1 | Systemeigenschaften - Tabreiter: Computername
rundll32 shell32.dll,Control_RunDLL sysdm.cpl,null,2 | Systemeigenschaften - Tabreiter: Hardware
rundll32 shell32.dll,Control_RunDLL sysdm.cpl,null,3 | Systemeigenschaften - Tabreiter: Erweitert
rundll32 shell32.dll,Control_RunDLL sysdm.cpl,null,4 | Systemeigenschaften - Tabreiter: Computerschutz
rundll32 shell32.dll,Control_RunDLL timedate.cpl,null,0 | Eigenschaften von Datum/Uhrzeit - Tabreiter: Datum und Uhrzeit
rundll32 shell32.dll,Control_RunDLL timedate.cpl,null,1 | Eigenschaften von Datum/Uhrzeit - Tabreiter: Zusätzliche Uhren
rundll32 shell32.dll,OpenAs_RunDLL | Box "Öffnen mit" aufrufen
rundll32 shell32.dll,OpenAs_RunDLL \<Datei\> | Öffnen mit... mit Dateiangabe
rundll32 Shell32.dll,ShellAboutA | Microsoft Windows Infobox
rundll32 shell32.dll,SHHelpShortcuts_RunDLL AddPrinter | Drucker hinzufügen
rundll32 shell32.dll,SHHelpShortcuts_RunDLL PrintersFolder | Druckerordner anzeigen
rundll32 printui.dll,PrintUIEntry \<Optionen\> \<@Befehlsdatei\> | Drucker direkt ohne Assistent hinzufügen, [Details](http://www.winfaq.de/faq_html/Content/tip2000/onlinefaq.php?h=tip2028.htm)
rundll32 printui.dll,PrintUIEntry /q /in /n \\\\ServerName\Freigabename | z.B. Netzwerkdrucker hinzufügen
rundll32 shell32.dll,SHHelpShortcuts_RunDLL FontsFolder | Schriftarten anzeigen
rundll32 shell32.dll,SHHelpShortcuts_RunDLL Connect | Netzwerklaufwerk verbinden, Dialog öffnen
rundll32 url.dll,TelnetProtocolHandler \<IP-Adresse bzw. Hostname\> | Telnet-Verbindung öffnen
rundll32 url.dll,FileProtocolHandler \<URL\> | Startet die URL
rundll32 url.dll,MailToProtocolHandler mailto:\<E-Mail Adresse\> | E-Mail erzeugen
rundll32 url.dll,MailToProtocolHandler "mailto:0?cc=1&?bcc=2&subject=3" | z.B. E-Mail Vorlage, nutze %20 als Leerzeichen
rundll32 user32.dll,LockWorkStation | Rechner sperren
rundll32 shell32.dll,Control_RunDLL hotplug.dll | Hardware sicher entfernen, Ist es möglich die Ansicht "Unplug or Eject Hardware" zu öffnen
rundll32 Keymgr.dll,KRShowKeyMgr | Gespeicherte Benutzernamen und Kennwörter
rundll32 powrprof.dll,SetSuspendState | Rechner wird in den Ruhezustand gefahren
rundll32 shell32.dll,Control_RunDLL wscui.cpl,Security Center | Windows Sicherheitscenter
rundll32 shell32.dll, Options_RunDLL 0 | Ordneroptionen