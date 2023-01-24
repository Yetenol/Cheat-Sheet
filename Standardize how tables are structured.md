---
dg-publish: true
example: Extract table to seperate files
command: 
priority: 1
---

1. Tabular environments should be nested in a **floating object** aka flaot.    
    see [[Floating objects]]
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


---


Sources:

Related:

Tags:
[[Standardize graphical elements]]