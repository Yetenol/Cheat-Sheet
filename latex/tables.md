# [⌂](../README.md) › [LaTeX](../README.md#latex) › **Tables**

# Column types

> Requirement [LaTeX.table](https://github.com/Yetenol/latex.table)

|                       | Content            | Width               | Alignment       | Availability                                          |
| --------------------- | ------------------ | ------------------- | --------------- | ----------------------------------------------------- |
| `L`                   | paragraph          | equally distributed | left            | [LaTeX.table](https://github.com/Yetenol/latex.table) |
| `R`                   | paragraph          | equally distributed | right           | [LaTeX.table](https://github.com/Yetenol/latex.table) |
| `C`                   | paragraph          | equally distributed | center          | [LaTeX.table](https://github.com/Yetenol/latex.table) |
| `X`                   | paragraph          | equally distributed | justify         | tabularx package                                      |
| `p{1cm}`              | paragraph          | fixed               | left            | built-in                                              |
| `p`                   | single line        | auto-fit to content | left            | built-in                                              |
| `m{}`                 | paragraph          | fixed               | vertical center | built-in                                              |
| `S[table-format=3.1]` | number/single line | fixed               | decimal point   | siunitx package                                       |
| `S`                   | number/single line | auto-fit to content | decimal point   | siunitx package                                       |

## Adjustable-width columns

> Requirement [LaTeX.table](https://github.com/Yetenol/latex.table)  
> CAPITAL letters are ⟨placeholders⟩

```latex
\begin{table} % \begin{table}[⟨positioning⟩]
    %%%%%%%%%% LAYOUT, META DATA %%%%%%%%%%
    \centering
    \caption{⟨caption⟩} % \caption[⟨list of tables caption⟩]{⟨caption⟩}
    \label{tab:⟨label name⟩}
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
        & \multicolumn{2}{c}{multicolumn header⟩} 
        \\ \cmidrule(lr){2-3}   % partial horizontal line
        {\COLUMNA* ⟨title supplement⟩} &
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

- `⟨positioning⟩` := see [Positioning](#positioning)
- `⟨caption⟩` := displayed name of the figure
- `⟨list of tables caption⟩` := (optional) replaced the entry in the list of figures with a summary
- `⟨label name⟩` := label to reference the figure using `\ref{fig:⟨label name⟩}`
- `⟨multicolumn header⟩` := column title that spans multiple columns
- `⟨title supplement⟩` optional := short supplement like sorting order that is only displayed in the table header


## Formatting numbers in tables

## Built-in work around

> Align numbers by splitting table cells at the decimal point

```latex
\begin{tabular}{c r @{.} l}
Pi expression &
\multicolumn{2}{c}{Value} \\
\hline
$\pi$           &     3&1416 \\
$\pi^\pi$       &    36&46   \\
$(\pi^\pi)^\pi$ & 80662&7    \\
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