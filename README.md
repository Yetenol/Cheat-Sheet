# Guide and instructions to setup my computers

```dataview
LIST
    nonnull(list(
        choice(
            any(list(storeId,website,githubUser)),
            join(nonnull(list(
                choice(
                    any(storeId),
                    choice(
                        startswith(upper(storeId), "XP"),
                        "&#128279;",
                        elink("https://microsoft.com/store/apps/" + storeId, "Microsoft Store")
                    ),
                    null
                ),
                choice(
                    githubUser,
                    elink(
                        "https://github.com/" + githubUser + "/" + 
                        githubRepo + "/releases/latest" + 
                        choice(
                            githubBinary,
                            "/download/" + githubBinary,
                            ""
                        ),
                        "Github"
                    ),
                    null
                ),
                choice(
                    website,
                    elink(website, "Website"),
                    null
                )
            ))),
            null
        ),
        choice(
            storeId,
            "`winget install -e " + upper(storeId) + " --accept-package-agreements`",
            null
        ),
        choice(
            wingetId,
            "`winget install -e " + wingetId + "`",
            null
        )
    ))
FROM
    "apps" and [[]] and ![[See extension]]
SORT
    choice(priority,priority,99)
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





