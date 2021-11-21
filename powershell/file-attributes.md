# [⌂] › (../README.md) [Powershell](../README.md#powershell) › File attributes

## Get attributes
```powershell
function Get-FileAttribute{
    param (
        [Parameter(Mandatory=$true)]    [string]$Path,
        [Parameter(Mandatory=$true)]    [System.IO.FileAttributes]$Attribute
    )
    $item = Get-Item -Path $Path -ErrorAction Stop
    if (($item.Attributes -band $item.Attributes) -eq $Attribute) {
        return $true
    } else {
        return $false
    }
}
```


## Set attributes
```powershell
function Set-FileAttribute{
    param (
        [Parameter(Mandatory=$true)]    [string]$Path,
        [Parameter(Mandatory=$true)]    [System.IO.FileAttributes]$Attribute
    )
    $item = Get-Item -Path $Path -ErrorAction Stop
    $item.Attributes = $item.Attributes -bor ($Attribute).value__
    if (!$?) {throw}
} 
```


## Clear attributes
```powershell
function Clear-FileAttribute{
    param (
        [Parameter(Mandatory=$true)]    [string]$Path,
        [Parameter(Mandatory=$true)]    [System.IO.FileAttributes]$Attribute
    )
    $item = Get-Item -Path $Path -ErrorAction Stop
    if (($item.Attributes -band $item.Attributes) -eq $Attribute) {
        $item.Attributes = $item.Attributes -bxor ($Attribute).value__
    }
    if (!$?) {throw}
}
```

## Toggle attributes
```powershell
function Toggle-FileAttribute{
    param (
        [Parameter(Mandatory=$true)]    [string]$Path,
        [Parameter(Mandatory=$true)]    [System.IO.FileAttributes]$Attribute
    )
    $item = Get-Item -Path $Path -ErrorAction Stop
    $item.Attributes = $item.Attributes -bxor ($Attribute).value__
    if (!$?) {throw}
}
```