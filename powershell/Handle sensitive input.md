# Encrypt or input data

Don't save passwords as plain text. Instead save them as a secure string and **encrypt** them **locally**.

- **Input sensitive data** into the console
    ```powershell
    $securePassword = Read-Host "Password" -AsSecureString
    ```

- Don't convert _plain text_ into _secure string_  
    as the commands get logged.
    ```powershell
    $securePassword = ConvertTo-SecureString $PlainPassword -AsPlainText -Force
    ```

# Read and write files

- **encrypt** an existing file
    ```powershell
    $xml = Get-Content -Path ".\temp.xml" -Raw
    ConvertTo-SecureString -AsPlainText $xml -Force `
    | ConvertFrom-SecureString `
    | Out-File secure.bin

    Remove-Item -Path ".\temp.xml"
    ```

- **decrypt** an existing file
    ```powershell
    $secure = Get-Content -Path ".\secure.bin" `
    | ConvertTo-SecureString

    $bstr = [Runtime.InteropServices.Marshal]::SecureStringToBSTR($secure)
	$xml = [Runtime.InteropServices.Marshal]::PtrToStringAuto($bstr)
    $xml | Out-File ".\temp.xml"
    ```


# Decrypt data locally

Only the **same PowerShell instance** can decrypt. 

- **Decrypt** a secure string
    ```powershell
    function Decrypt-SecureString {
        [CmdletBinding()] param(
            [Parameter(Mandatory=$true, ValueFromPipeline=$true)] $SecureObject
        )
        $type = ($SecureObject).getType()
        if ($type -eq [System.Security.SecureString]) {
            [System.Net.NetworkCredential]::new("", $SecureObject).Password
        } elseif ($type -eq [System.Management.Automation.PSCredential]) {
            Decrypt-SecureString -SecureObject $SecureObject.Password
        } else {
            Write-Error ("The parameter is of unknown type [" + [string]$($SecureObject.GetType().FullName) + "]")
        }
    }
    ```

- **Decrypt** a secure string or credential
    ```powershell
    function Decrypt-SecureString {
        [CmdletBinding()] param(
            [Parameter(ParameterSetName='secureString', Position=0, ValueFromPipeline=$true)]
            [System.Security.SecureString] $secureString,
            [Parameter(ParameterSetName='credential', Position=0)]
            [System.Management.Automation.PSCredential] $credential
        )
        switch ($PSCmdlet.ParameterSetName) {
            'secureString' {
                Write-Output ([System.Net.NetworkCredential]::new("", $secureString).Password)
            }
            'credential' {
                Decrypt-SecureString -secureString $credential.Password
            }
        }
    }
    ```


---
#obsidian/done 

Sources:

Related:

Tags:
[Operate on the file system](../Operate%20on%20the%20file%20system.md)
[Handle objects](../Handle%20objects.md)