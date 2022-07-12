<h1> Symbols </h1>

[⌂](../README.md) › [LaTeX](../README.md#latex) ›

> Commands for Mathematical Expressions, Symbols, Operators and Relations

Table of Contens
- [Favorites](#favorites)
- [Non-Mathematical Symbols](#non-mathematical-symbols)
- [Currencies](#currencies)
- [Degree Symbols](#degree-symbols)
- [Math Mode Accents](#math-mode-accents)
- [Greek Letters (lowercase)](#greek-letters-lowercase)
- [Greek Letters (uppercase)](#greek-letters-uppercase)
- [Hebrew Letters](#hebrew-letters)
- [Number sets](#number-sets)
- [Binary Relations](#binary-relations)
- [Negated Binary Relations and Arrows](#negated-binary-relations-and-arrows)
- [Binary Operators](#binary-operators)
- [Big Operators](#big-operators)
- [Arrows](#arrows)
- [Arrows as Accents](#arrows-as-accents)
- [Delimiters](#delimiters)
- [Large Delimiters](#large-delimiters)
- [Miscellaneous Symbols](#miscellaneous-symbols)
- [Math Alphabets](#math-alphabets)
- [Sources](#sources)

## Favorites
| Command           | Rendering         |
| ----------------- | ----------------- |
| `\lnot`           | $\lnot$           |
| `\land`           | $\land$           |
| `\lor`            | $\lor$            |
| `\longrightarrow` | $\longrightarrow$ |
| `\Rightarrow`     | $\Rightarrow$     |
| `\mathbb{R}`      | $\mathbb{R}$      |
| `\approx`         | $\approx$         |
| `\subseteq`       | $\subseteq$       |
| `\supseteq`       | $\supseteq$       |
| `\leq`            | $\leq$            |
| `\geq`            | $\geq$            |
| `\cap`            | $\cap$            |
| `\cup`            | $\cup$            |

## Non-Mathematical Symbols
> These symbols can also be used in text mode.

| Command                                 | Rendering      | Name or _Function_                   | Usage Example                    |
| --------------------------------------- | -------------- | ------------------------------------ | -------------------------------- |
| `-`                                     | -              | hyphen                               | daughter-in-law, X-rated         |
| `--`                                    | –              | en-dash                              | pages 13–67                      |
| `---`                                   | —              | em-dash                              | yes—or no?                       |
| `$-1$`                                  | −              | minus-sign                           | 0, 1 and −1                      |
| `/`                                     | /              | _prevents hyphenation_               | 5 MB/s                           |
| `\slash{}`                              | /              | _supports hyphenation_               | read/write                       |
| `\ldots{}`                              | …              | ellipsis                             | a, b, c, …                       |
| `Mr.~Smith`                             | Mr.&#160;Smith | _suppresses bigger sentence spacing_ | Did ⠀Mr.&#160;Smith ⠀win ⠀today? |
| `\dag{}`                                | †              | Dagger                               |
| `\ddag{}`                               | ‡              | Double Dagger                        |
| `\S{}`                                  | §              | Section Sign                         |
| `\P{}`                                  | ¶              | Pilcrow Sign                         |
| `\%{}`                                  | %              | Percent Sign                         |
| `\textsuperscript{\textcopyright}`      | ©              | Copyright Sign                       |
| `\textsuperscript{\textregistered}`     | ®              | Registered Trade Mark Sign           |
| `\texttrademark{}`                      | ™              | Trade Mark Sign                      |
| `\unit{\degree}` <br> `\textdegree{}`   | °              | Degree Sign                          | siunitx <br> _built in_          |
| `\ang{5}`                               | 5°             | Angle                                | siunitx                          |
| `\unit{\celsius}` <br> `\textcelsius{}` | ℃              | Degree Celsius                       | siunitx <br> _built in_          |
| `\qty{5}{\celsius}`                     | 5 ℃            |                                      | siunitx                          |


## Currencies
> `€`, `\$`, `pounds` and `\yen` are not recommended

| Command                          | Rendering | Variants | Dependency |
| -------------------------------- | --------- | -------- | ---------- |
| `\texteuro{}`                    | $€$       | €€€€     |
| `\textdollar{}`                  | $         |
| `\textsterling{}`                | £         |
| `\textyen{}`                     | ¥         |
| `\qty{5}{\text\texteuro}`        | 15 €      |          | siunitx    |
| `\qty{15}[\text\textdollar]{}`   | $15       |          | siunitx    |
| `\qty{15}[\text\textsterling]{}` | £15       |          | siunitx    |
| `\qty{15}[\text\textyen]{}`      | ¥15       |          | siunitx    |


- **Simplify Currencies**  
    Preamble Command:
    ```latex
    \DeclareSIUnit{\euro}{\text{\texteuro}}
    \DeclareSIUnit{\dollar}{\text{\textdollar}}
    \DeclareSIUnit{\sterling}{\text{\textsterling}}
    \DeclareSIUnit{\yen}{\text{\textyen}}
    ```
    | Command                 | Rendering | Dependency |
    | ----------------------- | --------- | ---------- |
    | `\qty{5}{\euro}`        | 15 €      | siunitx    |
    | `\qty{15}[\dollar]{}`   | $15       | siunitx    |
    | `\qty{15}[\sterling]{}` | £15       | siunitx    |
    | `\qty{15}[\yen]{}`      | ¥15       | siunitx    |
- **Change** euro symbol **style**.  
    Choose the official style or for special fonts one of the latter three
    | Preamble Command                                  | Rendering                  | Original | Dependency |
    | ------------------------------------------------- | -------------------------- | -------- | ---------- |
    | `\renewcommand{\texteuro}{\text{\officialeuro}}`  | € _(official symbol)_      | $€$      | eurosym    |
    | `\renewcommand{\texteuro}{\text{\geneuro}}`       | _overlay current font's C_ | $€$      | eurosym    |
    | `\renewcommand{\texteuro}{\text{\geneuronarrow}}` | _overlay current font's C_ | $€$      | eurosym    |
    | `\renewcommand{\texteuro}{\text{\geneurowide}}`   | _overlay current font's C_ | $€$      | eurosym    |

## Degree Symbols
| Command           | Rendering        | Dependency |
| ----------------- | ---------------- | ---------- |
| `^\circ`          | $^\circ$         |            |
| `\unit{\degree}`  | $^\circ$         | siunitx    |
| `\unit{\celsius}` | $^\circ\text{C}$ | siunitx    |

## Math Mode Accents
| Command           | Rendering         |
| ----------------- | ----------------- |
| `\acute{a}`       | $\acute{a}$       |
| `\bar{a}`         | $\bar{a}$         |
| `\breve{a}`       | $\breve{a}$       |
| `\check{a}`       | $\check{a}$       |
| `\ddot{a}`        | $\ddot{a}$        |
| `\dot{a}`         | $\dot{a}$         |
| `\grave{a}`       | $\grave{a}$       |
| `\hat{a}`         | $\hat{a}$         |
| `\mathring{a}`    | $\mathring{a}$    |
| `\tilde{a}`       | $\tilde{a}$       |
| `\vec{a}`         | $\vec{a}$         |
| `\widehat{AAA}`   | $\widehat{AAA}$   |
| `\widetilde{AAA}` | $\widetilde{AAA}$ |

## Greek Letters (lowercase)
| Command     | Rendering   | Variants      |
| ----------- | ----------- | ------------- |
| `\alpha`    | $\alpha$    |
| `\beta`     | $\beta$     |
| `\gamma`    | $\gamma$    |
| `\delta`    | $\delta$    |
| `\epsilon`  | $\epsilon$  | $\varepsilon$ |
| `\zeta`     | $\zeta$     |
| `\eta`      | $\eta$      |
| `\theta`    | $\theta$    | $\vartheta$   |
| `\iota`     | $\iota$     |
| `\kappa`    | $\kappa$    | $\varkappa$   |
| `\lambda`   | $\lambda$   |
| `\mu`       | $\mu$       |
| `\nu`       | $\nu$       |
| `\xi`       | $\xi$       |
| `o`         | $o$         |
| `\pi`       | $\pi$       | $\varpi$      |
| `\rho`      | $\rho$      | $\varrho$     |
| `\sigma`    | $\sigma$    | $\varsigma$   |
| `\tau`      | $\tau$      |
| `\upsilon`  | $\upsilon$  |
| `\phi`      | $\phi$      | $\varphi$     |
| `\chi`      | $\chi$      |
| `\psi`      | $\psi$      |
| `\omega`    | $\omega$    |
| `\digamma`  | $\digamma$  |               | amssymb |
| `\varkappa` | $\varkappa$ |               | amssymb |

- Change letter style
    | Preamble Command                       | Rendering     | Original   | Dependency |
    | -------------------------------------- | ------------- | ---------- | ---------- |
    | `\renewcommand{\epsilon}{\varepsilon}` | $\varepsilon$ | $\epsilon$ |
    | `\renewcommand{\theta}{\vartheta}`     | $\vartheta$   | $\theta$   |
    | `\renewcommand{\kappa}{\varkappa}`     | $\varkappa$   | $\kappa$   | amssymb    |
    | `\renewcommand{\pi}{\varpi}`           | $\varpi$      | $\pi$      |
    | `\renewcommand{\rho}{\varrho}`         | $\varrho$     | $\rho$     |
    | `\renewcommand{\sigma}{\varsigma}`     | $\varsigma$   | $\sigma$   |
    | `\renewcommand{\phi}{\varphi}`         | $\varphi$     | $\phi$     |
    
## Greek Letters (uppercase)
| Command    | Rendering  |
| ---------- | ---------- |
| `\Gamma`   | $\Gamma$   |
| `\Delta`   | $\Delta$   |
| `\Theta`   | $\Theta$   |
| `\Lambda`  | $\Lambda$  |
| `\Xi`      | $\Xi$      |
| `\Pi`      | $\Pi$      |
| `\Sigma`   | $\Sigma$   |
| `\Upsilon` | $\Upsilon$ |
| `\Phi`     | $\Phi$     |
| `\Psi`     | $\Psi$     |
| `\Omega`   | $\Omega$   |

## Hebrew Letters
| Command   | Rendering | Dependency |
| --------- | --------- | ---------- |
| `\beth`   | $\beth$   | amssymb    |
| `\gimel`  | $\gimel$  | amssymb    |
| `\daleth` | $\daleth$ | amssymb    |

## Number sets
| Command      | Rendering    |
| ------------ | ------------ |
| `\mathbb{A}` | $\mathbb{A}$ |
| `\mathbb{C}` | $\mathbb{C}$ |
| `\mathbb{H}` | $\mathbb{H}$ |
| `\mathbb{N}` | $\mathbb{N}$ |
| `\mathbb{O}` | $\mathbb{O}$ |
| `\mathbb{Q}` | $\mathbb{Q}$ |
| `\mathbb{R}` | $\mathbb{R}$ |
| `\mathbb{S}` | $\mathbb{S}$ |
| `\mathbb{Z}` | $\mathbb{Z}$ |

## Binary Relations

| Command               | Rendering             | Variants                                    | Dependency |
| --------------------- | --------------------- | ------------------------------------------- | ---------- |
| `<`                   | $<$                   | $\not<$                                     |
| `>`                   | $>$                   | $\not>$                                     |
| `=`                   | $=$                   | $\not=$                                     |
| `\leq` <br> `\le`     | $\leq$ <br> $\le$     | $\not\leq$ <br> $\not\le$                   |
| `\geq` <br> `\ge`     | $\geq$ <br> $\ge$     | $\not\geq$ <br> $\not\ge$                   |
| `\equiv`              | $\equiv$              | $\not\equiv$                                |
| `\ll`                 | $\ll$                 | $\not\ll$                                   |
| `\gg`                 | $\gg$                 | $\not\gg$                                   |
| `\doteq`              | $\doteq$              | $\not\doteq$                                |
| `\prec`               | $\prec$               | $\not\prec$                                 |
| `\succ`               | $\succ$               | $\not\succ$                                 |
| `\sim`                | $\sim$                | $\not\sim$                                  |
| `\preceq`             | $\preceq$             | $\not\preceq$                               |
| `\succeq`             | $\succeq$             | $\not\succeq$                               |
| `\simeq`              | $\simeq$              | $\not\simeq$                                |
| `\subset`             | $\subset$             | $\not\subset$                               |
| `\supset`             | $\supset$             | $\not\supset$                               |
| `\approx`             | $\approx$             | $\not\approx$                               |
| `\subseteq`           | $\subseteq$           | $\not\subseteq$                             |
| `\supseteq`           | $\supseteq$           | $\not\supseteq$                             |
| `\cong`               | $\cong$               | $\not\cong$                                 |
| `\sqsubset`           | $\sqsubset$           | $\not\sqsubset$                             | latexsym   |
| `\sqsupset`           | $\sqsupset$           | $\not\sqsupset$                             | latexsym   |
| `\Join`               | $\Join$               | $\not\Join$                                 | latexsym   |
| `\sqsubseteq`         | $\sqsubseteq$         | $\not\sqsubseteq$                           |
| `\sqsupseteq`         | $\sqsupseteq$         | $\not\sqsupseteq$                           |
| `\bowtie`             | $\bowtie$             | $\not\bowtie$                               |
| `\in`                 | $\in$                 | $\not\in$                                   |
| `\ni` <br> `\owns`    | $\ni$ <br> $\owns$    | $\not\ni$ <br> $\not\owns$                  |
| `\propto`             | $\propto$             | $\not\propto$ $\varpropto$ $\not\varpropto$ |
| `\vdash`              | $\vdash$              | $\not\vdash$                                |
| `\dashv`              | $\dashv$              | $\not\dashv$                                |
| `\models`             | $\models$             | $\not\models$                               |
| `\mid`                | $\mid$                | $\not\mid$                                  |
| `\parallel`           | $\parallel$           | $\not\parallel$                             |
| `\perp`               | $\perp$               | $\not\perp$                                 |
| `\smile`              | $\smile$              | $\not\smile$                                |
| `\frown`              | $\frown$              | $\not\frown$                                |
| `\asymp`              | $\asymp$              | $\not\asymp$                                |
| `:`                   | $:$                   | $\not:$                                     |
| `\lessdot`            | $\lessdot$            | $\not\lessdot$                              | amssymb    |
| `\gtrdot`             | $\gtrdot$             | $\not\gtrdot$                               | amssymb    |
| `\doteqdot`           | $\doteqdot$           | $\not\doteqdot$                             | amssymb    |
| `\leqslant`           | $\leqslant$           | $\not\leqslant$                             | amssymb    |
| `\geqslant`           | $\geqslant$           | $\not\geqslant$                             | amssymb    |
| `\risingdotseq`       | $\risingdotseq$       | $\not\risingdotseq$                         | amssymb    |
| `\eqslantless`        | $\eqslantless$        | $\not\eqslantless$                          | amssymb    |
| `\eqslantgtr`         | $\eqslantgtr$         | $\not\eqslantgtr$                           | amssymb    |
| `\fallingdotseq`      | $\fallingdotseq$      | $\not\fallingdotseq$                        | amssymb    |
| `\leqq`               | $\leqq$               | $\not\leqq$                                 | amssymb    |
| `\geqq`               | $\geqq$               | $\not\geqq$                                 | amssymb    |
| `\eqcirc`             | $\eqcirc$             | $\not\eqcirc$                               | amssymb    |
| `\lll`                | $\lll$                | $\not\lll$                                  | amssymb    |
| `\llless`             | $\llless$             | $\not\llless$                               | amssymb    |
| `\ggg`                | $\ggg$                | $\not\ggg$                                  | amssymb    |
| `\circeq`             | $\circeq$             | $\not\circeq$                               | amssymb    |
| `\lesssim`            | $\lesssim$            | $\not\lesssim$                              | amssymb    |
| `\gtrsim`             | $\gtrsim$             | $\not\gtrsim$                               | amssymb    |
| `\triangleq`          | $\triangleq$          | $\not\triangleq$                            | amssymb    |
| `\lessapprox`         | $\lessapprox$         | $\not\lessapprox$                           | amssymb    |
| `\gtrapprox`          | $\gtrapprox$          | $\not\gtrapprox$                            | amssymb    |
| `\bumpeq`             | $\bumpeq$             | $\not\bumpeq$                               | amssymb    |
| `\lessgtr`            | $\lessgtr$            | $\not\lessgtr$                              | amssymb    |
| `\gtrless`            | $\gtrless$            | $\not\gtrless$                              | amssymb    |
| `\Bumpeq`             | $\Bumpeq$             | $\not\Bumpeq$                               | amssymb    |
| `\lesseqgtr`          | $\lesseqgtr$          | $\not\lesseqgtr$                            | amssymb    |
| `\gtreqless`          | $\gtreqless$          | $\not\gtreqless$                            | amssymb    |
| `\thicksim`           | $\thicksim$           | $\not\thicksim$                             | amssymb    |
| `\lesseqqgtr`         | $\lesseqqgtr$         | $\not\lesseqqgtr$                           | amssymb    |
| `\gtreqqless`         | $\gtreqqless$         | $\not\gtreqqless$                           | amssymb    |
| `\thickapprox`        | $\thickapprox$        | $\not\thickapprox$                          | amssymb    |
| `\preccurlyeq`        | $\preccurlyeq$        | $\not\preccurlyeq$                          | amssymb    |
| `\succcurlyeq`        | $\succcurlyeq$        | $\not\succcurlyeq$                          | amssymb    |
| `\approxeq`           | $\approxeq$           | $\not\approxeq$                             | amssymb    |
| `\curlyeqprec`        | $\curlyeqprec$        | $\not\curlyeqprec$                          | amssymb    |
| `\curlyeqsucc`        | $\curlyeqsucc$        | $\not\curlyeqsucc$                          | amssymb    |
| `\backsim`            | $\backsim$            | $\not\backsim$                              | amssymb    |
| `\precsim`            | $\precsim$            | $\not\precsim$                              | amssymb    |
| `\succsim`            | $\succsim$            | $\not\succsim$                              | amssymb    |
| `\backsimeq`          | $\backsimeq$          | $\not\backsimeq$                            | amssymb    |
| `\precapprox`         | $\precapprox$         | $\not\precapprox$                           | amssymb    |
| `\succapprox`         | $\succapprox$         | $\not\succapprox$                           | amssymb    |
| `\vDash`              | $\vDash$              | $\not\vDash$                                | amssymb    |
| `\subseteqq`          | $\subseteqq$          | $\not\subseteqq$                            | amssymb    |
| `\supseteqq`          | $\supseteqq$          | $\not\supseteqq$                            | amssymb    |
| `\Vdash`              | $\Vdash$              | $\not\Vdash$                                | amssymb    |
| `\shortparallel`      | $\shortparallel$      | $\not\shortparallel$                        | amssymb    |
| `\Supset`             | $\Supset$             | $\not\Supset$                               | amssymb    |
| `\Vvdash`             | $\Vvdash$             | $\not\Vvdash$                               | amssymb    |
| `\blacktriangleleft`  | $\blacktriangleleft$  | $\not\blacktriangleleft$                    | amssymb    |
| `\sqsupset`           | $\sqsupset$           | $\not\sqsupset$                             | amssymb    |
| `\backepsilon`        | $\backepsilon$        | $\not\backepsilon$                          | amssymb    |
| `\vartriangleright`   | $\vartriangleright$   | $\not\vartriangleright$                     | amssymb    |
| `\because`            | $\because$            | $\not\because$                              | amssymb    |
| `\varpropto`          | $\varpropto$          | $\not\varpropto$                            | amssymb    |
| `\blacktriangleright` | $\blacktriangleright$ | $\not\blacktriangleright$                   | amssymb    |
| `\Subset`             | $\Subset$             | $\not\Subset$                               | amssymb    |
| `\between`            | $\between$            | $\not\between$                              | amssymb    |
| `\trianglerighteq`    | $\trianglerighteq$    | $\not\trianglerighteq$                      | amssymb    |
| `\smallfrown`         | $\smallfrown$         | $\not\smallfrown$                           | amssymb    |
| `\pitchfork`          | $\pitchfork$          | $\not\pitchfork$                            | amssymb    |
| `\vartriangleleft`    | $\vartriangleleft$    | $\not\vartriangleleft$                      | amssymb    |
| `\shortmid`           | $\shortmid$           | $\not\shortmid$                             | amssymb    |
| `\smallsmile`         | $\smallsmile$         | $\not\smallsmile$                           | amssymb    |
| `\trianglelefteq`     | $\trianglelefteq$     | $\not\trianglelefteq$                       | amssymb    |
| `\therefore`          | $\therefore$          | $\not\therefore$                            | amssymb    |
| `\sqsubset`           | $\sqsubset$           | $\not\sqsubset$                             | amssymb    |

- **Use primitively negated symbol**  
  Not recommended, use [properly negated symbols](#negated-binary-relations-and-arrows) instead.  
  Prefix the command with `\not` like `\not\leq`.  

- **Change** symbol **style**
  | Preamble Command                     | Rendering    | Original  | Dependency |
  | ------------------------------------ | ------------ | --------- | ---------- |
  | `\renewcommand{\propto}{\varpropto}` | $\varpropto$ | $\propto$ | amssymb    |

## Negated Binary Relations and Arrows
| Command             | Rendering           | Variants         | Dependency |
| ------------------- | ------------------- | ---------------- | ---------- |
| `\neq` <br> `\ne`   | $\neq$ <br> $\ne$   |                  |
| `\notin`            | $\notin$            |                  |
| `\nless`            | $\nless$            |                  | amssymb    |
| `\ngtr`             | $\ngtr$             |                  | amssymb    |
| `\lneq`             | $\lneq$             |                  | amssymb    |
| `\gneq`             | $\gneq$             |                  | amssymb    |
| `\nleq`             | $\nleq$             |                  | amssymb    |
| `\ngeq`             | $\ngeq$             |                  | amssymb    |
| `\nleqslant`        | $\nleqslant$        |                  | amssymb    |
| `\ngeqslant`        | $\ngeqslant$        |                  | amssymb    |
| `\lneqq`            | $\lneqq$            |                  | amssymb    |
| `\gneqq`            | $\gneqq$            |                  | amssymb    |
| `\lvertneqq`        | $\lvertneqq$        |                  | amssymb    |
| `\gvertneqq`        | $\gvertneqq$        |                  | amssymb    |
| `\nleqq`            | $\nleqq$            |                  | amssymb    |
| `\ngeqq`            | $\ngeqq$            |                  | amssymb    |
| `\lnsim`            | $\lnsim$            |                  | amssymb    |
| `\gnsim`            | $\gnsim$            |                  | amssymb    |
| `\lnapprox`         | $\lnapprox$         |                  | amssymb    |
| `\gnapprox`         | $\gnapprox$         |                  | amssymb    |
| `\nprec`            | $\nprec$            |                  | amssymb    |
| `\nsucc`            | $\nsucc$            |                  | amssymb    |
| `\npreceq`          | $\npreceq$          |                  | amssymb    |
| `\nsucceq`          | $\nsucceq$          |                  | amssymb    |
| `\precneqq`         | $\precneqq$         |                  | amssymb    |
| `\succneqq`         | $\succneqq$         |                  | amssymb    |
| `\precnsim`         | $\precnsim$         |                  | amssymb    |
| `\succnsim`         | $\succnsim$         |                  | amssymb    |
| `\precnapprox`      | $\precnapprox$      |                  | amssymb    |
| `\succnapprox`      | $\succnapprox$      |                  | amssymb    |
| `\subsetneq`        | $\subsetneq$        | $\varsubsetneq$  | amssymb    |
| `\supsetneq`        | $\supsetneq$        | $\varsupsetneq$  | amssymb    |
| `\nsubseteq`        | $\nsubseteq$        |                  | amssymb    |
| `\nsupseteq`        | $\nsupseteq$        |                  | amssymb    |
| `\subsetneqq`       | $\subsetneqq$       | $\varsubsetneqq$ | amssymb    |
| `\supsetneqq`       | $\supsetneqq$       | $\varsupsetneqq$ | amssymb    |
| `\nsubseteqq`       | $\nsubseteqq$       |                  | amssymb    |
| `\nsupseteqq`       | $\nsupseteqq$       |                  | amssymb    |
| `\nmid`             | $\nmid$             |                  | amssymb    |
| `\nparallel`        | $\nparallel$        |                  | amssymb    |
| `\nshortmid`        | $\nshortmid$        |                  | amssymb    |
| `\nshortparallel`   | $\nshortparallel$   |                  | amssymb    |
| `\nsim`             | $\nsim$             |                  | amssymb    |
| `\ncong`            | $\ncong$            |                  | amssymb    |
| `\nvdash`           | $\nvdash$           |                  | amssymb    |
| `\nvDash`           | $\nvDash$           |                  | amssymb    |
| `\nVdash`           | $\nVdash$           |                  | amssymb    |
| `\nVDash`           | $\nVDash$           |                  | amssymb    |
| `\ntriangleleft`    | $\ntriangleleft$    |                  | amssymb    |
| `\ntriangleright`   | $\ntriangleright$   |                  | amssymb    |
| `\ntrianglelefteq`  | $\ntrianglelefteq$  |                  | amssymb    |
| `\ntrianglerighteq` | $\ntrianglerighteq$ |                  | amssymb    |
| `\nleftarrow`       | $\nleftarrow$       |                  | amssymb    |
| `\nrightarrow`      | $\nrightarrow$      |                  | amssymb    |
| `\nleftrightarrow`  | $\nleftrightarrow$  |                  | amssymb    |
| `\nLeftarrow`       | $\nLeftarrow$       |                  | amssymb    |
| `\nRightarrow`      | $\nRightarrow$      |                  | amssymb    |
| `\nLeftrightarrow`  | $\nLeftrightarrow$  |                  | amssymb    |

- **Change** symbol **style**
  | Preamble Command                             | Rendering        | Original      |
  | -------------------------------------------- | ---------------- | ------------- |
  | `\renewcommand{\subsetneq}{\varsubsetneq}`   | $\varsubsetneq$  | $\subsetneq$  |
  | `\renewcommand{\supsetneq}{\varsupsetneq}`   | $\varsupsetneq$  | $\supsetneq$  |
  | `\renewcommand{\subsetneqq}{\varsubsetneqq}` | $\varsubsetneqq$ | $\subsetneqq$ |
  | `\renewcommand{\supsetneqq}{\varsupsetneqq}` | $\varsupsetneqq$ | $\supsetneqq$ |

## Binary Operators
| Command               | Rendering             | Variants            | Dependency |
| --------------------- | --------------------- | ------------------- | ---------- |
| `+`                   | $+$                   |
| `-`                   | $-$                   |
| `\pm`                 | $\pm$                 |
| `\mp`                 | $\mp$                 |
| `\triangleleft`       | $\triangleleft$       | $\vartriangleleft$  |
| `\cdot`               | $\cdot$               |
| `\div`                | $\div$                |
| `\triangleright`      | $\triangleright$      | $\vartriangleright$ |
| `\times`              | $\times$              |
| `\setminus`           | $\setminus$           |
| `\star`               | $\star$               |
| `\cup`                | $\cup$                |
| `\cap`                | $\cap$                |
| `\ast`                | $\ast$                |
| `\sqcup`              | $\sqcup$              |
| `\sqcap`              | $\sqcap$              |
| `\circ`               | $\circ$               |
| `\vee` <br> `\lor`    | $\vee$ <br> $\lor$    |
| `\wedge` <br> `\land` | $\wedge$ <br> $\land$ |
| `\bullet`             | $\bullet$             |
| `\oplus`              | $\oplus$              |
| `\ominus`             | $\ominus$             |
| `\diamond`            | $\diamond$            |
| `\odot`               | $\odot$               |
| `\oslash`             | $\oslash$             |
| `\uplus`              | $\uplus$              |
| `\otimes`             | $\otimes$             |
| `\bigcirc`            | $\bigcirc$            |
| `\amalg`              | $\amalg$              |
| `\bigtriangleup`      | $\bigtriangleup$      |
| `\bigtriangledown`    | $\bigtriangledown$    |
| `\dagger`             | $\dagger$             |
| `\lhd`                | $\lhd$                |                     | latexsym   |
| `\rhd`                | $\rhd$                |                     | latexsym   |
| `\ddagger`            | $\ddagger$            |                     |
| `\unlhd`              | $\unlhd$              |                     | latexsym   |
| `\unrhd`              | $\unrhd$              |                     | latexsym   |
| `\wr`                 | $\wr$                 |
| `\dotplus`            | $\dotplus$            |                     | amssymb    |
| `\centerdot`          | $\centerdot$          |                     | amssymb    |
| `\ltimes`             | $\ltimes$             |                     | amssymb    |
| `\rtimes`             | $\rtimes$             |                     | amssymb    |
| `\divideontimes`      | $\divideontimes$      |                     | amssymb    |
| `\doublecup`          | $\doublecup$          |                     | amssymb    |
| `\doublecap`          | $\doublecap$          |                     | amssymb    |
| `\smallsetminus`      | $\smallsetminus$      |                     | amssymb    |
| `\veebar`             | $\veebar$             |                     | amssymb    |
| `\barwedge`           | $\barwedge$           |                     | amssymb    |
| `\doublebarwedge`     | $\doublebarwedge$     |                     | amssymb    |
| `\boxplus`            | $\boxplus$            |                     | amssymb    |
| `\boxminus`           | $\boxminus$           |                     | amssymb    |
| `\circleddash`        | $\circleddash$        |                     | amssymb    |
| `\boxtimes`           | $\boxtimes$           |                     | amssymb    |
| `\boxdot`             | $\boxdot$             |                     | amssymb    |
| `\circledcirc`        | $\circledcirc$        |                     | amssymb    |
| `\intercal`           | $\intercal$           |                     | amssymb    |
| `\circledast`         | $\circledast$         |                     | amssymb    |
| `\rightthreetimes`    | $\rightthreetimes$    |                     | amssymb    |
| `\curlyvee`           | $\curlyvee$           |                     | amssymb    |
| `\curlywedge`         | $\curlywedge$         |                     | amssymb    |
| `\leftthreetimes`     | $\leftthreetimes$     |                     | amssymb    |

- **Change** symbol **style**
  | Preamble Command                                   | Rendering           | Original         | Dependency |
  | -------------------------------------------------- | ------------------- | ---------------- | ---------- |
  | `\renewcommand{\triangleleft}{\vartriangleleft}`   | $\vartriangleleft$  | $\triangleleft$  | amssymb    |
  | `\renewcommand{\triangleright}{\vartriangleright}` | $\vartriangleright$ | $\triangleright$ | amssymb    |

## Big Operators
| Command      | Rendering    |
| ------------ | ------------ |
| `\sum`       | $\sum$       |
| `\bigcup`    | $\bigcup$    |
| `\bigvee`    | $\bigvee$    |
| `\prod`      | $\prod$      |
| `\bigcap`    | $\bigcap$    |
| `\bigwedge`  | $\bigwedge$  |
| `\coprod`    | $\coprod$    |
| `\bigsqcup`  | $\bigsqcup$  |
| `\biguplus`  | $\biguplus$  |
| `\int`       | $\int$       |
| `\oint`      | $\oint$      |
| `\bigodot`   | $\bigodot$   |
| `\bigoplus`  | $\bigoplus$  |
| `\bigotimes` | $\bigotimes$ |

## Arrows
| Command                   | Rendering                 | Dependency |
| ------------------------- | ------------------------- | ---------- |
| `\leftarrow` <br> `\gets` | $\leftarrow$ <br> $\gets$ |
| `\longleftarrow`          | $\longleftarrow$          |
| `\rightarrow` <br> `\to`  | $\rightarrow$ <br> $\to$  |
| `\longrightarrow`         | $\longrightarrow$         |
| `\leftrightarrow`         | $\leftrightarrow$         |
| `\longleftrightarrow`     | $\longleftrightarrow$     |
| `\Leftarrow`              | $\Leftarrow$              |
| `\Longleftarrow`          | $\Longleftarrow$          |
| `\Rightarrow`             | $\Rightarrow$             |
| `\Longrightarrow`         | $\Longrightarrow$         |
| `\Leftrightarrow`         | $\Leftrightarrow$         |
| `\Longleftrightarrow`     | $\Longleftrightarrow$     |
| `\iff`                    | $\iff$ (bigger spaces)    |
| `\mapsto`                 | $\mapsto$                 |
| `\longmapsto`             | $\longmapsto$             |
| `\hookleftarrow`          | $\hookleftarrow$          |
| `\hookrightarrow`         | $\hookrightarrow$         |
| `\leftharpoonup`          | $\leftharpoonup$          |
| `\rightharpoonup`         | $\rightharpoonup$         |
| `\leftharpoondown`        | $\leftharpoondown$        |
| `\rightharpoondown`       | $\rightharpoondown$       |
| `\rightleftharpoons`      | $\rightleftharpoons$      |
| `\uparrow`                | $\uparrow$                |
| `\downarrow`              | $\downarrow$              |
| `\updownarrow`            | $\updownarrow$            |
| `\Uparrow`                | $\Uparrow$                |
| `\Downarrow`              | $\Downarrow$              |
| `\Updownarrow`            | $\Updownarrow$            |
| `\nearrow`                | $\nearrow$                |
| `\searrow`                | $\searrow$                |
| `\swarrow`                | $\swarrow$                |
| `\nwarrow`                | $\nwarrow$                |
| `\leadsto`                | $\leadsto$                | latexsym   |
| `\dashleftarrow`          | $\dashleftarrow$          | amssymb    |
| `\dashrightarrow`         | $\dashrightarrow$         | amssymb    |
| `\leftleftarrows`         | $\leftleftarrows$         | amssymb    |
| `\rightrightarrows`       | $\rightrightarrows$       | amssymb    |
| `\leftrightarrows`        | $\leftrightarrows$        | amssymb    |
| `\rightleftarrows`        | $\rightleftarrows$        | amssymb    |
| `\Lleftarrow`             | $\Lleftarrow$             | amssymb    |
| `\Rrightarrow`            | $\Rrightarrow$            | amssymb    |
| `\twoheadleftarrow`       | $\twoheadleftarrow$       | amssymb    |
| `\twoheadrightarrow`      | $\twoheadrightarrow$      | amssymb    |
| `\leftarrowtail`          | $\leftarrowtail$          | amssymb    |
| `\rightarrowtail`         | $\rightarrowtail$         | amssymb    |
| `\leftrightharpoons`      | $\leftrightharpoons$      | amssymb    |
| `\rightleftharpoons`      | $\rightleftharpoons$      | amssymb    |
| `\Lsh`                    | $\Lsh$                    | amssymb    |
| `\Rsh`                    | $\Rsh$                    | amssymb    |
| `\looparrowleft`          | $\looparrowleft$          | amssymb    |
| `\looparrowright`         | $\looparrowright$         | amssymb    |
| `\curvearrowleft`         | $\curvearrowleft$         | amssymb    |
| `\curvearrowright`        | $\curvearrowright$        | amssymb    |
| `\circlearrowleft`        | $\circlearrowleft$        | amssymb    |
| `\circlearrowright`       | $\circlearrowright$       | amssymb    |
| `\multimap`               | $\multimap$               | amssymb    |
| `\upuparrows`             | $\upuparrows$             | amssymb    |
| `\downdownarrows`         | $\downdownarrows$         | amssymb    |
| `\upharpoonleft`          | $\upharpoonleft$          | amssymb    |
| `\upharpoonright`         | $\upharpoonright$         | amssymb    |
| `\downharpoonright`       | $\downharpoonright$       | amssymb    |
| `\rightsquigarrow`        | $\rightsquigarrow$        | amssymb    |
| `\leftrightsquigarrow`    | $\leftrightsquigarrow$    | amssymb    |

## Arrows as Accents
| Command                    | Rendering                  |
| -------------------------- | -------------------------- |
| `\overrightarrow{AB}`      | $\overrightarrow{AB}$      |
| `\underrightarrow{AB}`     | $\underrightarrow{AB}$     |
| `\overleftarrow{AB}`       | $\overleftarrow{AB}$       |
| `\underleftarrow{AB}`      | $\underleftarrow{AB}$      |
| `\overleftrightarrow{AB}`  | $\overleftrightarrow{AB}$  |
| `\underleftrightarrow{AB}` | $\underleftrightarrow{AB}$ |

## Delimiters
| Command             | Rendering             | Dependency       |
| ------------------- | --------------------- | ---------------- |
| `(`                 | $($                   |
| `)`                 | $)$                   |
| `\uparrow`          | $\uparrow$            |
| `\lbrack` <br> `[`  | $\lbrack$ <br> $[$    |
| `\rbrack` <br> `]`  | $\rbrack$ <br> $]$    |
| `\downarrow`        | $\downarrow$          |
| `\lbrace` <br> `\{` | $\lbrace$ <br> $\\\{$ |
| `\rbrace` <br> `\}` | $\rbrace$ <br> $\\\}$ |
| `\updownarrow`      | $\updownarrow$        |
| `\langle`           | $\langle$             |
| `\rangle`           | $\rangle$             |
| `\Uparrow`          | $\Uparrow$            |
| `\vert` <br> `\|`   | $\vert$ <br> $\|$     |
| `\Vert` <br> `\\|`  | $\Vert$ <br> $\\|$    |
| `\Downarrow`        | $\Downarrow$          |
| `/`                 | $/$                   |
| `\backslash`        | $\backslash$          |
| `\Updownarrow`      | $\Updownarrow$        |
| `\lfloor`           | $\lfloor$             |
| `\rfloor`           | $\rfloor$             |
| `\rceil`            | $\rceil$              |
| `\lceil`            | $\lceil$              |
| `\ulcorner`         | $\ulcorner$           | amssymb          |
| `\urcorner`         | $\urcorner$           | amssymb          |
| `\llcorner`         | $\llcorner$           | amssymb          |
| `\lrcorner`         | $\lrcorner$           | amssymb          |
| `\lvert`            | $\lvert$              | amssymb, amsmath |
| `\rvert`            | $\rvert$              | amssymb, amsmath |
| `\lVert`            | $\lVert$              | amssymb, amsmath |
| `\rVert`            | $\rVert$              | amssymb, amsmath |

## Large Delimiters
| Command       | Rendering     |
| ------------- | ------------- |
| `\lgroup`     | $\lgroup$     |
| `\rgroup`     | $\rgroup$     |
| `\lmoustache` | $\lmoustache$ |
| `\arrowvert`  | $\arrowvert$  |
| `\Arrowvert`  | $\Arrowvert$  |
| `\bracevert`  | $\bracevert$  |
| `\rmoustache` | $\rmoustache$ |

## Miscellaneous Symbols
| Command              | Rendering            | Variants       | Dependency |
| -------------------- | -------------------- | -------------- | ---------- |
| `\dots`              | $\dots$              |
| `\cdots`             | $\cdots$             |
| `\vdots`             | $\vdots$             |
| `\ddots`             | $\ddots$             |
| `\hbar`              | $\hbar$              |
| `\imath`             | $\imath$             |
| `\jmath`             | $\jmath$             |
| `\ell`               | $\ell$               |
| `\Re`                | $\Re$                |
| `\Im`                | $\Im$                |
| `\aleph`             | $\aleph$             |
| `\wp`                | $\wp$                |
| `\forall`            | $\forall$            |
| `\exists`            | $\exists$            |
| `\mho`               | $\mho$               |                | latexsym   |
| `\partial`           | $\partial$           |
| `'`                  | $'$                  |
| `\prime`             | $\prime$             |
| `\emptyset`          | $\emptyset$          |
| `\infty`             | $\infty$             |
| `\nabla`             | $\nabla$             |
| `\triangle`          | $\triangle$          | $\vartriangle$ | amssymb    |
| `\Box`               | $\Box$               |                | latexsym   |
| `\Diamond`           | $\Diamond$           |                | latexsym   |
| `\bot`               | $\bot$               |
| `\top`               | $\top$               |
| `\angle`             | $\angle$             |
| `\surd`              | $\surd$              |
| `\diamondsuit`       | $\diamondsuit$       |
| `\heartsuit`         | $\heartsuit$         |
| `\clubsuit`          | $\clubsuit$          |
| `\spadesuit`         | $\spadesuit$         |
| `\neg` <br> `\lnot`  | $\neg$ <br> $\lnot$  |
| `\flat`              | $\flat$              |
| `\natural`           | $\natural$           |
| `\sharp`             | $\sharp$             |
| `\square`            | $\square$            |                | amssymb    |
| `\vartriangle`       | $\vartriangle$       |                | amssymb    |
| `\triangledown`      | $\triangledown$      |                | amssymb    |
| `\lozenge`           | $\lozenge$           |                | amssymb    |
| `\diagup`            | $\diagup$            |                | amssymb    |
| `\hslash`            | $\hslash$            |                | amssymb    |
| `\blacksquare`       | $\blacksquare$       |                | amssymb    |
| `\blacktriangle`     | $\blacktriangle$     |                | amssymb    |
| `\blacktriangledown` | $\blacktriangledown$ |                | amssymb    |
| `\blacklozenge`      | $\blacklozenge$      |                | amssymb    |
| `\measuredangle`     | $\measuredangle$     |                | amssymb    |
| `\diagdown`          | $\diagdown$          |                | amssymb    |
| `\nexists`           | $\nexists$           |                | amssymb    |
| `\Finv`              | $\Finv$              |                | amssymb    |
| `\eth`               | $\eth$               |                | amssymb    |
| `\sphericalangle`    | $\sphericalangle$    |                | amssymb    |
| `\Bbbk`              | $\Bbbk$              |                | amssymb    |
| `\circledS`          | $\circledS$          |                | amssymb    |
| `\complement`        | $\complement$        |                | amssymb    |
| `\Game`              | $\Game$              |                | amssymb    |
| `\bigstar`           | $\bigstar$           |                | amssymb    |
| `\backprime`         | $\backprime$         |                | amssymb    |
| `\varnothing`        | $\varnothing$        |                | amssymb    |
| `\mho`               | $\mho$               |                | amssymb    |

- **Change** symbol **style**
  | Preamble Command                         | Rendering      | Original    | Dependency |
  | ---------------------------------------- | -------------- | ----------- | ---------- |
  | `\renewcommand{\triangle}{\vartriangle}` | $\vartriangle$ | $\triangle$ | amssymb    |

## Math Alphabets
> example TEXT: `ABCDEabcde1234`

| Command             | Rendering                     | Dependency          |
| ------------------- | ----------------------------- | ------------------- |
| `\mathrm{TEXT}`     | $\mathrm{ABCDEabcde1234}$     |
| `\mathit{TEXT}`     | $\mathit{ABCDEabcde1234}$     |
| `\mathnormal{TEXT}` | $\mathnormal{ABCDEabcde1234}$ |
| `\mathcal{TEXT}`    | $\mathcal{ABCDE}$             |
| `\mathscr{TEXT}`    | $\mathscr{ABCDE}$             | mathrsfs            |
| `\mathfrak{TEXT}`   | $\mathfrak{ABCDEabcde1234}$   | amsfonts or amssymb |
| `\mathbb{TEXT}`     | $\mathbb{ABCDE}$              | amsfonts or amssymb |


# Sources

- 2022-06-10: [The Not So Short Introduction to LaTeX2e](https://tobi.oetiker.ch/lshort/lshort.pdf)
- 2022-06-10: [LaTeX Math Symbols Cheat Sheet - Kapeli](https://kapeli.com/cheat_sheets/LaTeX_Math_Symbols.docset/Contents/Resources/Documents/index)
- 2022-06-10: [LaTeX Math for Undergrads](http://tug.ctan.org/info/undergradmath/undergradmath.pdf)
- 2022-06-10: [List of mathematical symbols by subject - Wikipedia](https://en.wikipedia.org/wiki/List_of_mathematical_symbols_by_subject)