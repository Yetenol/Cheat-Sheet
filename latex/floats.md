# Floating Bodies
[⌂](../README.md) › [LaTeX](../README.md#latex) ›
- [Positioning](#positioning)
- [Add Images](#add-images)
- [Add List Of Figures](#add-list-of-figures)

## Positioning

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


## Add Images

```latex
\begin{figure}[POSITIONING]
    \centering
    \caption[SHORT-CAPTION]{CAPTION}
    \label{fig:IMAGE_LABEL}
    \includegraphics[width=0.75\columnwidth]{FILE_NAME}
\end{figure}
```

- `POSITIONING` := see [Positioning](#positioning)
- `FILE_NAME` := path (without extension) of the image 
- `SHORT-CAPTION` := (optional) replaced the entry in the list of figures with a summary
- `CAPTION` := displayed name of the figure
- `IMAGE_LABEL` := label to reference the figure



## Add List Of Figures

```latex
\listoffigures
\listoftables
```