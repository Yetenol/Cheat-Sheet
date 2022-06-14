# Tables
[⌂](../README.md) › [LaTeX](../README.md#latex) ›

# Column types

> Requirement [LaTeX.table](https://github.com/Yetenol/latex.table)

|                       | Content            | Width               | Alignment       |
| --------------------- | ------------------ | ------------------- | --------------- |
| `L`                   | paragraph          | equally distributed | left            |
| `R`                   | paragraph          | equally distributed | right           |
| `C`                   | paragraph          | equally distributed | center          |
| `X`                   | paragraph          | equally distributed | justify         |
| `p{1cm}`              | paragraph          | fixed               | left            |
| `p`                   | single line        | auto-fit to content | left            |
| `m{}`                 | paragraph          | fixed               | vertical center |
| `S[table-format=3.1]` | number/single line | fixed               | decimal point   |
| `S`                   | number/single line | auto-fit to content | decimal point   |

## Adjustable-width columns

> Requirement [LaTeX.table](https://github.com/Yetenol/latex.table)

```latex
\begin{table}%[POSITIONING]
    %%%%%%%%%% LAYOUT, META DATA %%%%%%%%%%
    \centering
    \caption{CAPTION} % \caption[LISTOFTABLES-CAPTION]{CAPTION}
    \label{tab:LABEL}
    %%%%%%%%%% COLUMN NAMES %%%%%%%%%%
    \def\COLUMNA*{Person}
    \def\COLUMNB*{Father}
    \def\COLUMNC*{Mother}
    %%%%%%%%%% COLUMN FORMATTING %%%%%%%%%%
    \begin{tabularx}{\columnwidth}
    {
        p{1.75cm} % fixes width
        X % Justify text
        C % centering text
        X % 
    }
        \toprule     %%%%%%%%%% TABLE HEADER %%%%%%%%%%
        & \multicolumn{2}{c}{Parents} 
        \\ \cmidrule(lr){2-3}   % partial horizontal line
        {\COLUMNA* (a-z)} &
        {\COLUMNB*} &
        {\COLUMNC*}
        \\ \midrule     %%%%%%%%%% TABLE BODY %%%%%%%%%%
            Dieter & Klaus & Hans \\
        \bottomrule     %%%%%%%%%% END OF BODY %%%%%%%%%%
    \end{tabularx}
    \begin{multicols}{2}   % number of legend columns
        \begin{enumerate}     %%%%% COLUMN LEGEND %%%%%
            \item[\COLUMNA*] Frequenz
            \item[\COLUMNB*] Eingangsspannung
            \item[\COLUMNC*] Spannung über den Widerstand
        \end{enumerate}     %%%%% END OF LEGEND %%%%%
    \end{multicols}
\end{table}
```


## Align decimal points

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
    \caption{CAPTION} % \caption[LISTOFTABLES-CAPTION]{CAPTION}
    \label{tab:LABEL}
    \sisetup{table-auto-round = true}
    %%%%%%%%%% COLUMN SYMBOLS %%%%%%%%%%
    \def\SYMBOLA*{\ensuremath{\alpha}}
    \def\SYMBOLB*{\ensuremath{\beta}}
    \def\SYMBOLC*{\ensuremath{\gamma}}
    %%%%%%%%%% COLUMN FORMATTING %%%%%%%%%%
    \begin{tabular}[]{
        S[table-format = +3.0e-1] % column A
        S[table-format =  3.1] % column B
        S[table-format = +2.e1, color = orange] % column C
    }
        \toprule     %%%%%%%%%% TABLE HEADER %%%%%%%%%%
        & \multicolumn{2}{c}{Group} 
        \\ \cmidrule(lr){2-3}   % partial horizontal line
        {\SYMBOLA* in \unit{V}} &
        {\SYMBOLB* in \unit{\micro\second\per\liter}} &
        {\SYMBOLC* in \unit{kg.\frac{m}{s}}}
        \\ \midrule     %%%%%%%%%% TABLE BODY %%%%%%%%%%
        453.116 & 382.657  & -426418 \\
        88.760  & 245.946 & 332002 \\
        \bottomrule     %%%%%%%%%% END OF BODY %%%%%%%%%%
    \end{tabular}
    \begin{multicols}{2}   % number of legend columns
        \begin{itemize}     %%%%% COLUMN LEGEND %%%%%
            \item[\SYMBOLA*] Frequenz
            \item[\SYMBOLB*] Eingangsspannung
            \item[\SYMBOLC*] Spannung über den Widerstand
        \end{itemize}     %%%%% END OF LEGEND %%%%%
    \end{multicols}
\end{table}
```