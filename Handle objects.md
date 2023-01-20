---
example: [ Import, Export, Filter, RegEx Parsing ]
command: 
priority: 2
---

```dynamic-embed
[[Map of Content]]
```


<ul class="dataview list-view-ul"><li><span><a aria-label-position="top" aria-label="Filter and select objects.md" data-href="Filter and select objects.md" href="Filter and select objects.md" class="internal-link" target="_blank" rel="noopener">Filter and select objects</a></span>: <ul class="dataview dataview-ul dataview-result-list-ul"><li class="dataview-result-list-li"><span>Add calculated property</span></li><li class="dataview-result-list-li"><span><code>select -First 2 -Last 3</code></span></li></ul></li><li><span><a aria-label-position="top" aria-label="Export to files or outputs.md" data-href="Export to files or outputs.md" href="Export to files or outputs.md" class="internal-link" target="_blank" rel="noopener">Export to files or outputs</a></span>: <ul class="dataview dataview-ul dataview-result-list-ul"><li class="dataview-result-list-li"><span>CSV Tables, Plaintext files</span></li><li class="dataview-result-list-li"><span><code>Export-Csv -Delimiter "," -NoTypeInformation -Path ".\text.csv"</code></span></li></ul></li><li><span><a aria-label-position="top" aria-label="Handle sensitive input.md" data-href="Handle sensitive input.md" href="Handle sensitive input.md" class="internal-link" target="_blank" rel="noopener">Handle sensitive input</a></span>: <ul class="dataview dataview-ul dataview-result-list-ul"></ul></li><li><span><a aria-label-position="top" aria-label="Import and extract specific information out of a data file.md" data-href="Import and extract specific information out of a data file.md" href="Import and extract specific information out of a data file.md" class="internal-link" target="_blank" rel="noopener">Import and extract specific information out of a data file</a></span>: <ul class="dataview dataview-ul dataview-result-list-ul"><li class="dataview-result-list-li"><span>Find occurrences of a pattern</span></li><li class="dataview-result-list-li"><span><code>[RegEx]::Match($_, $pattern)</code></span></li></ul></li><li><span><a aria-label-position="top" aria-label="Input information.md" data-href="Input information.md" href="Input information.md" class="internal-link" target="_blank" rel="noopener">Input information</a></span>: <ul class="dataview dataview-ul dataview-result-list-ul"><li class="dataview-result-list-li"><span>File Parsing</span></li><li class="dataview-result-list-li"><span><code>[RegEx]::Match($_, $pattern).Groups[1].value</code></span></li></ul></li><li><span><a aria-label-position="top" aria-label="Standardize the handling of temporal data, clock times and time stamps.md" data-href="Standardize the handling of temporal data, clock times and time stamps.md" href="Standardize the handling of temporal data, clock times and time stamps.md" class="internal-link" target="_blank" rel="noopener">Standardize the handling of temporal data, clock times and time stamps</a></span>: <ul class="dataview dataview-ul dataview-result-list-ul"><li class="dataview-result-list-li"><span>First day of this month</span></li><li class="dataview-result-list-li"><span><code>[DateTime]::Now.TimeOfDay</code></span></li></ul></li><li><span><a aria-label-position="top" aria-label="Strongly type variables to ensure correct content and members.md" data-href="Strongly type variables to ensure correct content and members.md" href="Strongly type variables to ensure correct content and members.md" class="internal-link" target="_blank" rel="noopener">Strongly type variables to ensure correct content and members</a></span>: <ul class="dataview dataview-ul dataview-result-list-ul"><li class="dataview-result-list-li"><span>Hashtable, PSCustomObject</span></li><li class="dataview-result-list-li"><span><code>[PSCustomObject] @{ Name = "Karl"; ID = 45; }</code></span></li></ul></li></ul>


---


Sources:

Related:

Tags:
[PowerShell](PowerShell.md)