---
example: 
command: table-floats/
---

Writing everything in one file reduces readability, increases compile time, and makes debugging more difficult. Therefore a logical project structure is highly recommended.

- **`main.tex`** for project structure which inputs all files
- **`setup/`** for the preamble, configuration, layout and formatting
    - **`packages.tex`** for used packages
    - **`layout.tex`** for formatting styles, package configuration
    - **`definitions.tex`** for new commands, environments, etc.
- **`chapters/`** for text chapters
- **`resources/`** for images, table values, sourcecode files, attachments
- **`bibliographies/`** for sources and external references
- **`table-floats/`** for floating object definitions of tables
- **`figure-floats/`** for the floating object definitions of images and graphics
- **`listing-floats/`** for the floating object definitions of listings
- **`sty/`** for self-written packages

## Preamble
Main document at **`main.tex`**
- minimal version
    ```latex
    %%%%%%%%%% PREAMBLE %%%%%%%%%%
    \input{setup/packages}
    \input{setup/definitions}
    \input{setup/layout}
    \begin{document} 
        %%%%%%%%%% HEADINGS %%%%%%%%%%
        \input{text/headings}
    \end{document}
    ```
- regular version
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
        \tableofcontents
        %%%%%%%%%% HEADINGS %%%%%%%%%%
        \newpage
        \pagestyle{headings}
        \input{text/headings}
        %%%%%%%%%%% DIRECTORIES %%%%%%%%%%
        \clearpage
        \section{Verzeichnisse}
        \listoftables            % Tabellenverzeichnis
        \listoffigures           % Abbildungsverzeichnis
        \lstlistoflistings       % Codelistenverzeichnis
        \input{bib/bibliography} % Literaturverzeichnis
        %%%%%%%%%% APPENDICES %%%%%%%%%%
        \input{src/appendix.tex}
    \end{document}
    ```

## Package requirements 
Dependencies at **`setup/packages.tex`**
- see [Document Classes](layout.md#document-classes) for `\documentclass{}`
```latex
\documentclass[a4paper, 11pt]{article}
\usepackage{syntonly} % Suppress pdf creating and check syntax only

\usepackage[T1]{fontenc} % Use Latin Modern font encoding, e.g. accents, greek letters
\usepackage[utf8]{inputenc} % Use unicode as input encoding 
\usepackage[margin=1.5cm]{geometry} % Set page margins
\usepackage[ngerman]{babel} % Use German hyphenation and names like Inhaltsverzeichnis
\usepackage{csquotes} % Use German quotation marks
```

## Headings
at **`text/headings.tex`**
```latex
\section{Introduction}
\label{sec:introduction}
\input{text/introduction}

\section{Capter 1}
\label{sec:capter-1}
\input{text/capter-1}
```