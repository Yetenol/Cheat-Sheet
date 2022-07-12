<h1> Data types </h1>

[⌂](../../README.md) › [PowerShell](../../README.md#powershell) ›

> examples for common data types

| Examples                                                                                                                    | .GetType()-Names                                                                                                                                      |
| --------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------- |
| 42                                                                                                                          | Integers (Convert automatically to larger types) <br> <b>Int32, Int (32-bit signed integer)</b> <br> Int64, Long (64-bit signed integer)              |
| 3.65                                                                                                                        | Decimal numbers <br> <b>Double (Double-precision 64-bit floating point number)</b> <br> Single, Float (Single-precision 32-bit floating point number) |
| $True <br> $False                                                                                                           | <b>Boolean</b>                                                                                                                                        |
| "Hello" <br> 'Raw &%\Text' <br> "$env:temp\Trash" <br> ("Hi " + $a + "!`n")                                                 | Text or single characters <br> <b>String (Fixed-length string of Unicode characters)</b> <br> Char (A Unicode 16-bit character)                       |
| [DateTime]::Now <br> [DateTime]::UtcNow <br> [DateTime]"1999-12-31" <br> [DateTime]"23:45:33" <br> [DateTime]"1.1.07 12:30" | Timestamp as date and time <br> <b>DateTime</b>                                                                                                       |
| @(1; 2; 3; 7) <br> @(1..3; 7) <br> @('I'; 'am'; "here")                                                                     | <b>Object[], Array</b>                                                                                                                                |
| @{X=12; Y=45; N="Karl"}                                                                                                     | Dictionary of key/value pairs <br> <b>Hashtable</b>                                                                                                   |
| [ordered]@{X=12; Y=45}                                                                                                      | Ordered dictionary of key/value pairs <br> <b>OrderedDictionary</b>                                                                                   |