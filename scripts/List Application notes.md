```dataview
LIST
    nonnull(list(
        example,
        choice(
            any(command),
            join(
                map(nonnull(command), (x) => "`" + x + "`")
            ),
            null
        )
    ))
FROM "applications"
```