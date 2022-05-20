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
\begin{tabularx}{\SYMBOLwidth}{X|p{1.7cm}|C|}
    
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


## Data tables

```latex
\usepackage{siunitx} % Aligning numbers by decimal points in table columns
\usepackage{booktabs} % To thicken table lines
\usepackage{multicol} % split the legend into multiple columns
\usepackage{xcolor} % to color columns
\usepackage{array}
```

```latex
\begin{table}%[POSITIONING]
    %%%%%%%%%% LAYOUT, META DATA %%%%%%%%%%
    \centering
    \caption[LISTOFTABLES-CAPTION]{CAPTION}
    \label{fig:TABLE_LABEL}
    \sisetup{table-auto-round = true}
    %%%%%%%%%% COLUMN SYMBOLS %%%%%%%%%%
    \def\SYMBOLA*{$\alpha$}
    \def\SYMBOLB*{$\beta$}
    \def\SYMBOLC*{$\gamma$}
    %%%%%%%%%% COLUMN FORMATTING %%%%%%%%%%
    \begin{tabular}[]{
        S[table-format = -3.0e-1] % column A
        S[table-format =  3.1] % column B
        S[table-format =  2.e1, color = orange] % column C
    }
        \toprule     %%%%%%%%%% TABLE HEADER %%%%%%%%%%
        & \multicolumn{2}{c}{Group} \\
        \cmidrule(lr){2-3}   % partial horizontal line
        {\SYMBOLA* in \unit{V}} &
        {\SYMBOLB* in \unit{\micro\second/l}} &
        {\SYMBOLC* in \unit{kg.\frac{m}{s}}}
        \\ \midrule     %%%%%%%%%% TABLE BODY %%%%%%%%%%
        453.116 & 382.657  & -426418 \\
        88.760  & -245.946 & 332002 \\
        \bottomrule     %%%%%%%%%% END OF BODY %%%%%%%%%%
    \end{tabular}
    \begin{multicols}{2}   % number of legend columns
        \begin{enumerate}     %%%%% COLUMN LEGEND %%%%%
            \item[\SYMBOLA*] Frequenz
            \item[\SYMBOLB*] Eingangsspannung
            \item[\SYMBOLC*] Spannung über den Widerstand
        \end{enumerate}     %%%%% END OF LEGEND %%%%%
    \end{multicols}
\end{table}
```