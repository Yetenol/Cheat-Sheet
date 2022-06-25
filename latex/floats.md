# Floating Bodies
[⌂](../README.md) › [LaTeX](../README.md#latex) ›
- [Positioning](#positioning)
- [Add Images](#add-images)
- [Add List Of Figures](#add-list-of-figures)

## Placement Specifiers

```latex
\begin{figure}[htbp] % or table
\end{figure}
```

- default `tbp`

| .   | Name   | Placement Permissions                                                            |
| --- | ------ | -------------------------------------------------------------------------------- |
| `!` | force  | Force the following settings, without considerung most of the internal parameter |
| `h` | here   | Put it exactly where we say it should go.                                        |
| `t` | top    | Put it at the top of the _next available_ page.                                  |
| `b` | bottom | Put it at the bottom of the _next available_ page.                               |
| `p` | page   | Put it on a special page containing only floats.                                 |

## [Tables ›](tables.md)

## Images

```latex
\begin{figure}  % or \begin{figure}[PLACEMENT]
    \centering
    \caption{CAPTION}  % or \caption[LISTOFTABLES-CAPTION]{CAPTION}
    \label{fig:LABEL}
    \includegraphics[width=0.75\columnwidth]{FILENAME}
\end{figure}
```

- `PLACEMENT` := see [Placement Specifiers](#placement-specifiers)
- `CAPTION` := displayed name of the figure
- `LISTOFTABLES-CAPTION` := (optional) replaces the entry in the list of figures with a shorter version
- `LABEL` := label to reference the figure
- `FILENAME` := file path (with extension) of the image 

## Source Code Listings
```latex
\begin{figure}  % or \begin{figure}[PLACEMENT]
    \centering
    \lstset{caption = {CAPTION}}
    \lstset{label = code:LABEL}
    \lstinputlisting[language = matlab]{FILENAME}
\end{figure}
```

- `PLACEMENT` := see [Placement Specifiers](#placement-specifiers)
- `CAPTION` := displayed name of the source code listing
- `LABEL` := label to reference the figure
- `FILENAME` := file path (with extension) of the source code 

## Directories

```latex
\listoftables       % Tabellenverzeichnis
\listoffigures      % Abbildungsverzeichnis
\lstlistoflistings  % Codelistenverzeichnis
```