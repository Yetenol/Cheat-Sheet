---
categoryName: Subsystem
priority: 10
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

<ul class="dataview list-view-ul"><li><span><a aria-label-position="top" aria-label="apps/WSATools.md" data-href="apps/WSATools.md" href="apps/WSATools.md" class="internal-link" target="_blank" rel="noopener">WSATools</a></span>: <ul class="dataview dataview-ul dataview-result-list-ul"><li class="dataview-result-list-li"><span><a aria-label-position="top" aria-label="https://microsoft.com/store/apps/9n4p75dxl6fg" rel="noopener" class="external-link" href="https://microsoft.com/store/apps/9n4p75dxl6fg" target="_blank">Microsoft Store</a></span></li><li class="dataview-result-list-li"><span><code>winget install -e 9N4P75DXL6FG --accept-package-agreements</code></span></li></ul></li><li><span><a aria-label-position="top" aria-label="apps/Windows Subsystem for Linux.md" data-href="apps/Windows Subsystem for Linux.md" href="apps/Windows Subsystem for Linux.md" class="internal-link" target="_blank" rel="noopener">Windows Subsystem for Linux</a></span>: <ul class="dataview dataview-ul dataview-result-list-ul"><li class="dataview-result-list-li"><span><a aria-label-position="top" aria-label="https://microsoft.com/store/apps/9nblggh4msv6" rel="noopener" class="external-link" href="https://microsoft.com/store/apps/9nblggh4msv6" target="_blank">Microsoft Store</a></span></li><li class="dataview-result-list-li"><span><code>winget install -e 9NBLGGH4MSV6 --accept-package-agreements</code></span></li></ul></li><li><span><a aria-label-position="top" aria-label="apps/Windows Subsystem for Android.md" data-href="apps/Windows Subsystem for Android.md" href="apps/Windows Subsystem for Android.md" class="internal-link" target="_blank" rel="noopener">Windows Subsystem for Android</a></span>: <ul class="dataview dataview-ul dataview-result-list-ul"><li class="dataview-result-list-li"><span><a aria-label-position="top" aria-label="https://microsoft.com/store/apps/9p3395vx91nr" rel="noopener" class="external-link" href="https://microsoft.com/store/apps/9p3395vx91nr" target="_blank">Microsoft Store</a>, <a aria-label-position="top" aria-label="https://allthings.how/how-to-download-windows-subsystem-for-android-without-microsoft-store-msixbundle/" rel="noopener" class="external-link" href="https://allthings.how/how-to-download-windows-subsystem-for-android-without-microsoft-store-msixbundle/" target="_blank">Website</a></span></li><li class="dataview-result-list-li"><span><code>winget install -e 9P3395VX91NR --accept-package-agreements</code></span></li></ul></li><li><span><a aria-label-position="top" aria-label="apps/OpenInWSA.md" data-href="apps/OpenInWSA.md" href="apps/OpenInWSA.md" class="internal-link" target="_blank" rel="noopener">OpenInWSA</a></span>: <ul class="dataview dataview-ul dataview-result-list-ul"><li class="dataview-result-list-li"><span><a aria-label-position="top" aria-label="https://github.com/efraimbart/OpenInWSA/releases/latest/download/OpenInWSA.exe" rel="noopener" class="external-link" href="https://github.com/efraimbart/OpenInWSA/releases/latest/download/OpenInWSA.exe" target="_blank">Github</a></span></li></ul></li></ul>


---


Sources:

Related:
[README](../README.md)

Tags:
