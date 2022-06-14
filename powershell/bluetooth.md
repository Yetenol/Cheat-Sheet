# Bluetooth
[⌂](../README.md) › [PowerShell](../README.md#powershell) ›

## List all bluetooth devices
```powershell
Get-PnpDevice -Class Bluetooth | where HardwareID -Match "\\DEV_"
```