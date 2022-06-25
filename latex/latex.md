# Getting Started
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

    ```latex
    \usepackage{syntonly}
    ```

    ```latex
    \syntaxonly
    ```
