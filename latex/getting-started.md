# [⌂](../README.md) › [LaTeX](../README.md#latex)) › **Getting Started**

## Main file structure

### Preamble

```latex
\documentclass[a4paper, 11pt]{article}
\usepackage[utf8]{inputenc} % Set encoding
\title{My Template}
\author{Anton Pusch}
\date{\today}
```


### Body

```latex
\begin{document}

\maketitle % print title, author, date information

\section{Introduction}
\end{document}
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