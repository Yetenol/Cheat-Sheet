<h1> Import data </h1>

[⌂](../../README.md) › [PowerShell](../../README.md) › [FileSystem](filesystem.md) ›

Table of Contents
- [User Input](#user-input)
- [.Net formatted file](#net-formatted-file)
- [Plain text file](#plain-text-file)
  - [Find Occurrences Of A Pattern](#find-occurrences-of-a-pattern)
  - [Extract Data Using A Pattern](#extract-data-using-a-pattern)
- [Sensitive input](#sensitive-input)
  - [Decrypt locally](#decrypt-locally)

# User Input

```powershell
$User = Get-Host "Username"
```

# .Net formatted file

> Use `.xml` files to preserve the PowerShells Object information.

- Import an **object** from an .xml file:

    ```powershell
    $object = Import-Clixml -Path ".\example.xml"
    ```

- Count the elements of the object:

    ```powershell
    $object.Count
    ```

- Find all an array's elements whose name contains `processor`:

    ```powershell
    $captures = $object |            # output the pipeline into $captures
    ? { $_.Name -match "processor" } # filter only matching objects
    ```


# Plain text file

- Import **all** lines from a plaintext file:

    ```powershell
    $lines = Get-Content -Path ".\example.txt"
    ```

- Import only a specific line or **range of lines** from a plaintext file: 

    ```powershell
    $line26      = (Get-Content -Path ".\example.txt")[25]
    $line23til26 = (Get-Content -Path ".\example.txt")[22..25]
    ```

    > `-TotalCount` speeds up the commands by only loading the first 26 lines.

    ```powershell
    $line26      = (Get-Content -Path ".\example.txt" -TotalCount 26)[25]
    $line23til26 = (Get-Content -Path ".\example.txt" -TotalCount 26)[22..25]
    ```

- Count the number of lines:

    ```powershell
    $lines.Count
    ```

## Find Occurrences Of A Pattern

> Quick [**Regular Expression**](../../languages/regex.md) Reference for `-match` and `[RegEx]::`  
> `(?ENABLE-DISABLE)` [Interpretation Options](../../languages/regex.md#engine-interpretation-options):  `i` IgnoreCase;  `n` ExplicitCapture;  `x` IgnorePatternWhitespace;  `m` Multiline;  `s` Singleline;  
> `^` Start of line;  `$` End of line;  `.*` ≥0 character(s);  `.+` ≥0 character(s);  `\w*` Any word;  `\S*` Any non-whitespace;
> `\s*` Any whitespace;  `(.*)` Unnamed group;     `(?<user>.*)` Named group called user

In the following, lines are searched for that begin with the word `user`, case-insensitive:
```powershell
$pattern = "(?i)^user"
```

- Find the lines of **all** occurrences of the pattern:
    ```powershell
    $captures = Get-Content -Path ".\example.txt"  |
    ? {$_ -match $pattern}
    ```
    > `-ReadCount` speeds up the search when using large files as it sends the lines in 1k batches through the pipeline. Beware of slightly different formatting.
    ```powershell
    $captures = Get-Content -Path ".\example.txt" -ReadCount 1000 | 
    ? { $_ -match $pattern }
    ```


- **Count** the occurrences of the pattern:

    ```powershell
    $captures.Count
    ```

- Find the line of the **first** occurrence of the pattern:

    ```powershell
    $capture = $captures[0]
    ```

    ```powershell
    Get-Content -Path ".\example.txt" | 
    ? { $_ -match $pattern } | 
    % {
        $capture = $_
        break
    }
    ```

    > `-ReadCount` is difficult to use here.

## Extract Data Using A Pattern

> Quick [**Regular Expression**](../../languages/regex.md) Reference for `-match` and `[RegEx]::`  
> `(?ENABLE-DISABLE)` [Interpretation Options](../../languages/regex.md#engine-interpretation-options):  `i` IgnoreCase;  `n` ExplicitCapture;  `x` IgnorePatternWhitespace;  `m` Multiline;  `s` Singleline;  
> `^` Start of line;  `$` End of line;  `.*` ≥0 character(s);  `.+` ≥0 character(s);  `\w*` Any word;  `\S*` Any non-whitespace;
> `\s*` Any whitespace;  `(.*)` Unnamed group;     `(?<user>.*)` Named group called user

- Extract a **single** datum from the **first** occurrence of the pattern.

    Get the username from lines that start with the listing of a user name:

    ```powershell
    # line example   ···Username:···anna····[...] 
    $pattern = '(?i)^\s*username:\s*(\w*)'

    Get-Content -Path ".\example.txt" | 
    % { [RegEx]::Match($_, $pattern) } | # output regex search foreach line
    ? { $_.Success } |                   # filter only matching lines
    % {
        $capture = $_.Groups[1].value    # matched groups start at index 1
        break                            # stop further searching
    }

    if ($capture) {Write-Output $capture} else {Write-Error "Nothing found!"}
    ```

- Extract **multiple** data from **each** occurrence of the pattern.

    Get the credentials from lines that list a username and password:

    > Use option `n` (ExplicitCapture) to ignore all unnamed groups.

    ```powershell
    # line example    ···Username:···annaSchmidt···Password:···turtles_48··· 
    $pattern = '(?in)^\s*username:\s*(?<user>\S*)\s*password:\s*(?<pwd>\S*)\s*$'
    
    $capture = Get-Content -Path ".\example.txt" | # output each line
    % { [RegEx]::Match($_, $pattern) } | # output regex search foreach line
    ? { $_.Success } |                   # filter only matching lines
    % { [PSCustomObject]@{               # output each credential into the array
        Username = $_.Groups["user"].value;
        Password = $_.Groups["pwd"].value;
    }}

    if ($capture) {Write-Output $capture} else {Write-Error "Nothing found!"}
    ```

- Extract from occurrences of a **multiline** pattern.

    Get the title key pairs of listings in consecutive lines:

    > Use `[RegEx]::Matches` for **all** and `[RegEx]::Match` for the **first** occurrence of the pattern.

    > Import file using `-Raw` to save it as a **single string** instead of an array of lines.  
    > Use option `m` (multiline) to let `^` and `$` match the beginning and end of **each line** instead of the entire input string. 

    ```powershell
    # lines example    Name···:···ProgramFiles 
    #                  Value··:···C:\Program Files (x86)
    $pattern = '(?inm)^name\s*:\s*(?<title>.*)\nvalue\s*:\s*(?<key>.*)$'

    $captures = Get-Content -Path ".\example.txt" -Raw | # output one string 
    % { [RegEx]::Matches($_, $pattern) } | # output all regex matches
    % { [PSCustomObject]@{                 # output each pair into the array
        Title = $_.Groups["title"].value;
        Key   = $_.Groups["key"].value;
    }}

    if ($captures) {Write-Output $captures} else {Write-Error "Nothing found!"}
    ```

# Sensitive input

Don't save passwords as plain text.   
Instead save them as a secure string and **encrypt** them **locally**.

- **Input sensitive data** into the console
    ```powershell
    $securePassword = Read-Host "Password" -AsSecureString
    ```

- Don't convert _plain text_ into _secure string_  
    as the commands get logged.
    ```powershell
    $securePassword = ConvertTo-SecureString $PlainPassword -AsPlainText -Force
    ```

## Decrypt locally

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