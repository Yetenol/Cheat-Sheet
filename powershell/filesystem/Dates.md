- Get a **date**
    ```powershell
    [DateTime]$date = [DateTime]"2022-04-13"
    ```

- **Read a date** according to the **current culture**
    ```powershell
    [DateTime]$date = "13.04.2022" |
    foreach { [DateTime]::Parse($_, [CultureInfo]::CurrentCulture) }
    ```

- **Read a date** according to a **specific culture**
    ```powershell
    $germanCulture = [cultureinfo]::GetCultureInfo('de-DE')
    [DateTime]$date = "13.04.2022" |
    foreach { [DateTime]::Parse($_, $germanCulture) }
    ```

- Read a date according to a **specific format**    
    ```powershell
    $dateFormat = "yyyyMMdd"
    [DateTime]$date = "20220413" | foreach {
        [DateTime]::ParseExact($_, $dateFormat, [CultureInfo]::InvariantCulture)
    }
    ```