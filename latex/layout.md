# Layout
[⌂](../README.md) › [LaTeX](../README.md#latex) ›

## Document Classes

```latex
\documentclass[twocolumn]{article}
```

## File Template
Global formatting at **`setup/layout.tex`**
```
\title{My Template}
\author{Anton Pusch}
\date{\today}
```


## Table Of Contents

```latex
\usepackage{hyperref}
\hypersetup{colorlinks=true} % optional
```

```latex
\tableofcontents
```


## Page Margins

```latex
\usepackage[margin=1.5cm]{geometry} % Set page margins
\usepackage[top=2cm, bottom=2cm, left=3cm, right=1cm]{geometry} % Set page margins
```