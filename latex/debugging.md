# Debugging
[⌂](../README.md) › [LaTeX](../README.md#latex) ›
- [Obmit PDF output and only check syntax](#obmit-pdf-output-and-only-check-syntax)
- [Draft Mode](#draft-mode)

## Obmit PDF output and only check syntax

> **Debugging only, don't enable while exporting**

- suppress pdf output
- only check syntax

```latex
\usepackage{syntonly}
```

```latex
\syntaxonly
```

## Draft Mode

> **Debugging only, don't enable while exporting**

- highlight overfull conflicts

```latex
\documentclass[draft]{article}
```