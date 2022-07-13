<h1> Packages </h1>

[⌂](../README.md) › [LaTeX](../README.md#latex) ›

Table of Contents
- [Documentation](#documentation)
- [Set Encoding](#set-encoding)
- [Generate Placeholder Text](#generate-placeholder-text)
- [Multiline comments](#multiline-comments)

## Documentation

View package documentation
- visit [TeX and LaTeX documentation lookup system](https://texdoc.org/)  
    `http://texdoc.org/serve/%s/0`
- if LaTeX is installed on your system, run:  
    `texdoc PACKAGE_NAME`
- or visit [CTAN Comprehensive TEX Archive Network](https://ctan.org/)  
    `https://ctan.org/pkg/%s`

## Set Encoding

```latex
\usepackage[utf8]{inputenc}  % Set encoding
```


## Generate Placeholder Text

```latex
\usepackage{lipsum} % Generate placeholder paragraphs
```

## Multiline comments

```latex
\usepackage{verbatim} % Multiline comments

```

```latex
\begin{comment}
\end{comment}
```