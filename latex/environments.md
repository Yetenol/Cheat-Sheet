# [⌂](../README.md) › [LaTeX](../README.md#latex) › **Environment**

## Extend an existing environment 

```
\usepackage{etoolbox} % Append methods to environments
```

Declare placeholders for environment-internal methods: 
```latex
\newcommand{\inaccessiblesetauthor}{}
\newcommand{\inaccessiblesetpage}{}
```

Give the existing start and end commands of the environment aliases to be able to call them later on.
```latex
\let\oldquote\quote
\let\endoldquote\endquote
```

Expand the existing environment.
```latex
\renewenvironment{quote}
{
    \oldquote % begin{quote}

    % Define setauthor (only accessible inside the environment)
    \renewcommand{\inaccessiblesetauthor}[1]
    {
        \def\author{##1}
    }
    \global\let\setauthor\inaccessiblesetauthor

    % Define setpage (only accessible inside the environment)
    \renewcommand{\inaccessiblesetpage}[1]
    {
        \def\page{##1}
    }
    \global\let\setpage\inaccessiblesetpage
}
{
    \par\nobreak\smallskip\hfill(\author --- \page)
    \endoldquote % end{quote}
    \addvspace{\bigskipamount}
}
```