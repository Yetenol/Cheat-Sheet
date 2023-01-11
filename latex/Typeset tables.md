# Best practices

1. Tabular environments should be nested in a **floating object** (aka flaot)
    ```latex
    \begin{table}
        \begin{⟨tabular environment⟩}
        \end{⟨tabular environment⟩}
    \end{table}
    ```

    - `⟨tabular environment⟩`: Environment defining the style and syntax of the table

2. Always provide a **caption** displayed underneath and a **label**, to cross reference in elsewhere. Horizontally center the float as well.
    ```latex
    \begin{table}
        \begin{⟨tabular environment⟩}
        \end{⟨tabular environment⟩}
        \centering % horizontally center the float
        \caption{⟨caption⟩} % title displayed below the table and in the index
        \label{tab:⟨table name⟩} % a handle to cross reference the table
    \end{table}
    ```

    - `⟨caption⟩`: Title displayed below the table and in the index
    - `⟨table name⟩`: Filename and handle to cross reference the table

3. Table floats contain many lines of text, so they are distracting in the main text. Therefore, extract each floating object into a separate file.

    1. Extract the float into a **separate file** like `floating-tables/⟨table name⟩.tex`
    2. **Request to place** the floating object at the next possible position considering the placement parameters
        ```latex
        \input{floating-tables/⟨table name⟩}
        ```
    3. Write a reference to the floating object, as it might not appear on the same page
        ```latex
        Our measurement results can be seen in Table \ref{tab:⟨table name⟩}.
        ```


# Column types

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
    \CatchFileDef{\input⟨data title⟩}{src/⟨data title⟩}{}
    \begin{table}  % or \begin{table}[⟨placement specifiers⟩]
        %%%%%%%%%% LAYOUT, META DATA %%%%%%%%%%
        \centering
        \caption{⟨caption⟩} % title displayed below the table and in the index
        \label{tab:⟨table name⟩} % handle to cross reference the table
        \begin{tabularx}{\columnwidth} % total table width
        {   %%%%%%%%%% COLUMN FORMATTING %%%%%%%%%%
            p{1.75cm} % fixed-width column
            X         % justify text, sketching column
            C         % centering text, sketching column
            X         % justify text, sketching column
        }
            \toprule     %%%%%%%%%% MULTICOLUMN HEADERS %%%%%%%%%%
            & \multicolumn{2}{c}{⟨multicolumn header⟩} 
            \\ \cmidrule(lr){2-3}   %%%%%%%%%% COLUMN HEADERS %%%%%%%%%%
            {Child} &
            {Mother} &
            {Father}
            \\ \midrule     %%%%%%%%%% TABLE BODY %%%%%%%%%%
            \input⟨data title⟩ % body file defined in first line
            \bottomrule     %%%%%%%%%% END OF BODY %%%%%%%%%%
        \end{tabularx}
    \end{table}
    ```

    - `⟨data title⟩`: File where the table's body is stored
    - `⟨placement specifiers⟩` := see [Positioning](#positioning)
    - `⟨caption⟩`: Title displayed below the table and in the index
    - `⟨table name⟩`: Filename and handle to cross reference the table
    - `⟨multicolumn header⟩` := column title that spans multiple columns

## Number table

- Use **required packages** in `setup/packages.tex`  
    ```latex
    \usepackage{siunitx}  % Aligning numbers by decimal points in table columns
    \usepackage{booktabs} % To thicken table lines
    \usepackage{multicol} % split the legend into multiple columns
    \usepackage{xcolor}   % to color columns
    \usepackage{array}
    ```

- Create **mathematical symbols** in `math/symbols.tex`  
    Globally define column titles as macros to ensure consistent symbols throughout the document.  
    ```latex
    \newmathsnippet{\⟨symbol a⟩}{f_\mathrm{E}}
    \newmathsnippet{\⟨symbol b⟩}{U_\mathrm{E}}
    \newmathsnippet{\⟨symbol c⟩}{U_\mathrm{R,pp}}
    ```

- **Table body** in `src/measured-values.tex`  
    ```latex
    % f_E   & U_E      & U_Rpp
    453.116 & 382.657  & -426418 \\
    88.760  & 245.946  & 332002 \\
    ```

- **Table columns, design** in `table/numbers.tex`
    ```latex
    CatchFileDef{\input⟨data title⟩}{src/measured-values}{}
    \begin{table}  % or \begin{table}[⟨placement specifiers⟩]
        %%%%%%%%%% LAYOUT, META DATA %%%%%%%%%%
        \centering
        \caption{⟨caption⟩} % or \caption[⟨listoftables caption⟩]{⟨caption⟩}
        \label{tab:⟨table name⟩}
        \sisetup{table-auto-round = true}
        \begin{tabular}[]
        {   %%%%%%%%%% COLUMN FORMATTING %%%%%%%%%%
            S[table-format = -3.0e-1] % column A
            S[table-format =  3.1] % column B
            S[table-format = -2.e1, color = orange] % column C
        }
            \toprule     %%%%%%%%%% MULTICOLUMN HEADERS %%%%%%%%%%
            & \multicolumn{2}{c}{⟨multicolumn header⟩} 
            \\ \cmidrule(lr){2-3}   %%%%%%%%%% COLUMN HEADERS %%%%%%%%%%
            {\⟨symbol a⟩* in \unit{V}} &
            {\⟨symbol b⟩* in \unit{\micro\second\per\liter}} &
            {\⟨symbol c⟩* in \unit{kg.\frac{m}{s}}}
            \\ \midrule     %%%%%%%%%% TABLE BODY %%%%%%%%%%
            \input⟨data title⟩  % body file defined in first line
            \bottomrule     %%%%%%%%%% END OF BODY %%%%%%%%%%
        \end{tabular}
        \begin{multicols}{2}   % number of legend columns
            \begin{itemize}     %%%%% COLUMN LEGEND %%%%%
                \item[\⟨symbol a⟩*] Frequenz
                \item[\⟨symbol b⟩*] Eingangsspannung
                \item[\⟨symbol c⟩*] Spannung über den Widerstand
            \end{itemize}     %%%%% END OF LEGEND %%%%%
        \end{multicols}
    \end{table}
    ```

    - `⟨symbol a⟩`, `⟨symbol b⟩`, `⟨symbol c⟩`: Column titles as mathematical expression
    - `⟨data title⟩`: File where the table's body is stored
    - `⟨placement specifiers⟩` := see [Positioning](#positioning)
    - `⟨caption⟩`: Title displayed below the table and in the index
    - `⟨table name⟩`: Filename and handle to cross reference the table
    - `⟨multicolumn header⟩` := column title that spans multiple columns

## Align custom delimiter tables

- Use **required packages** in `setup/packages.tex`  
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
    CatchFileDef{\input⟨data title⟩}{src/measured-values}{}
    \begin{table}  % or \begin{table}[⟨placement specifiers⟩]
        %%%%%%%%%% LAYOUT, META DATA %%%%%%%%%%
        \centering
        \caption{⟨caption⟩} % or \caption[⟨listoftables caption⟩]{⟨caption⟩}
        \label{tab:⟨label⟩}
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
            \input⟨ipaddresses⟩ % body file defined in first line
            \bottomrule     %%%%%%%%%% END OF BODY %%%%%%%%%%
        \end{tabular}
    \end{table}
    ```

- alternatively use `\usepackage{dcolumn}`


---


Sources:
2023-01-06: [Tables - Overleaf, Online LaTeX Editor](https://www.overleaf.com/learn/latex/Tables)
2023-01-10: [tables - What is the difference between tabular, tabular* and tabularx environments? - TeX - LaTeX Stack Exchange](https://tex.stackexchange.com/questions/341205/what-is-the-difference-between-tabular-tabular-and-tabularx-environments)
2023-01-10: [LaTeX tables - Tutorial with code examples - LaTeX-Tutorial.com](https://latex-tutorial.com/tutorials/tables/)

Related:
[Floating Bodies](Floating%20Bodies.md)

Tags:
