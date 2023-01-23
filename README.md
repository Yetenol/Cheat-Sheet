# Guide and instructions to setup my computers

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
```





