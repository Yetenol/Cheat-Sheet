---
dg-publish: false
example: 
command: 
priority: 
---

# Query types

1.  **TABLE**: The traditional view type; one row per data point, with several columns of field data.
2.  **LIST**: A list of pages which match the query. You can output a single associated value for each page.
3.  **TASK**: A list of tasks whose pages match the given query.
4.  **CALENDAR**: A calendar view displaying each hit via a dot on its reffered date

## General Format

```
TABLE|LIST|TASK
    <field> [AS "Column Name"],
    <field>, 
    ...,
    <field> 
FROM <source>
WHERE <expression>
SORT <expression> [ASC/DESC]
... other data commands
```

## Internal functions

- [Functions - Dataview](https://blacksmithgu.github.io/obsidian-dataview/reference/functions/#choicebool-left-right)

# Format output

Hide bullet point and remove indentation from first level of dataview results using a custom css snippet
```css
/* no need the previous padding adjustment if using Minimal */
ul.dataview.list-view-ul {
	list-style: none;
    padding-left: 0;
}

/* reinstate the bullet to "subpoints" but also adjust the position
   for the bullet to be on the inside (for compatibility with Minimal) */
ul.dataview.dataview-ul.dataview-result-list-ul {
	list-style: disc;
	/* margin-left: 1.5rem; */
}
```

Hide bullet point and remove indentation from first level of all lists
```css
/* no need the previous padding adjustment if using Minimal */
ul {
	list-style: none;
    padding-left: 0;
}

/* reinstate the bullet to "subpoints" but also adjust the position
   for the bullet to be on the inside (for compatibility with Minimal) */
ul ul {
	list-style: disc;
	margin-left: 1.5rem;
}
```

---

#research/addExamples

Sources:
- 2023-01-23: [Can we make a cleaner Dataview list? - Resolved help - Obsidian Forum](https://forum.obsidian.md/t/can-we-make-a-cleaner-dataview-list/32843/10)
- 2023-01-05: [Structure of a Query - Dataview](https://blacksmithgu.github.io/obsidian-dataview/queries/structure/)
- 2023-01-17: [Embed files - Obsidian-docs](https://jackiegeek.gitee.io/obsidian-docs/fr/How%20to/Embed%20files/)

Related:
[[obsidian]]

Tags:
[[Languages and Encodings]]