---
dg-publish: false
example: 
command: 
priority: 3
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