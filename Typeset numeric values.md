---
dg-publish: false
example: [ Numbers, Physical quantities ]
command: \qty{3}{\celsius}
priority: 1
---

# Numeric values

Dependecy: [siunitx](https://texdoc.org/serve/siunitx/0)

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

# Physical values

Dependecy: [siunitx](https://texdoc.org/serve/siunitx/0)

## Units

| Example Command                                           | Rendering                 |
| --------------------------------------------------------- | ------------------------- |
| `\unit{kg.m/s^2}`                                         | $\mathrm{kg\ m/s^2}$      |
| `\unit{\gram\per\cubic\centi\metre}`                      | $\mathrm{g\ cm^{-3}}$     |
| `\unit[per-mode = symbol]{\gram\per\cubic\centi\metre}`   | $\mathrm{g/cm^3}$         |
| `\unit[per-mode = fraction]{\gram\per\cubic\centi\metre}` | $\mathrm{\frac{g}{cm^3}}$ |

## Quantities

| Example Command     | Rendering              |
| ------------------- | ---------------------- |
| `\qty{3}{\celsius}` | $3\ \mathrm{^\circ C}$ |

# Monetary values

Dependencies: [currency](https://texdoc.org/serve/currency/0) + [[Standardize currencies and monetary values]]

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


---


Sources:

Related:

Tags:
[[Standardize values]]