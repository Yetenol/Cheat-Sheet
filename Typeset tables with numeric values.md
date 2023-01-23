---
dg-publish: true
example: Legend below the table defines the symbols used
command: 'S[table-format = -3.0e-1]'
priority: 7
---

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

# Align custom delimiter tables

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
[[Floating objects]]

Tags:
[[Standardize graphical elements]]