---
dg-publish: true
dg-home: true
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
