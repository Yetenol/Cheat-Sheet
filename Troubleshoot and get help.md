---
dg-publish: true
example: [ Cheat sheets, Package Documentation ]
command: '\PackageError {⟨package name⟩} {⟨error text⟩} {}'
priority: 1
---

# View user guide of a specific packages  
 
- by adding a custom search engine to your browser
    ```
    http://texdoc.org/serve/%s/0
    ```
- by visiting **[texdoc.org](https://texdoc.org/index.html)**
- by running the following as long as LaTeX is installed  
    `texdoc ⟨package name⟩`
- by visiting **[ctan.org](https://ctan.org/)**

# Highlight overfull conflicts

- by enabling draft mode in the preamble
    ```latex
    \documentclass[draft]{article}
    ```
- only **check syntax**  
    by supressing the PDF creation in the preamble  
    Dependency: syntonly
    ```latex
    \syntaxonly
    ```
- **throw an error** for a specific package
    ```latex
    \PackageError {⟨package name⟩} {⟨error text⟩} {}
    ```

# Print cheat sheets

- [LATEX quick reference](https://icl.utk.edu/~mgates3/docs/latex.pdf)
- [A quick guide to LaTeX](https://www.overleaf.com/latex/templates/a-quick-guide-to-latex/fghqpfgnxggz.pdf)
- [LaTeX Cheat Sheet](https://wch.github.io/latexsheet/latexsheet-a4.pdf)


---


Sources:

Related:

Tags:
[[LaTeX]]