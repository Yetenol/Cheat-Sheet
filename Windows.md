---
dg-publish: true
example: 
command: 
priority: 
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
```

---


Sources:

Related:
[Anton's Digital Garden](Anton's%20Digital%20Garden.md)

Tags:
