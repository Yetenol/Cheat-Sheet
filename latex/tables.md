# [⌂](../README.md) › [LaTeX](../README.md#latex)) › **Tables**


```latex
\usepackage{tabularx}

\newcolumntype{L}{>{\raggedright\arraybackslash}X}
\newcolumntype{R}{>{\raggedleft\arraybackslash}X}
\newcolumntype{C}{>{\centering\arraybackslash}X}
```

```latex
\begin{table}[]
    \centering
    \caption{CAPTION}
    \label{tab:TABLE_LABEL}
    \begin{tabularx}{TABLE_WIDTH} {
    | >{\raggedright\arraybackslash}ALLIGNMENT 
    | >{\raggedleft\arraybackslash}X
    | >{\centering\arraybackslash}X 
    | >{\raggedright\arraybackslash}X 
    | }
        \hline
        Datum & Deutsche Rentenversicherung Bund & Übertragungsmedium & Anton Pusch \\
        \hline
        24-08-2021 & & ePostfach mit Personalausweis & Freiwilliges \\
        \hline
         item 11 & item 12 & item 13 & \\
         \hline
         item 21  & item 22  & item 23 & \\
        \hline
    \end{tabularx}
\end{table}
```

`ALLIGNMENT` := 