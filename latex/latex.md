# Getting Started
[⌂](../README.md) › [LaTeX](../README.md#latex) ›

## Help Yourself

View package documentation
```powershell
texdoc PACKAGE_NAME
```

## Project Structure

- **`setup/`**
	- **[`packages.tex`](templates.md#package-requirements)**  
        Required packages | `\usepackage{}`
	- **`definitions.tex`**  
        new commands, environments, columntypes | `\newcommand{}{}`
	- **[`layout.tex`](templates.md#layout)**  
        global formatting, spacing, margins | `\hypersetup{colorlinks=true}`
- **`table/`**  
    - **[_table name_`.tex`](tables.md)**  
        one table [float](floats.md) | `\begin{table}`
- **`figure/`**  
    - **[_figure name_`.tex`](figures.md)**  
        one figure [float](floats.md) | `\begin{figure}`
- **`listing/`**  
    for source code typesetting 
    - **[_listing name_`.tex`](listings.md)**  
        one source code [float](floats.md) | `\lstinputlisting{}`
- **`bib/`**  
    for external references
	- **`bibliography.tex`**  
        Structure of the bibliography | `\printbibliography{}`
	- **_reference type_`.bib`**  
        letters or annex
- **`text/`**  
    - **[`headings.tex`](templates.md#headings)** structure of the headings  
        Text headings | `\section{}`
	- **_heading name_`.tex`**  
        continuous text paragraphs | `\subsection{}`



## Use two columns

```latex
\documentclass[twocolumn]{article}
```


### Add Table Of Contents

```latex
\usepackage{hyperref}
\hypersetup{colorlinks=true} % optional
```

```latex
\tableofcontents
```


## Set Page Margins

```latex
\usepackage[margin=1.5cm]{geometry} % Set page margins
\usepackage[top=2cm, bottom=2cm, left=3cm, right=1cm]{geometry} % Set page margins
```

## Dashes

| .    | LaTeX             | Name                             | Example                  |
| ---- | ----------------- | -------------------------------- | ------------------------ |
| `-`  | `-`               | hyphen                           | daughter-in-law, X-rated |
| `–`  | `--` en-dash      | pages 13–67                      |
| `—`  | `---` em-dash     | yes—or no?                       |
| `−`  | `$-1$`            | minus-sign                       | 0, 1 and −1              |
| `∼`  | `$\sim$`          |
| `/`  | `/`slash          | no hyphenation                   | 5 MB/s                   |
| `/`  | `\slash`          | support hyphenation              | read\slash write         |
| `◦C` | `^{\circ}\mathrm` | degree symbol                    | °C                       |
| `…`  | `\ldots`          | (low dots                        | a, b, c, …               |
|      | `                 | suppress bigger sentence spacing | Mr.~Smith w              |