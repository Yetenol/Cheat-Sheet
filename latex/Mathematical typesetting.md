Table of Contents
- [Custom symbols](#custom-symbols)
- [Custom functions](#custom-functions)
- [Better vectors](#better-vectors)
- [Change symbol style](#change-symbol-style)

## Custom symbols

> Dependecy: siunitx

- Custom **symbol**
    ```latex
    \newmathsymbol{\fE}{f_\mathrm{E}}
    ```

## Custom functions

- **Norm**
    ```latex
    \newcommand{\norm}[1]{\left\lVert{}#1\right\rVert}
    ```

- **Absolute** value
    ```latex
    \newcommand{\abs}[1]{\left\lvert{}#1\right\rvert}

## Better vectors

- **Wider vector arrows**  
    The vector arrow is as wide as the elements it spans.
    ```latex
    \renewcommand{\vec}{\vv}
    ```

## Change symbol style
```latex
\renewmathsymbol{\phi}{\varphi}
```

| Preamble Command                                   | Rendering                  | Original         | Dependency |
| -------------------------------------------------- | -------------------------- | ---------------- | ---------- |
| `\renewcommand{\texteuro}{\text{\officialeuro}}`   | € _(official symbol)_      | $€$              | eurosym    |
| `\renewcommand{\texteuro}{\text{\geneuro}}`        | _overlay current font's C_ | $€$              | eurosym    |
| `\renewcommand{\texteuro}{\text{\geneuronarrow}}`  | _overlay current font's C_ | $€$              | eurosym    |
| `\renewcommand{\texteuro}{\text{\geneurowide}}`    | _overlay current font's C_ | $€$              | eurosym    |
| `\renewcommand{\epsilon}{\varepsilon}`             | $\varepsilon$              | $\epsilon$       |
| `\renewcommand{\theta}{\vartheta}`                 | $\vartheta$                | $\theta$         |
| `\renewcommand{\kappa}{\varkappa}`                 | $\varkappa$                | $\kappa$         | amssymb    |
| `\renewcommand{\pi}{\varpi}`                       | $\varpi$                   | $\pi$            |
| `\renewcommand{\rho}{\varrho}`                     | $\varrho$                  | $\rho$           |
| `\renewcommand{\sigma}{\varsigma}`                 | $\varsigma$                | $\sigma$         |
| `\renewcommand{\phi}{\varphi}`                     | $\varphi$                  | $\phi$           |
| `\renewcommand{\propto}{\varpropto}`               | $\varpropto$               | $\propto$        | amssymb    |
| `\renewcommand{\subsetneq}{\varsubsetneq}`         | $\varsubsetneq$            | $\subsetneq$     |
| `\renewcommand{\supsetneq}{\varsupsetneq}`         | $\varsupsetneq$            | $\supsetneq$     |
| `\renewcommand{\subsetneqq}{\varsubsetneqq}`       | $\varsubsetneqq$           | $\subsetneqq$    |
| `\renewcommand{\supsetneqq}{\varsupsetneqq}`       | $\varsupsetneqq$           | $\supsetneqq$    |
| `\renewcommand{\triangleleft}{\vartriangleleft}`   | $\vartriangleleft$         | $\triangleleft$  | amssymb    |
| `\renewcommand{\triangleright}{\vartriangleright}` | $\vartriangleright$        | $\triangleright$ | amssymb    |
| `\renewcommand{\triangle}{\vartriangle}`           | $\vartriangle$             | $\triangle$      | amssymb    |
    ```