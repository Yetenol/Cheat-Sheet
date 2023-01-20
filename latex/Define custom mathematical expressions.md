---
example: Norm
command: 
priority: 7
---

# Custom symbols

Dependecy: siunitx

- Custom **symbol**
    ```latex
    \newmathsymbol{\fE}{f_\mathrm{E}}
    ```

# Custom functions

- **Norm**
    ```latex
    \newcommand{\norm}[1]{\left\lVert{}#1\right\rVert}
    ```

- **Absolute** value
    ```latex
    \newcommand{\abs}[1]{\left\lvert{}#1\right\rvert}

## Better vectors

- **Wider vector arrows**  
    The vector arrow is as wide as the elements it spans.
    ```latex
    \renewcommand{\vec}{\vv}
    ```


---


Sources:

Related:

Tags:
[Standardize values](../notes/Standardize%20values.md)