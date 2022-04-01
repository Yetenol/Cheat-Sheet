# [⌂](../README.md) › [Powershell](../README.md#powershell) › Symbolic Link

## Create a symbolic link

```powershell
New-Item -ItemType SymbolicLink `
    -Name <# Filename #> `
    -Target <# Target Path #>
```

## Create a hard link

```powershell
New-Item -ItemType HardLink `
    -Name <# Filename #> `
    -Target <# Target Path #>
```

## Create a junction

```powershell
New-Item -ItemType Junction `
    -Name <# Filename #> `
    -Target <# Target Path #>
```