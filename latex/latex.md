<h1> Getting Started </h1>

[⌂](../README.md) › [LaTeX](../README.md#latex) ›

## Project Structure

- **`setup/`**
	- **[`packages.tex`](templates.md#package-requirements)**  
        Required packages | `\usepackage{}`
	- **`definitions.tex`**  
        new commands, environments, columntypes | `\newcommand{}{}`
	- **[`layout.tex`](templates.md#layout)**  
        global formatting, spacing, margins | `\hypersetup{colorlinks=true}`
- **`src/`**  
    Resources, Image File, Table Content Files, Source Code Files, Attachments, Appendices
- **`table/`**  
    Tables
    - **[_table name_`.tex`](tables.md)**  
        one table [float](floats.md) | `\begin{table}`
- **`figure/`**  
    Images, Graphics
    - **[_figure name_`.tex`](floats.md#images)**  
        one figure [float](floats.md) | `\begin{figure}`
- **`listing/`**  
    Source Code Typesetting 
    - **[_listing name_`.tex`](floats.md#source-code-listings)**  
        one source code [float](floats.md) | `\lstinputlisting{}`
- **`bib/`**  
    External References
	- **`bibliography.tex`**  
        Structure of the bibliography | `\printbibliography{}`
	- **_reference type_`.bib`**  
        letters or annex
- **`text/`**  
    - **[`headings.tex`](templates.md#headings)** structure of the headings  
        Text headings | `\section{}`
	- **_heading name_`.tex`**  
        continuous text paragraphs | `\subsection{}`
- **`sty/`**  
    Own Packages
  - **_package name_`.sty`**  
    self-written package | `\ProvidesPackage{sty/PACKAGENAME}`

## Debugging

**[READ PACKAGE DOCUMENTATIONS ›](packages.md#documentation)**
> **Debugging only, don't enable while exporting**

- **Draft Mode**  
    highlight overfull conflicts
    ```latex
    \documentclass[draft]{article}
    ```

- **Syntax only**  
    Suppress PDF output and only check syntax.  
    > Dependency: syntonly
    ```latex
    \syntaxonly
    ```
- **Throw Errors**
    Throw an error for a specific package
    ```latex
    \PackageError {⟨package-name⟩} {⟨error-text⟩} {⟨help-text⟩}
    ```


## Numbers and quantities
> Dependecy: siunitx

- **Number**  
    | Example Command    | Rendering             |
    | ------------------ | --------------------- |
    | `\num{12345.2}`    | $12\ 345.2$           |
    | `\num{1\,234 5,2}` | $12\ 345.2$           |
    | `\num{3.45e-4}`    | $3.45 \times 10^{-4}$ |

- **Angles**  
    | Example Command | Rendering      |
    | --------------- | -------------- |
    | `\ang{10}`      | $10^\circ$     |
    | `\ang{1;2;3}`   | $1^\circ2'3''$ |

- **Units**  
    | Example Command                                           | Rendering                 |
    | --------------------------------------------------------- | ------------------------- |
    | `\unit{kg.m/s^2}`                                         | $\mathrm{kg\ m/s^2}$      |
    | `\unit{\gram\per\cubic\centi\metre}`                      | $\mathrm{g\ cm^{-3}}$     |
    | `\unit[per-mode = symbol]{\gram\per\cubic\centi\metre}`   | $\mathrm{g/cm^3}$         |
    | `\unit[per-mode = fraction]{\gram\per\cubic\centi\metre}` | $\mathrm{\frac{g}{cm^3}}$ |

- **Physicial quantities**  
    | Example Command     | Rendering              |
    | ------------------- | ---------------------- |
    | `\qty{3}{\celsius}` | $3\ \mathrm{^\circ C}$ |