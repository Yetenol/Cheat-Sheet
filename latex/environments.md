# Environment
[⌂](../README.md) › [LaTeX](../README.md#latex) ›

## Extend an existing environment 

```latex
\usepackage{etoolbox} % Append methods to environments
```

## Private environment methods

1. Declare a public global placeholder _METHOD_
    ```latex
    \newcommand{\inaccessibleMETHOD}{}
    ```

2. Create references to the environment _ENVIRONMENT_ to be overwritten in order to access it later on
    ```latex
    \let\@oldENVIRONMENT\ENVIRONMENT
    \let\@endoldENVIRONMENT\endENVIRONMENT
    ```

3. Define method (private)
    ```latex
    \renewenvironment{ENVIRONMENT}
    {
        \oldENVIRONMENT % begin{ENVIRONMENT}

        % Define method \SETTER{ATTRIBUTE}
        % - only accessible inside the environment (aka method)
        \renewcommand{\inaccessibleSETTER}[1]
        {
            \def\@ATTRIBUTE{##1}
        }
        \global\let\SETTER\inaccessibleSETTER
    }
    {
        \endoldENVIRONMENT % end{ENVIRONMENT}
    }
    ```