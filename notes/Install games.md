---
categoryName: Gaming
priority: 9
---

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



<ul class="dataview list-view-ul"><li><span><a aria-label-position="top" aria-label="apps/Minecraft Java.md" data-href="apps/Minecraft Java.md" href="apps/Minecraft Java.md" class="internal-link" target="_blank" rel="noopener">Minecraft Java</a></span>: <ul class="dataview dataview-ul dataview-result-list-ul"><li class="dataview-result-list-li"><span><a aria-label-position="top" aria-label="https://download.curseforge.com/" rel="noopener" class="external-link" href="https://download.curseforge.com/" target="_blank">Website</a></span></li><li class="dataview-result-list-li"><span><code>winget install -e Overwolf.CurseForge</code></span></li></ul></li><li><span><a aria-label-position="top" aria-label="apps/Minecraft Bedrock.md" data-href="apps/Minecraft Bedrock.md" href="apps/Minecraft Bedrock.md" class="internal-link" target="_blank" rel="noopener">Minecraft Bedrock</a></span>: <ul class="dataview dataview-ul dataview-result-list-ul"><li class="dataview-result-list-li"><span><a aria-label-position="top" aria-label="https://microsoft.com/store/apps/9NBLGGH2JHXJ" rel="noopener" class="external-link" href="https://microsoft.com/store/apps/9NBLGGH2JHXJ" target="_blank">Microsoft Store</a></span></li><li class="dataview-result-list-li"><span><code>winget install -e 9NBLGGH2JHXJ --accept-package-agreements</code></span></li></ul></li><li><span><a aria-label-position="top" aria-label="apps/Factorio.md" data-href="apps/Factorio.md" href="apps/Factorio.md" class="internal-link" target="_blank" rel="noopener">Factorio</a></span>: <ul class="dataview dataview-ul dataview-result-list-ul"><li class="dataview-result-list-li"><span><a aria-label-position="top" aria-label="https://factorio.com/download" rel="noopener" class="external-link" href="https://factorio.com/download" target="_blank">Website</a></span></li></ul></li></ul>


---


Sources:

Related:
[README](../README.md)

Tags:
