# [⌂](../README.md) › [Powershell](../README.md#powershell) › File attributes

## .Net Attribute Flags

Attributes are bitwise combination of the following fields:


| Value                      | Name                 | Description                                                                                                                                                                                                                                                                                                                                                                 |
| -------------------------- | -------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `0x000001`  <br> = 1       | ReadOnly             | The file is read-only. ReadOnly is supported on Windows, Linux, and macOS. On Linux and macOS, changing the ReadOnly flag is a permissions operation.                                                                                                                                                                                                                       |
| `0x000002`  <br> = 2       | Hidden               | The file is hidden, and thus is not included in an ordinary directory listing. Hidden is supported on Windows, Linux, and macOS.                                                                                                                                                                                                                                            |
| `0x000004`  <br> = 4       | System               | The file is a system file. That is, the file is part of the operating system or is used exclusively by the operating system.                                                                                                                                                                                                                                                |
| `0x000010`  <br> = 16      | Directory            | The file is a directory. Directory is supported on Windows, Linux, and macOS.                                                                                                                                                                                                                                                                                               |
| `0x000020`  <br> = 32      | Archive              | This file is marked to be included in incremental backup operation. Windows sets this attribute whenever the file is modified, and backup software should clear it when processing the file during incremental backup.                                                                                                                                                      |
| `0x000040`  <br> = 64      | Device               | Reserved for future use.                                                                                                                                                                                                                                                                                                                                                    |
| `0x000080`  <br> = 128     | Normal               | The file is a standard file that has no special attributes. This attribute is valid only if it is used alone. Normal is supported on Windows, Linux, and macOS.                                                                                                                                                                                                             |
| `0x000100`  <br> = 256     | Temporary            | The file is temporary. A temporary file contains data that is needed while an application is executing but is not needed after the application is finished. File systems try to keep all the data in memory for quicker access rather than flushing the data back to mass storage. A temporary file should be deleted by the application as soon as it is no longer needed. |
| `0x000200`  <br> = 512     | SparseFile           | The file is a sparse file. Sparse files are typically large files whose data consists of mostly zeros.                                                                                                                                                                                                                                                                      |
| `0x000400`  <br> = 1024    | ReparsePoint         | The file contains a reparse point, which is a block of user-defined data associated with a file or a directory. ReparsePoint is supported on Windows, Linux, and macOS.                                                                                                                                                                                                     |
| `0x000800`  <br> = 2048    | Compressed           | The file is compressed.                                                                                                                                                                                                                                                                                                                                                     |
| `0x001000`  <br> = 4096    | Offline              | The file is offline. The data of the file is not immediately available.                                                                                                                                                                                                                                                                                                     |
| `0x002000`  <br> = 8192    | NotContentIndexed    | The file will not be indexed by the operating system's content indexing service.                                                                                                                                                                                                                                                                                            |
| `0x004000`  <br> = 16384   | Encrypted            | The file or directory is encrypted. For a file, this means that all data in the file is encrypted. For a directory, this means that encryption is the default for newly created files and directories.                                                                                                                                                                      |
| `0x008000`  <br> = 32768   | IntegrityStream      | The file or directory includes data integrity support. When this value is applied to a file, all data streams in the file have integrity support. When this value is applied to a directory, all new files and subdirectories within that directory, by default, include integrity support.                                                                                 |
| `0x020000`  <br> = 131072  | NoScrubData          | The file or directory is excluded from the data integrity scan. When this value is applied to a directory, by default, all new files and subdirectories within that directory are excluded from data integrity.                                                                                                                                                             |
| `0x080000`  <br> = 524288  | _AlwaysAvailable_ ¹⁾ | The file or directory is a OneDrive item that is always available on this device.                                                                                                                                                                                                                                                                                           |
| `0x100000`  <br> = 1048576 | _NoDataOnDisk_ ¹⁾    | The file or directory is a OneDrive item whose local disk space has been completely freed up to 0 bytes.                                                                                                                                                                                                                                                                    |

> ¹⁾ Non part of the official .Net documentation but official Windows behavior.

## Test A Specific Attribute:
```powershell
function Test-Attribute {
    [CmdletBinding()]
    param (
        [Parameter(Mandatory=$true, ValueFromPipeline=$true)]
        [ValidateNotNullOrEmpty()]
        $Path
        ,
        [ValidateSet('ReadOnly', 'Hidden', 'System', 'Directory', 'Archive', 'Device', 
        'Normal', 'Temporary', 'SparseFile', 'ReparsePoint', 'Compressed', 'Offline', 
        'NotContentIndexed', 'Encrypted', 'IntegrityStream', 'NoScrubData',
        '1', '2', '4', '8', '16', '32', '64', '128', '256', '512', '1024', 
        '2048', '4096', '8192', '16384', '32768', '65536', '131072', '262144', '524288', 
        '1048576', '2097152', '4194304', '8388608', '16777216', '33554432', '67108864', 
        '134217728', '268435456', '536870912', '1073741824')]
        [Parameter(Mandatory=$true)]
        $Attribute
    )
    switch (($Path).GetType()) {
        'System.IO.FileInfo' {
            $Path = $Path.FullName
        }
        'System.IO.DirectoryInfo' {
            $Path = $Path.FullName
        }
    }
    $item = Get-Item -Path $Path -ErrorAction Stop
    return [boolean]($item.Attributes -band $Attribute)
}
```

## Get All Attributes:
```powershell
function Get-Attributes {
    [CmdletBinding()]
    param(
        [Parameter(Mandatory=$true, ValueFromPipeline=$true)]
        [ValidateNotNullOrEmpty()]
        $Path
    )
    switch (($Path).GetType()) {
        'System.IO.FileInfo' {
            $Path = $Path.FullName
        }
        'System.IO.DirectoryInfo' {
            $Path = $Path.FullName
        }
    }
    foreach ($_ in 0..30) {
        [int]$value = [Math]::Pow(2, $_)
        if (Test-Attribute -Path $Path -Attribute $value) {
            Write-Output ([Enum]::Parse([System.IO.FileAttributes], $value))
        }
    }
}
```

## Show Attributes In Current Folder:
```powershell
Get-ChildItem . `
| select -Property Name, `
    @{Label="Flags"; Expression={[int]$_.Attributes}}, `
    @{Label="Attributes"; Expression={Get-Attributes -Path $_}}
```

## Enable A Specific Attribute:
```powershell
function Enable-Attribute {
    [CmdletBinding()]
    param (
        [Parameter(Mandatory=$true, ValueFromPipeline=$true)]
        [ValidateNotNullOrEmpty()]
        $Path
        ,
        [ValidateSet('ReadOnly', 'Hidden', 'System', 'Directory', 'Archive', 'Device', 
        'Normal', 'Temporary', 'SparseFile', 'ReparsePoint', 'Compressed', 'Offline', 
        'NotContentIndexed', 'Encrypted', 'IntegrityStream', 'NoScrubData',
        '1', '2', '4', '8', '16', '32', '64', '128', '256', '512', '1024', 
        '2048', '4096', '8192', '16384', '32768', '65536', '131072', '262144', '524288', 
        '1048576', '2097152', '4194304', '8388608', '16777216', '33554432', '67108864', 
        '134217728', '268435456', '536870912', '1073741824')]
        [Parameter(Mandatory=$true)]
        $Attribute
    )
    switch (($Path).GetType()) {
        'System.IO.FileInfo' {
            $Path = $Path.FullName
        }
        'System.IO.DirectoryInfo' {
            $Path = $Path.FullName
        }
    }
    $item = Get-Item -Path $Path -ErrorAction Stop
    $item.Attributes = $item.Attributes -bor [int]$Attribute
}
```

## Disable A Specific Attribute:
```powershell
function Disable-Attribute {
    [CmdletBinding()]
    param (
        [Parameter(Mandatory=$true, ValueFromPipeline=$true)]
        [ValidateNotNullOrEmpty()]
        $Path
        ,
        [ValidateSet('ReadOnly', 'Hidden', 'System', 'Directory', 'Archive', 'Device', 
        'Normal', 'Temporary', 'SparseFile', 'ReparsePoint', 'Compressed', 'Offline', 
        'NotContentIndexed', 'Encrypted', 'IntegrityStream', 'NoScrubData',
        '1', '2', '4', '8', '16', '32', '64', '128', '256', '512', '1024', 
        '2048', '4096', '8192', '16384', '32768', '65536', '131072', '262144', '524288', 
        '1048576', '2097152', '4194304', '8388608', '16777216', '33554432', '67108864', 
        '134217728', '268435456', '536870912', '1073741824')]
        [Parameter(Mandatory=$true)]
        $Attribute
    )
    switch (($Path).GetType()) {
        'System.IO.FileInfo' {
            $Path = $Path.FullName
        }
        'System.IO.DirectoryInfo' {
            $Path = $Path.FullName
        }
    }
    $item = Get-Item -Path $Path -ErrorAction Stop
    $item.Attributes = $item.Attributes -bxor [int]$Attribute
}
```

## Useful Combinations

| Hexadecimal            | Description                     | Fields                                     | Target | Name |
| ---------------------- | ------------------------------- | ------------------------------------------ | ------ | ---- |
| `0x080410` <br> 525328 | Always available on this device | `0x000010` <br> `0x000400` <br> `0x008000` |        |      |
| `0x080420` <br> 525344 |                                 | `0x000020` <br> `0x000400` <br> `0x008000` |        |      |

- List all valid attributes:
    ```powershell
    function List-ValidAttributes {
        foreach ($_ in 0..30) {
            [int]$flag = [Math]::Pow(2, $_)
            $possibleName = [Enum]::Parse([System.IO.FileAttributes], $flag)
            if ($possibleName -match "\D+") {
                $hexFlag = ("0x" + [System.String]::Format("{0:X6}",$flag))
                Write-Output ([PSCustomObject]@{ 
                Decimal = $flag
                Hexadecimal = $hexFlag
                Name = $possibleName
            })
            }
        }
    }
    ```

## Sources

- 2022-04-05 [FileAttributes Enum (System.IO) - Microsoft Docs](https://docs.microsoft.com/en-us/dotnet/api/system.io.fileattributes?view=net-6.0)
- 2022-04-05 [What does Directory and file Attributes - 525328, 525344 ,5248544 mean- - PowerShell](https://www.reddit.com/r/PowerShell/comments/sgsgpr/what_does_directory_and_file_attributes_525328/)