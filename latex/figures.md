# [⌂](../README.md) › [LaTeX](../README.md#latex)) › **Figures**

## Positioning

```latex
\begin{figure}[htbp]
\end{figure}
```

| .   | Name   | Placement                                            |
| --- | ------ | ---------------------------------------------------- |
| `!` | force  | Force the following settings:                        |
| `h` | here   | Put it exactly where we say it should go.            |
| `t` | top    | Put it at the top of the **next available** page.    |
| `b` | bottom | Put it at the bottom of the **next available** page. |
| `p` | page   | Put it on a seperate page.                           |


## Add Images

```latex
\begin{figure}[POSITIONING]
    \centering
    \includegraphics[width=0.75\columnwidth]{FILE_NAME}
    \caption[SHORT_CAPTION]{CAPTION}
    \label{fig:IMAGE_LABEL}
\end{figure}
```


`POSITIONING` := see (#positioning)
`FILE_NAME` := path (without extension) of the image 
`SHORT_CAPTION` := (optional) replaced the entry in the list of figures with a summary
`CAPTION` := displayed name of the figure
`IMAGE_LABEL` := label to reference the figure



## Add List Of Figures

```latex

```