---
example: AutoComplete
command: [Parameter(Mandatory = $true)]
---

Parameters are defined at the first non-comment line within a script of function.
```powershell
param (
    $noun,
    $verb
)
```

- define **flag**  
    Boolean is _true_ or _false_.
    ```powershell
    [switch]$force
    ```
- define **specific type**  
    ```powershell
    [DateTime]$date
    ```
- **validate** out of predefined options  
    Enables AutoComplete.
    ```powershell
    [ValidateSet("World", "Galaxy", "Universe")]
    $noun
    ```
- set **default value**  
    ```powershell
    $noun = "none"
    ```
- set **default** via command  
    ```powershell
    $date = $(Get-Date)
    ```
- **require** parameter  
    ```powershell
    [Parameter(Mandatory = $true)]
    $noun
    ```
    
## Attributes

| Attribute                             | Description                                                                     |
| ------------------------------------- | ------------------------------------------------------------------------------- |
| `[DontShow()]`                        | Hide parameter in IntelliSense and tab completion                               |
| `[HelpMessage()]`                     | Provide a help message for mandatory parameters                                 |
| `[HelpMessageBaseName()]`             | Name of resource assembly that contains compiled help messages                  |
| `[HelpMessageResourceId()]`           | Resource identifier for help message                                            |
| `[Mandatory()]`                       | Make parameter mandatory and prompt for value when the user does not supply one |
| `[ParameterSetName()]`                | Define mutually exclusive parameters                                            |
| `[Position()]`                        | Assign positions to parameters and use arguments without parameter names        |
| `[ValueFromPipeline()]`               | Assign pipeline input to a parameter                                            |
| `[ValueFromPipelineByPropertyName()]` | Assign a specific property of pipeline input to a parameter                     |
| `[ValueFromRemainingArguments()]`     | Create a ParamArray and assign any unbound argument to a parameter              |


## Sources
- 2022-11-14: [Designing Professional Parameters - powershell.one](https://powershell.one/powershell-internals/attributes/parameters)