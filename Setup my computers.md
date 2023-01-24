---
dg-publish: false
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

# List of all applications

Programs that I no longer install are shown in italics.

```dataview
TABLE WITHOUT ID
    choice(
        priority != null,
        file.link,
        "*" + file.link + "*"
    )
    as "App",
    join(sort(
        map(
            filter(
                file.outlinks,
                (x) => x.categoryName != null
            ),
            (x) => link(x.file.link,  x.categoryName)
    ))) 
    as "Category"
FROM
    "apps"
FLATTEN
    "This is a Map of all apps"
```


---


Sources:

Related:

Tags:
[[Anton's Digital Garden]]