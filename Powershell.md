
```dataview
LIST
    (example + " | `" + command + "`")
FROM "powershell"
```
-   [Analyse objects and diagnose issues](powershell/Analyse%20objects%20and%20diagnose%20issues.md): - | `\-`
-   [Bulk rename picture and videos to their capture time](powershell/Bulk%20rename%20picture%20and%20videos%20to%20their%20capture%20time.md): - | `\-`
-   [Data types](powershell/Data%20types.md): Hashtable | `\-`
-   [Dates](powershell/filesystem/Dates.md): - | `\-`
-   [Create shortcuts and symbolic links](powershell/filesystem/Create%20shortcuts%20and%20symbolic%20links.md): - | `\-`
-   [Download or invoke files from the internet](powershell/filesystem/Download%20or%20invoke%20files%20from%20the%20internet.md): - | `\-`
-   [attributes](powershell/filesystem/attributes.md): - | `\-`
-   [export](powershell/filesystem/export.md): - | `\-`
-   [Interact with the File System](powershell/filesystem/Interact%20with%20the%20File%20System.md): Run as administrator | `\-`
-   [Test paths and retrieve filesystem information](powershell/filesystem/Test%20paths%20and%20retrieve%20filesystem%20information.md): - | `\-`
-   [bash-equivalents](powershell/basics/bash-equivalents.md): While Loop | `read name <-> $name = Read-Host -Prompt "Name"`
-   [Modify objects](powershell/basics/Modify%20objects.md): Add calculated property | `$list[(0..1;-3..-1)]`
-   [Data file](powershell/Data%20file.md): - | `\-`
-   [File system metadata](powershell/File%20system%20metadata.md): - | `\-`
-   [List all apps in PATH locations](powershell/List%20all%20apps%20in%20PATH%20locations.md): - | `\-`
-   [List all bluetooth devices](powershell/List%20all%20bluetooth%20devices.md): List Devices | `Get-PnpDevice -Class Bluetooth`
-   [Input information](powershell/Input%20information.md): File Parsing | `[RegEx]::Match($_, $pattern).Groups[1].value`
-   [Naming convention](powershell/Naming%20convention.md): - | `\-`
-   [Make scripts executable when renamed cmd](powershell/Make%20scripts%20executable%20when%20renamed%20cmd.md): script.ps1.bat | `Invoke-Command -ScriptBlock ([ScriptBlock]::Create($cmd))`
-   [Offer different options in a command line menu](powershell/Offer%20different%20options%20in%20a%20command%20line%20menu.md): Select option 1, 2, 3 | `$Choice = Read-Host -Prompt "Select ..."`
-   [Powershell Examples](powershell/Powershell%20Examples.md): list connfiguration items | `\-`
-   [Specify parameters for functions and scripts](powershell/Specify%20parameters%20for%20functions%20and%20scripts.md): AutoComplete | `Parameter(Mandatory = $true)`
-   [Upgrade applications](powershell/Upgrade%20applications.md): Update Store Apps | `$wmiObj.UpdateScanMethod()`
-   [Powershell](Powershell.md): - | `\-`
-   [Sensitive input](powershell/Sensitive%20input.md): - | `\-`
-   [Encrypt or decrypt sensitive text](powershell/Encrypt%20or%20decrypt%20sensitive%20text.md): Passwords | `ConvertTo-SecureString`