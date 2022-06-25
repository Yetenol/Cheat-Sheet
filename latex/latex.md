# Getting Started
[⌂](../README.md) › [LaTeX](../README.md#latex) ›

## Help Yourself

View package documentation
```powershell
texdoc PACKAGE_NAME
```

## File Structure

- **`setup/`**
	- **`packages.tex`**  
        Required packages | `\usepackage{}`
	- **`definitions.tex`**  
        new commands, environments, columntypes | `\newcommand{}{}`
	- **`layout.tex`**  
        global formatting, spacing, margins | `\hypersetup{colorlinks=true}`
- **`table/`**  
    - **_table name_`.tex`**  
        one table float | `\begin{table}`
- **`figure/`**  
    - **_figure name_`.tex`**  
        one figure float | `\begin{figure}`
- **`listing/`**  
    for source code typesetting 
    - **_listing name_`.tex`**  
        one source code floats | `\lstinputlisting{}`
- **`bib/`**  
    for external references
	- **`bibliography.tex`**  
        Structure of the bibliography | `\printbibliography{}`
	- **_reference type_`.bib`**  
        letters or annex
- **`text/`**  
    - **`headings.tex`** structure of the headings  
        Text headings | `\section{}`
	- **_heading name_`.tex`**  
        continuous text paragraphs | `\subsection{}`


### Preamble

- **Main document** in `main.tex`
	```latex
	%%%%%%%%%% PREAMBLE %%%%%%%%%%
	\input{setup/packages}
	\input{setup/definitions}
	\input{setup/layout}
	\begin{document} 
        %%%%%%%%%% HEADINGS %%%%%%%%%%
	\end{document}
	```
	```latex
	%%%%%%%%%% PREAMBLE %%%%%%%%%%
	\input{setup/packages}
	\input{setup/definitions}
	\input{setup/layout}
	\begin{document} 
	    %%%%%%%%%% TITLE PAGES %%%%%%%%%%
	    \maketitle % print title, author, date information
        \input{setup/titlepage}
        \pagestyle{empty}
        \input{setup/eidesstattlicheErklaerung}
        \tableofcontents
        \newpage
        \pagestyle{headings}
        %%%%%%%%%% HEADINGS %%%%%%%%%%
        \section{Introduction}
        \label{sec:introduction}
        \input{text/introduction}

        \section{Capter 1}
        \label{sec:capter-1}
        \input{text/capter-1}
        %%%%%%%%%%% DIRECTORIES %%%%%%%%%%
	    \clearpage
	    \section{Verzeichnisse}
	    \listoftables       % Tabellenverzeichnis
	    \listoffigures      % Abbildungsverzeichnis
	    \lstlistoflistings  % Codelistenverzeichnis
	    \input{bib/bibliography} % Literaturverzeichnis
	    %%%%%%%%%% APPENDICES %%%%%%%%%%
	\end{document}
	```

- **Package requirements** in `setup/packages.tex`
	```latex
	\documentclass[a4paper, 11pt]{article}
	\usepackage{syntonly} % Suppress pdf creating and check syntax only

	\usepackage[T1]{fontenc} % Use Latin Modern font encoding, e.g. accents, greek letters
	\usepackage[utf8]{inputenc} % Use unicode as input encoding 
	\usepackage[margin=1.5cm]{geometry} % Set page margins
	\usepackage[ngerman]{babel} % Use German hyphenation and names like Inhaltsverzeichnis
	\usepackage{csquotes} % Use German quotation marks
	```

- **Layout** in `setup/layout.tex`
	```
	\title{My Template}
	\author{Anton Pusch}
	\date{\today}
```


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

