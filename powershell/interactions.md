# Powershell - Interactions

## Ask a question once / until answered
```powershell
do {
  $Choice = Read-Host -Prompt "=== Select from: ===`n0 blue`ny yellow`n"
  switch ($Choice) {
    0 {
      Write-Host -Object "Painting in blue"
      break
    } 
    "y" {
      Write-Host -Object "Painting in yellow"
      return
    }
    default {
      $Choice = $null
      Write-Host -Object "=== Invalid choice! ==="
      break
    }
  }
} while ($Choice -eq $null)
```

## Ask a question repeatedly until canceled
```powershell
while ($true) {
  $Choice = Read-Host -Prompt "=== Select from: ===`n0  Sleep`n9+ Shutdown in _s`nq  Quit`n"
  $n = -1 # Choice parsed to number
  switch ($Choice) {
    0 {
      Write-Host -Object "Falling asleep"
      break
    } 
    {<#isNumber#>[double]::TryParse($_,[ref]$n) -and <# >8 #>($n -gt 8)} {
      Write-Host -Object @("Shutdown in", [math]::floor($_), "seconds")
      break
    }
    "q" {
      Write-Host -Object "=== Quit ==="
      return
    }
    default {
      $Choice = $null
      Write-Host -Object "=== Invalid choice! ==="
      break
    }
  }
}
```

## Edit file attributes
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

function Set-FileAttribute{
    param (
        [Parameter(Mandatory=$true)]    [string]$Path,
        [Parameter(Mandatory=$true)]    [System.IO.FileAttributes]$Attribute
    )
    $item = Get-Item -Path $Path -ErrorAction Stop
    $item.Attributes = $item.Attributes -bor ($Attribute).value__
    if (!$?) {throw}
} 

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