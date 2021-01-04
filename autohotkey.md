# AutoHotKey - Windows Automation scripting language

## Override existing instance when launched again
```ahk
#SingleInstance, force
```

## Set a windows taskbar icon
- e.g: Display a keyboard
```autohotkey
Menu, Tray, Icon, % A_WinDir "\system32\imageres.dll", 174 
```