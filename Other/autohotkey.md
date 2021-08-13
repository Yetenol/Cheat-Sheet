# AutoHotKey - Windows Automation scripting language

## 1. Generell code structure
```ahk
^j::                    ; :: indicates a hotkey
Send, My First Script   ;
return                  ;
```

## 1.1 Hotkeys
- end with `::`
- pauses current thread and starts a new one
```ahk
#, <#, ># /*Send*/ LWin, RWin
        ^ /*Send*/ Ctrl, LCtrl, RCtrl
        + /*Send*/ Shift, LShift, RShift
        ! /*Send*/ Alt, LAlt, RAlt
LButton ; primary mouse button
RButton ; secondary mouse button
MButton ; middle / wheel mouse button
Space, Tab, Enter, Escape, Pause, CtrlBreak
ScrollLock, CapsLock, NumLock, Insert, PrintScreen
Numpad0, NumpadAdd, NumpadEnter
```

## Legacy syntax
```ahk
RawText = My name is %username%!
TrayTip, %ExampleTitle%, Hello %username%, , 0x10
```
## Expression syntax
```ahk
Text := "My name is".username."!"
TrayTip, % generateTitle(482), % "Hello ".username, , % (0x4 + 0x4) * 2
```


## Override existing instance when launched again
```ahk
#SingleInstance, force
```

## Set a windows taskbar icon
- e.g: Display a keyboard
```ahk
Menu, Tray, Icon, % A_WinDir "\system32\imageres.dll", 174 
```

## Get program stdout, stderr
```ahk
    Shell := ComObjCreate("WScript.Shell") ; Create a new shell environment
	Script := Shell.Exec(information) ; Launch the script, proceed immidiately
	WinWait,% "ahk_exe youtube-dl.exe" ; Hide the script as soon as visible
	WinHide,% "ahk_exe youtube-dl.exe"
	
	; Get all output
	StdOut := Script.StdOut.ReadAll()
	StdErr := Script.StdErr.ReadAll()
	ErrLvl := (Script.Status == 2)	

	if (ErrLvl || StdErr) { ; Script failed
        MsgBox,% "The Script execution failed"
    }
```