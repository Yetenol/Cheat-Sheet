# [⌂](../README.md) › [LaTeX](../README.md#latex) › **Getting Started**

## File Structure

- `config`
  - `packages.tex` only \usepackage commands
  - `definitions.tex` new commands, environments, columns
  - `layout.tex` global formatting, spacing, margins
- `figrues` floating bodies: tables and figures
- `references`
  - `bibliography.tex`
  - ...`.bib`
- `texts`
  - _section_`.tex` continuous section paragraphs


### Preamble

- `main.tex`
```latex
\documentclass[a4paper, 11pt]{article}

\input{config/packages}
\input{config/definitions}
\input{config/layout}

\begin{document}
  \maketitle % print title, author, date information
\end{document}
```

- `packages.tex`
```latex
\usepackage{syntonly} % Suppress pdf creating and check syntax only

\usepackage[T1]{fontenc} % Use Latin Modern font encoding, e.g. accents, greek letters
\usepackage[utf8]{inputenc} % Use unicode as input encoding 
\usepackage[margin=1.5cm]{geometry} % Set page margins
\usepackage[ngerman]{babel} % Use German hyphenation and names like Inhaltsverzeichnis
\usepackage{csquotes} % Use German quotation marks
```

- `layout.tex`
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
| `—`  | `---` em-das      | yes—or no?                       |
| `−`  | `$-1$`            | minus-sign                       | 0, 1 and −1              |
| `∼`  | `$\sim$`          |
| `/`  | `/`slash          | no hyphenation                   | 5 MB/s                   |
| `/`  | `\slash`          | support hyphenation              | read\slash write         |
| `◦C` | `^{\circ}\mathrm` | degree symbol                    | °C                       |
| `…`  | `\ldots`          | (low dots                        | a, b, c, …               |
|      | `                 | surpress bigger sentence spacing | Mr.~Smith w              |

