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
FROM "languages"
```

-   [autohotkey](languages/autohotkey.md):
    -   Get Program stdout
    -   `Shell := ComObjCreate("WScript.Shell")`
-   [java](languages/java.md):
    
-   [Languages and Encodings](languages/Languages%20and%20Encodings.md):
    
-   [Dataview](languages/Dataview.md):
    
-   [git](languages/git.md):
    -   Delete binary from history
    -   `git clone git@github.com:Yetenol/⟨repository⟩.git`
-   [markdown](languages/markdown.md):
    
-   [parameter-passing](languages/parameter-passing.md):
    
-   [Regular expressions](languages/Regular%20expressions.md):
    -   Quantifiers
    -   `(?in)user:(?<name>\S*)\s*key:(?<pwd>\S*)`
-   [Sort or hide files using unicode characters](languages/Sort%20or%20hide%20files%20using%20unicode%20characters.md):
    
-   [Useful functions for Minecraft datapacks and mcfunctions](languages/Useful%20functions%20for%20Minecraft%20datapacks%20and%20mcfunctions.md):
    -   Leash Decorations
    -   `kill   e[type=item,nbt={Item:{id:"minecraft:wool"}}]`
-   [GDB Command Line Arguments](languages/GDB%20Command%20Line%20Arguments.md):
    -   Examinate Variables
    -   `break`
-   [RegEx implementation in .Net](languages/RegEx%20implementation%20in%20.Net.md):