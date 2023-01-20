---
example: [ Content, Width, Alignment ]
command: [ L, X, S ]
priority: 9
---

|                       | Content            | Width               | Alignment       | Dependency                                            |
| --------------------- | ------------------ | ------------------- | --------------- | ----------------------------------------------------- |
| `L`                   | paragraph          | equally distributed | left            | [LaTeX.table](https://github.com/Yetenol/latex.table) |
| `R`                   | paragraph          | equally distributed | right           | [LaTeX.table](https://github.com/Yetenol/latex.table) |
| `C`                   | paragraph          | equally distributed | center          | [LaTeX.table](https://github.com/Yetenol/latex.table) |
| `X`                   | paragraph          | equally distributed | justify         | [tabularx](https://texdoc.org/serve/tabularx/0)       |
| `p{1cm}`              | paragraph          | fixed               | left            | built-in                                              |
| `p`                   | single line        | auto-fit to content | left            | built-in                                              |
| `m{}`                 | paragraph          | fixed               | vertical center | built-in                                              |
| `S[table-format=3.1]` | number/single line | fixed               | decimal point   | [siunitx](https://texdoc.org/serve/siunitx/0)         |
| `S`                   | number/single line | auto-fit to content | decimal point   | [siunitx](https://texdoc.org/serve/siunitx/0)         |
#research/addContent 


---


Sources:

Related:

Tags:
[Standardize graphical elements](../Standardize%20graphical%20elements.md)