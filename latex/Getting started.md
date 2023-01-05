[Project Structure](Project%20Structure.md)

# Debugging

## View user guide of a specific packages  
 
- by adding a custom search engine to your browser
    ```
    http://texdoc.org/serve/%s/0
    ```
- by visiting **[texdoc.org](https://texdoc.org/index.html)**
- by running the following as long as LaTeX is installed  
    `texdoc ⟨package name⟩`
- by visiting **[ctan.org](https://ctan.org/)**

## Highlight overfull conflicts

- by enabling draft mode in the preamble
    ```latex
    \documentclass[draft]{article}
    ```
- only **check syntax**  
    by supressing the PDF creation in the preamble  
    Dependency: syntonly
    ```latex
    \syntaxonly
    ```
- **throw an error** for a specific package
    ```latex
    \PackageError {⟨package name⟩} {⟨error text⟩} {}
    ```

# Numeric values

Dependecy: siunitx

## Numbers  

| Example Command    | Rendering             |
| ------------------ | --------------------- |
| `\num{12345.2}`    | $12\ 345.2$           |
| `\num{1\,234 5,2}` | $12\ 345.2$           |
| `\num{3.45e-4}`    | $3.45 \times 10^{-4}$ |

## Angles

| Example Command | Rendering      |
| --------------- | -------------- |
| `\ang{10}`      | $10^\circ$     | 
| `\ang{1;2;3}`   | $1^\circ2'3''$ |

## Units

| Example Command                                           | Rendering                 |
| --------------------------------------------------------- | ------------------------- |
| `\unit{kg.m/s^2}`                                         | $\mathrm{kg\ m/s^2}$      |
| `\unit{\gram\per\cubic\centi\metre}`                      | $\mathrm{g\ cm^{-3}}$     |
| `\unit[per-mode = symbol]{\gram\per\cubic\centi\metre}`   | $\mathrm{g/cm^3}$         |
| `\unit[per-mode = fraction]{\gram\per\cubic\centi\metre}` | $\mathrm{\frac{g}{cm^3}}$ |

## Physicial quantities

| Example Command     | Rendering              |
| ------------------- | ---------------------- |
| `\qty{3}{\celsius}` | $3\ \mathrm{^\circ C}$ |

# Money 

Dependencies: currency + [`\DefineCurrency`](symbols.md#currencies)

## Currency

| Command   | Rendering |
| --------- | --------- |
| `\cEUR{}` | €         |
| `\cUSD{}` | $         |
| `\cJPY{}` | ¥         |
| `\cGBP{}` | £         |

## Amount of money

| Command      | Rendering |
| ------------ | --------- |
| `\dEUR{1.5}` | 1.50 €    |
| `\dUSD{1.5}` | $ 1.50    |
| `\dJPY{1.5}` | 2 ¥       |
| `\dGBP{1.5}` | £ 1.50    |