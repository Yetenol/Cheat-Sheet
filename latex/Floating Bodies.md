---
example: Images
command: \begin{figure}[htbp]
---
# Placement Specifiers

```latex
\begin{FLOAT-ENVIRONMENT}[PLACEMENT-SPECIFIERS]
\end{FLOAT-ENVIRONMENT}
```

| Specifier          | Name    | Add placement option                                                              |
| ------------------ | ------- | --------------------------------------------------------------------------------- |
| _empty_ <br> `tbp` | default | Put if at the top, bottom of the _next available_ page or on a floats-only page.  |
| `!`                | force   | Force the following settings, without considerung most of the internal parameter. |
| `h`                | here    | Put it exactly where we say it should go.                                         |
| `t`                | top     | Put it at the top of the _next available_ page.                                   |
| `b`                | bottom  | Put it at the bottom of the _next available_ page.                                |
| `p`                | page    | Put it on a special page containing only floats.                                  |

Example

```latex
\begin{figure}[htbp]
\end{figure}
```

# Images

```latex
\begin{figure}  % or \begin{figure}[PLACEMENT-SPECIFIERS]
    \centering
    \caption{CAPTION}  % or \caption[LISTOFTABLES-CAPTION]{CAPTION}
    \label{fig:LABEL}
    \includegraphics[width=0.75\columnwidth]{FILENAME}
\end{figure}
```

- `CAPTION` := displayed name of the figure
- `LISTOFTABLES-CAPTION` := (optional) replaces the entry in the list of figures with a shorter version
- `LABEL` := label to reference the figure using `\ref{fig:LABEL}`
- `FILENAME` := file path (with extension) of the image 

# Source Code Listings

```latex
\begin{figure}  % or \begin{figure}[PLACEMENT]
    \centering
    \lstset{caption = {CAPTION}}
    \lstset{label = code:LABEL}
    \lstinputlisting[language = matlab]{FILENAME}
\end{figure}
```

# Directories

```latex
\listoftables       % Tabellenverzeichnis
\listoffigures      % Abbildungsverzeichnis
\lstlistoflistings  % Codelistenverzeichnis
```


---
#latex/standardizePlaceholders 

Sources:

Related:

Tags:
