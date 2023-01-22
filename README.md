---
dg-publish: true
dg-home: true
dg-publish: true
---

# Documentation 

![last commit](https://img.shields.io/github/last-commit/yetenol/doc?color=white)

This project contains all my documentations of my developer life including code templates, tips and tricks, cheat sheets and glossaries.

```dataview
LIST
    nonnull(list(
        choice(
            any(example),
            join(nonnull(example)),
            null
        ),
        choice(
            any(command),
            join(
                map(
                    nonnull(command), 
                    (x) => "`" + x + "`"
                )
            ),
            null
        )
    ))
FROM
    [[]]
SORT
    choice(priority, priority, 999999)
```

<ul class="dataview list-view-ul"><li><span><a aria-label-position="top" aria-label="Applications.md" data-href="Applications.md" href="Applications.md" class="internal-link" target="_blank" rel="noopener">Applications</a></span>: <ul class="dataview dataview-ul dataview-result-list-ul"></ul></li><li><span><a aria-label-position="top" aria-label="Discussions.md" data-href="Discussions.md" href="Discussions.md" class="internal-link" target="_blank" rel="noopener">Discussions</a></span>: <ul class="dataview dataview-ul dataview-result-list-ul"></ul></li><li><span><a aria-label-position="top" aria-label="Languages and Encodings.md" data-href="Languages and Encodings.md" href="Languages and Encodings.md" class="internal-link" target="_blank" rel="noopener">Languages and Encodings</a></span>: <ul class="dataview dataview-ul dataview-result-list-ul"></ul></li><li><span><a aria-label-position="top" aria-label="LaTeX.md" data-href="LaTeX.md" href="LaTeX.md" class="internal-link" target="_blank" rel="noopener">LaTeX</a></span>: <ul class="dataview dataview-ul dataview-result-list-ul"></ul></li><li><span><a aria-label-position="top" aria-label="Windows.md" data-href="Windows.md" href="Windows.md" class="internal-link" target="_blank" rel="noopener">Windows</a></span>: <ul class="dataview dataview-ul dataview-result-list-ul"></ul></li><li><span><a aria-label-position="top" aria-label="PowerShell.md" data-href="PowerShell.md" href="PowerShell.md" class="internal-link" target="_blank" rel="noopener">PowerShell</a></span>: <ul class="dataview dataview-ul dataview-result-list-ul"></ul></li></ul>
