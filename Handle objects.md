---
dg-publish: false
example: [ Import, Export, Filter, RegEx Parsing ]
command: 
priority: 2
---

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
FLATTEN
    "This is a Map of Content"
```

---


Sources:

Related:

Tags:
[[PowerShell]]