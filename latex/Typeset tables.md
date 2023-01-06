CAPITAL letters are ⟨placeholders⟩

# Best practices

1. Tabular environments should be nested in a **floating object** called `table`. 
    ```latex
    \begin{table}
        \begin{TABULAR-ENVIRONMENT}
        \end{TABULAR-ENVIRONMENT}
    \end{table}
    ```

2. Always provide a **caption** displayed underneath and a **label**, to cross reference in elsewhere. Horizontally center the float as well.
    ```latex
    \begin{table}
        \begin{TABULAR-ENVIRONMENT}
        \end{TABULAR-ENVIRONMENT}
        \centering % horizontally center the float
        \caption{CAPTION} % title displayed below the table and in the index
        \label{tab:LABEL} % a handle to cross reference the table
    \end{table}
    ```

3. Table floats contain many lines of text, so they are distracting in the main text. Therefore, extract each floating object into a separate file.

main chapter file like `chapters/measurement.tex`  

```latex
My friends' parents \ref{tab:LABEL}

\input{table-floats/values-measured}
```

floating object in `table-floats/values-measured.tex`

```latex
\begin{table}
    \begin{tabular}[]{}
        Child   & Mother & Father \\
        Alysha  & Lyra   & Hans \\
        Klaus   & Rosy   & Dieter \\
    \end{tabular}
    \centering
    \caption{My friends' parents}
    \label{tab:my-friends-parents}
\end{table}
```

# Column types

> Requirement [LaTeX.table](https://github.com/Yetenol/latex.table)

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

# Table types

## Auto-stretching columns table

Dependency [LaTeX.table](https://github.com/Yetenol/latex.table)

- **Table body** in `resources/children-list.tex`  
    ```latex
    % Child & Mother & Father
    Alysha  & Lyra   & Hans \\
    Klaus   & Rosy   & Dieter \\
    ```

- **Table columns, design** in `table/auto-stretch.tex`
    ```latex
    \CatchFileDef{\inputCHILDRENLIST}{src/children-list}{}
    \begin{table}  % or \begin{table}[FLOAT-POSITIONING]
        %%%%%%%%%% LAYOUT, META DATA %%%%%%%%%%
        \centering
        \caption{CAPTION} % or \caption[LISTOFTABLES-CAPTION]{CAPTION}
        \label{tab:LABEL}
        \begin{tabularx}{\columnwidth} % total table width
        {   %%%%%%%%%% COLUMN FORMATTING %%%%%%%%%%
            p{1.75cm} % fixed-width column
            X         % justify text, sketching column
            C         % centering text, sketching column
            X         % justify text, sketching column
        }
            \toprule     %%%%%%%%%% MULTICOLUMN HEADERS %%%%%%%%%%
            & \multicolumn{2}{c}{Parents} 
            \\ \cmidrule(lr){2-3}   %%%%%%%%%% COLUMN HEADERS %%%%%%%%%%
            {Child} &
            {Mother} &
            {Father}
            \\ \midrule     %%%%%%%%%% TABLE BODY %%%%%%%%%%
            \inputCHILDRENLIST % body file defined in first line
            \bottomrule     %%%%%%%%%% END OF BODY %%%%%%%%%%
        \end{tabularx}
    \end{table}
    ```

- `⟨positioning⟩` := see [Positioning](#positioning)
- `⟨caption⟩` := displayed name of the figure
- `⟨list of tables caption⟩` := (optional) replaced the entry in the list of figures with a summary
- `⟨label name⟩` := label to reference the figure using `\ref{fig:⟨label name⟩}`
- `⟨multicolumn header⟩` := column title that spans multiple columns
- `⟨title supplement⟩` optional := short supplement like sorting order that is only displayed in the table header

## Number table


- **Package requirements** in `setup/packages.tex`  
    `\input` the file into the [document preamble](Troubleshoot%20and%20get%20help.md#preamble).
    ```latex
    \usepackage{siunitx}  % Aligning numbers by decimal points in table columns
    \usepackage{booktabs} % To thicken table lines
    \usepackage{multicol} % split the legend into multiple columns
    \usepackage{xcolor}   % to color columns
    \usepackage{array}
    ```

- **Mathematical symbols** in `math/symbols.tex`  
    Globally define column titles as macros to ensure consistent symbols throughout the document.  
    `\input` the file into the [document preamble](Troubleshoot%20and%20get%20help.md#preamble).
    ```latex
    \newmathsnippet{\SYMBOLA}{f_\mathrm{E}}
    \newmathsnippet{\SYMBOLB}{U_\mathrm{E}}
    \newmathsnippet{\SYMBOLC}{U_\mathrm{R,pp}}
    ```

- **Table body** in `src/measured-values.tex`  
    ```latex
    % f_E   & U_E      & U_Rpp
    453.116 & 382.657  & -426418 \\
    88.760  & 245.946  & 332002 \\
    ```

- **Table columns, design** in `table/numbers.tex`
    ```latex
    CatchFileDef{\inputMEASUREDVALUES}{src/measured-values}{}
    \begin{table}  % or \begin{table}[FLOAT-POSITIONING]
        %%%%%%%%%% LAYOUT, META DATA %%%%%%%%%%
        \centering
        \caption{CAPTION} % or \caption[LISTOFTABLES-CAPTION]{CAPTION}
        \label{tab:LABEL}
        \sisetup{table-auto-round = true}
        \begin{tabular}[]
        {   %%%%%%%%%% COLUMN FORMATTING %%%%%%%%%%
            S[table-format = -3.0e-1] % column A
            S[table-format =  3.1] % column B
            S[table-format = -2.e1, color = orange] % column C
        }
            \toprule     %%%%%%%%%% MULTICOLUMN HEADERS %%%%%%%%%%
            & \multicolumn{2}{c}{Group} 
            \\ \cmidrule(lr){2-3}   %%%%%%%%%% COLUMN HEADERS %%%%%%%%%%
            {\SYMBOLA* in \unit{V}} &
            {\SYMBOLB* in \unit{\micro\second\per\liter}} &
            {\SYMBOLC* in \unit{kg.\frac{m}{s}}}
            \\ \midrule     %%%%%%%%%% TABLE BODY %%%%%%%%%%
            \inputMEASUREDVALUES  % body file defined in first line
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


## Align custom delimiter tables

- **Package requirements** in `setup/packages.tex`  
    `\input` the file into the [document preamble](Troubleshoot%20and%20get%20help.md#preamble).
    ```latex
    \usepackage{booktabs} % To thicken table lines
    ```

- **Table body** in `src/ip-addresses.tex`  
    ```latex
    % Computername & 255&255&255&255 (Ip address)
    Mikes-Computer & 10 & 0 & 0 & 14 % =10.0.0.14
    Peters-Phone   & 192&168&179&  2 % =192.168.179.2
    ```

- **Table columns, design** in `table/network.tex`
    ```latex
    CatchFileDef{\inputIPADDRESSES}{src/measured-values}{}
    \begin{table}  % or \begin{table}[FLOAT-POSITIONING]
        %%%%%%%%%% LAYOUT, META DATA %%%%%%%%%%
        \centering
        \caption{CAPTION} % or \caption[LISTOFTABLES-CAPTION]{CAPTION}
        \label{tab:LABEL}
        \begin{tabular}
        {   %%%%%%%%%% COLUMN FORMATTING %%%%%%%%%%
            c      % Computername
            r @{.} % 192.
            r @{.} %     168.
            r @{.} %         179.
            r      %             1
        }
            \toprule %%%%%%%%%% COLUMN HEADERS %%%%%%%%%%
            Computername &
            \multicolumn{4}{c}{Ip address}
            \\ \midrule     %%%%%%%%%% TABLE BODY %%%%%%%%%%
            \inputIPADDRESSES % body file defined in first line
            \bottomrule     %%%%%%%%%% END OF BODY %%%%%%%%%%
        \end{tabular}
    \end{table}
    ```

- alternatively use `\usepackage{dcolumn}`


---


Sources:
2023-01-06: [Tables - Overleaf, Online LaTeX Editor](https://www.overleaf.com/learn/latex/Tables)

Related:
[Floating Bodies](Floating%20Bodies.md)

Tags:
