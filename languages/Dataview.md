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




---
#research/addExamples

Sources:
- 2023-01-05: [Structure of a Query - Dataview](https://blacksmithgu.github.io/obsidian-dataview/queries/structure/)

Related:
[obsidian](../applications/obsidian.md)

Tags:
