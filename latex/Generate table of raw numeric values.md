Dependency: [pgfplotstable](https://texdoc.org/serve/pgfplotstable/0)

# Usage

- use dependencies in `setup/packages.tex`
```latex
\usepackage{booktabs}
\usepackage{pgfplotstable}
```

- setup header layout in `setup/layout.tex`
```latex
\pgfplotstableset{
    every head row/.style = {
        before row=\toprule, 
        after row=\midrule
    },
    every last row/.style = {
        after row = \bottomrule
    },
    col sep = comma, 
    header = true
}
```

- typeset an **inline table**
```latex
\begin{center}
\pgfplotstabletypeset{resources/children-raw.tex}
\end{center}
```

- typeset a **floating table**
```latex
\begin{table}
    \pgfplotstabletypeset{resources/phasenfrequenzgang.csv}
    \centering
    \caption{Table generated from .csv}
    \label{tab:csv-generated}
\end{table}
```


---
#research/addExamples 

Sources:

Related:
[Typeset tables](Typeset%20tables.md)

Tags:
