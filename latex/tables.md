# [⌂](../README.md) › [LaTeX](../README.md#latex) › **Tables**

## TABULARX Set table width

```latex
\usepackage{tabularx}
```

```
\newcolumntype{L}{>{\raggedright\arraybackslash}X}
\newcolumntype{R}{>{\raggedleft\arraybackslash}X}
\newcolumntype{C}{>{\centering\arraybackslash}X}
```

```latex
\begin{center}
\begin{tabularx}{\columnwidth}{X|p{1.7cm}|C|}
    
\end{tabularx}
\end{center}
```

| .      | Width               | Alignment      | Content   |
| ------ | ------------------- |
| L      | equally distributed | left-aligned   | paragraph |
| R      | equally distributed | right-aligned  | paragraph |
| X      | equally distributed | center-aligned | paragraph |
| p{1cm} | fixed               | left-aligned   | paragraph |
| m{}    | fixed               |

`ALLIGNMENT` := 


## Allign decimal points

```latex
\begin{tabular}{c r @{.} l}
Pi expression &
\multicolumn{2}{c}{Value} \\
\hline
$\pi$ & 3&1416 \\
$\pi^{\pi}$ & 36&46 \\
$(\pi^{\pi})^{\pi}$ & 80662&7 \\
\end{tabular}
```

- alternatively use `\usepackage{dcolumn}`