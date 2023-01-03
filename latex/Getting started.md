Table of Contents
- [Project Structure](#project-structure)
- [Debugging](#debugging)
- [Numeric values](#numeric-values)
- [Money](#money)

## Project Structure

- **`setup/`**
	- **[`packages.tex` ›](templates.md#package-requirements)**  
        Required packages | `\usepackage{}`
	- **`definitions.tex`**  
        new commands, environments, columntypes | `\newcommand{}{}`
	- **[`layout.tex` ›](templates.md#layout)**  
        global formatting, spacing, margins | `\hypersetup{colorlinks=true}`
- **`src/`** for resources, images, table values, sourcecode files, attachments, appendices
- **`table/`** for table floats
    - **[_table name_`.tex` ›](tables.md)**  
        one table [float](Floating%20Bodies.md) | `\begin{table}`
- **`figure/`** for image or graphic floats
    - **[_figure name_`.tex` ›](Floating%20Bodies.md#images)**  
        one figure [float](Floating%20Bodies.md) | `\begin{figure}`
- **`listing/`** for sourcecode typesetting floats
    - **[_listing name_`.tex` ›](Floating%20Bodies.md#source-code-listings)**  
        one source code [float](Floating%20Bodies.md) | `\lstinputlisting{}`
- **`bib/`** for external references
	- **`bibliography.tex`**  
        Structure of the bibliography | `\printbibliography{}`
	- **_reference type_`.bib`**  
        letters or annex
- **`text/`** for continues text
    - **[`headings.tex` ›](templates.md#headings)**  
        Structure of the headings  | `\section{}`
	- **_heading name_`.tex`**  
        Continuous text paragraphs | `\subsection{}`
- **`sty/`** for own packages
  - **_package name_`.sty`**  
    self-written package | `\ProvidesPackage{sty/PACKAGENAME}`

## Debugging

- **view user guide** of a specific packages  
    - by adding a custom search engine to your browser  
    `http://texdoc.org/serve/%s/0`
    - by visiting **[texdoc.org](https://texdoc.org/index.html)**
    - by running the following as long as LaTeX is installed  
        `texdoc ⟨package name⟩`
    - by visiting **[ctan.org](https://ctan.org/)**
- **highlight overfull conflicts**  
    by enabling draft mode in the preamble
    ```latex
    \documentclass[draft]{article}
    ```
- only **check syntax**  
    by supressing the PDF creation in the preamble
    > Dependency: syntonly
    ```latex
    \syntaxonly
    ```
- **throw an error** for a specific package
    ```latex
    \PackageError {⟨package name⟩} {⟨error text⟩} {}
    ```


## Numeric values
> Dependecy: siunitx

- **Numbers**  
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

## Money 
> Dependencies: currency + [`\DefineCurrency`](symbols.md#currencies)

- **Currency**  
    | Command   | Rendering |
    | --------- | --------- |
    | `\cEUR{}` | €         |
    | `\cUSD{}` | $         |
    | `\cJPY{}` | ¥         |
    | `\cGBP{}` | £         |

- **Amount of money**  
    | Command      | Rendering |
    | ------------ | --------- |
    | `\dEUR{1.5}` | 1.50 €    |
    | `\dUSD{1.5}` | $ 1.50    |
    | `\dJPY{1.5}` | 2 ¥       |
    | `\dGBP{1.5}` | £ 1.50    |