<h1> .Net Operations </h1>

[⌂](../README.md) ([Languages](../README.md#languages-encodings)) › [Regular Expressions](regex.md) ›

> Class: System.Text.RegularExpressions.Regex 

## Pattern matching with Regex objects

| To initialize with | Use constructor                       |
| ------------------ | ------------------------------------- |
| Regular            | exp Regex(String)                     |
| + options          | Regex(String, RegexOptions)           |
| + time-out         | Regex(String, RegexOptions, TimeSpan) |


## Pattern matching with static methods 

Use an overload of a method below to supply the 
regular expression and the text you want to search.


## Finding and replacing matched patterns

| To                    | Use method                                       |
| --------------------- | ------------------------------------------------ |
| Validate match        | Regex.IsMatch                                    |
| Retrieve single match | Regex.Match (first)  <br> Match.NextMatch (next) |
| Retrieve all matches  | Regex.Matches                                    |
| Replace match         | Regex.Replace                                    |
| Divide text           | Regex.Split                                      |
| Handle char escapes   | Regex.Escape <br> Regex.Unescape                 |


## Getting info about regular expression patterns

| To get        | Use Regex API                               |
| ------------- | ------------------------------------------- |
| Group names   | GetGroupNames <br> GetGroupNameFromNumber   |
| Group numbers | GetGroupNumbers <br> GetGroupNumberFromName |
| Expression    | ToString                                    |
| Options       | Options                                     |
| Time-out      | MatchTimeOut                                |
| Cache size    | CacheSize                                   |
| Direction     | RightToLeft                                 |