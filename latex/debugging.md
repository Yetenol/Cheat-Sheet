# [⌂](../README.md) › [LaTeX](../README.md#latex) › **Debugging**

## Throw Errors

```latex
\PackageError {⟨package-name⟩} {⟨error-text⟩} {⟨help-text⟩}
```

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