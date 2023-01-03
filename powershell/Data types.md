---
example: Hashtable
script: "[DateTime]::Now"
---
#obsidian/done

Examples for common data types

# Numbers

## Integers

- Convert automatically to larger types
- `[Int32]`, `[Int]` 32-bit signed integer
- `[Int64]`, `[Long]` 64-bit signed integer

```powershell
[Int] $smallNumber = 2147483647
[Long] $highNumber = 9223372036854775807
```

## Decimal numbers 

- `[Single]`, `[Float]` Single-precision 32-bit floating point number    
- `[Double]` Double-precision 64-bit floating point number

```powershell
[Float] $lowPrecision = 15.95459
[Double] $highPrecision = 15.954589770191
```

## Boolean

- `[Boolean]` Logical value
```powershell
[Boolean] $enabled = $True 
[Bool] $disabled = $False
```

# Text

- `[Char]` **Single** Unicode 16-bit **character**    
- `[String]` Fixed-length string of Unicode characters
 Char (A Unicode 16-bit character)
 
```powershell
[Char] $letter = "a"
[String] $evaluatedString = "Hello $env:Username"
[String] $unevaluatedString = 'Raw <>|$&%\Text'
[String] $combinedString1 = ("Found " + $_.Name + "!")
[String] $combinedString2 = ("Found $($_.Name)!")
[String] $combinedString3 = [String]@(
    "Found ",
    $_.Name,
    "!"
)
[String] $multilineString = @”  
First-line  
Second line  
Third line  
“@
```

# Time and date

- `[DateTime]` Timestamp as date and time   
  `Date`, `Day`, `DayOfWeek`, `DayOfYear`, `Hour`, `Kind`, `Millisecond`, `Minute`, `Month`, `Second`, `Ticks`, `TimeOfDay`, `Year`, `DateTime`

- `[DateTimeOffset]` Time intervall contains    
  `Date`, `DateTime`, `Day`, `DayOfWeek`, `DayOfYear`, `Hour`, `LocalDateTime`, `Millisecond`, `Minute`, `Month`, `Offset`, `Second`, `Ticks`, `TimeOfDay`, `UtcDateTime`, `UtcTicks`, `Year`

- get **current** time    
    ```powershell
    [DateTime] $currentTimestamp1 = Get-Date
    [DateTime] $currentTimestamp2 = [DateTime]::Now
    [DateTime] $currentUtcTimestamp = [DateTime]::UtcNow
    [Int64] $unixMillis = [DateTimeOffset]::Now.ToUnixTimeMilliseconds()
    ```

- get **specific** timestamp    
    ```powershell
    [DateTime] $nowNewYearsEve = Get-Date -Year 1999 -Month 12 -Day 31
    [DateTime] $midnightNewYearsEve = [DateTime]"1999-12-31" 
    [DateTime] $todayQuarterToTwelve = [DateTime]"23:45:33" 
    [DateTime] $13ofJanuary2007 = [DateTime]"1.13.07 12:30"
    ```

- get **relative** timestamp    
    ```powershell
    [DateTime] $lastMidnight = [DateTime]::Now - [DateTime]::Now.TimeOfDay
    [DateTime] $yesterday = [DateTime]::Now.AddDays(-1)
    [DateTime] $firstThisMonth = Get-Date -Date $lastMidnight -Day 1
    ```

# Containers

- `[Object[]]`, `[Array]` **List** of values
- `[PSCustomObject]` Custom **entity** of members and properties
- `[Hashtable]` **Dictionary** of key-value pairs
- `[Collections.Specialized.OrderedDictionary]` **Ordered dictionary** of key-value pairs 
```powershell
[Int32[]] $numbers1 = @(1; 2; 3; 7)
[Int32[]] $numbers2 = @(1..3; 7) 
[Int32[]] $numbers3 = (1..3, 7)
[String[]] $words = @(
    'I'; 
    'am';
    "here"
)
```
```powershell
[PSCustomObject] $object = [PSCustomObject] @{
    Name = "Karl";
    ID = 45;
}
$object | select ID
```
```powershell
[Hashtable] $hashtable = @{
    Name = "Karl";
    ID = 45;
}
$hashtable | foreach { $_.ID }
```
```powershell
[Collections.Specialized.OrderedDictionary] $List = [ordered]@{
    First = 12; 
    Second = 45;
}
$List[0]
```


---
Sources:
- 2022-12-17: [PowerShell Hash Table vs. PSCustomObject- Deep Dive & Comparison - Jeff Brown Tech](https://jeffbrown.tech/powershell-hash-table-pscustomobject/)
- 2022-12-17: [Difference between single quote (‘) and double quote (“) in PowerShell](https://www.tutorialspoint.com/difference-between-single-quote-and-double-quote-in-powershell)
- 2022-12-17: [PowerShell Multiline String - Working of multiline string using her string](https://www.educba.com/powershell-multiline-string/)

Related:
[Input information](Input%20information.md)

Tags:
