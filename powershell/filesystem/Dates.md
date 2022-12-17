- **Read a date**
    ```powershell
    [DateTime]$date = [DateTime]"2022-02-01"
    ```

- **Read a date** according to the **current culture**
    ```powershell
    [DateTime]$date = "01.02.2022" |
    foreach { [DateTime]::Parse($_, [CultureInfo]::CurrentCulture) }
    ```

- **Read a date** according to a **specific culture**
    ```powershell
    $germanCulture = [cultureinfo]::GetCultureInfo('de-DE')
    [DateTime]$date = "01.02.2022" |
    foreach { [DateTime]::Parse($_, $germanCulture) }
    ```