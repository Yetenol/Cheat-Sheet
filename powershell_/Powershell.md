- [Upgrade applications](Upgrade%20applications.md)    
    Update Store Apps | `$wmiObj.UpdateScanMethod()`
- [Offer different options in a command line menu](Powershell/Offer%20different%20options%20in%20a%20command%20line%20menu.md)    
    Select option 1, 2, 3 | `$Choice = Read-Host -Prompt "Select ..."`
- [Encryption](Powershell/Encryption.md)    
    Passwords | `ConvertTo-SecureString`
- [List all bluetooth devices](Powershell/List%20all%20bluetooth%20devices.md)    
    List Devices | `Get-PnpDevice -Class Bluetooth`
- [Win-X Menu](windows/Win-X%20Menu.md)    
    Add Win+X entries
- [Input information](Powershell/Input%20information.md)    
    File Parsing | `[RegEx]::Match($_, $pattern).Groups[1].value`
- [Powershell Examples](Powershell%20Examples.md)    
    List all apps in PATH locations | ``
- [Modify objects](Powershell/basics/Modify%20objects.md)    
    Add calculated property | `$list[(0..1;-3..-1)]`
- **[Bash equivalents](Powershell/basics/bash-equivalents.md)**    
    While Loop | `read name` ⟷ `$name = Read-Host -Prompt "Name"`
- **[Parameter](Powershell/Specify%20parameters%20for%20functions%20and%20scripts.md)**    
    AutoComplete | `[Parameter(Mandatory = $true)]`
- **[File system](Powershell/filesystem/File%20system.md)**    
    Run as administrator | ``explorer "/select,`"$(Resolve-Path $file)`""``