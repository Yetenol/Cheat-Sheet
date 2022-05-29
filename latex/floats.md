# [⌂](../README.md) › [LaTeX](../README.md#latex) › **Floating Bodies**


## Positioning

```latex
\begin{⟨float environment⟩}[⟨positioning⟩]
\end{⟨float environment⟩}
```

> default `tbp` is used if no positioning is set

| .   | Name   | Placement Permissions                                                            |
| --- | ------ | -------------------------------------------------------------------------------- |
| `!` | force  | Force the following settings, without considerung most of the internal parameter |
| `h` | here   | Put it exactly where we say it should go.                                        |
| `t` | top    | Put it at the top of the _next available_ page.                                  |
| `b` | bottom | Put it at the bottom of the _next available_ page.                               |
| `p` | page   | Put it on a special page containing only floats.                                 |

e.g:
```latex
\begin{figure}[htbp]
\end{figure}
```

## Add Images

```latex
\begin{figure} % \begin{figure}[⟨positioning⟩]
    \centering
    \caption{⟨caption⟩} % \caption[list of figures caption⟩]{⟨caption⟩}
    \label{fig:⟨label name⟩}
    \includegraphics[width = ⟨factor⟩\columnwidth]{⟨file name⟩}
\end{figure}
```

- `⟨positioning⟩` := see [Positioning](#positioning)
- `⟨caption⟩` := displayed name of the figure
- `⟨list of figures caption⟩` := (optional) replaced the entry in the list of figures with a summary
- `⟨label name⟩` := label to reference the figure using `\ref{fig:⟨label name⟩}`
- `⟨factor⟩` := e.g: `0.7`, image width in percent of text width
- `⟨file name⟩` := path (without extension) of the image



## Add List Of Figures

```latex
\listoffigures
\listoftables
```