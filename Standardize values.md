---
dg-publish: true
example: [ Numbers, Symbols, Quantities, Money ]
command: [ '\qty{3}{\celsius}', '\phi', '\dEUR{1.5}' ]
priority: 4
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
[[LaTeX]]