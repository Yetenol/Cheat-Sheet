---
example: Convert wikilinks to markdown
command: 
---

- **convert** wikilinks to markdown links   
    ```powershell
    $pattern = '\[\[(?<target>.*?)\]\]'
    Get-ChildItem -Filter "*.md" |
    foreach { 
        $file = $_.FullName
        $content = Get-Content -Path $file -Raw   # output as one string

        [RegEx]::Matches($content, $pattern) |   # output all regex matches
        foreach { 
            $Target = $_.Groups["target"].value
            $Match = $_.Groups[0].value
            $Encoded = $Target -replace ' ', '%20'
            $Replace = "[$Target]($Encoded)"
            $content = $content -replace [RegEx]::Escape($Match), $Replace
        }

        Set-Content -Path $file -Value $content
    }
    ```


---


Sources:

Related:

Tags:
[Applications](Applications.md)