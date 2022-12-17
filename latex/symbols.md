<h1> Symbols </h1>



> Commands for Mathematical Expressions, Symbols, Operators and Relations

Table of Contents
- [Favorites](#favorites)
- [Non-Mathematical Symbols](#non-mathematical-symbols)
- [Money and currencies](#money-and-currencies)
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

| Command                                 | Rendering      | Name or _Function_                   | Usage Example                      |
| --------------------------------------- | -------------- | ------------------------------------ | ---------------------------------- |
| `-`                                     | -              | hyphen                               | daughter-in-law, X-rated           |
| `--`                                    | –              | en-dash                              | pages 13–67                        |
| `---`                                   | —              | em-dash                              | yes—or no?                         |
| `$-1$`                                  | −              | minus-sign                           | 0, 1 and −1                        |
| `/`                                     | /              | _prevents hyphenation_               | 5 MB/s                             |
| `\slash{}`                              | /              | _supports hyphenation_               | read/write                         |
| `\ldots{}`                              | …              | ellipsis                             | a, b, c, …                         |
| `Mr.~Smith`                             | Mr.&#160;Smith | _suppresses bigger sentence spacing_ | Did ⠀Mr.&#160;Smith ⠀win ⠀today?   |
| `\dag{}`                                | †              | Dagger                               |
| `\ddag{}`                               | ‡              | Double Dagger                        |
| `\S{}`                                  | §              | Section Sign                         |
| `\P{}`                                  | ¶              | Pilcrow Sign                         |
| `\%{}`                                  | %              | Percent Sign                         |
| `\textsuperscript{\textcopyright}`      | ©              | Copyright Sign                       |
| `\textsuperscript{\textregistered}`     | ®              | Registered Trade Mark Sign           |
| `\texttrademark{}`                      | ™              | Trade Mark Sign                      |
| `\unit{\degree}` <br> `\textdegree{}`   | °              | Degree Sign                          | [siunitx][siunitx] <br> _built in_ |
| `\ang{5}`                               | 5°             | Angle                                | [siunitx][siunitx]                 |
| `\unit{\celsius}` <br> `\textcelsius{}` | ℃              | Degree Celsius                       | [siunitx][siunitx] <br> _built in_ |
| `\qty{5}{\celsius}`                     | 5 ℃            |                                      | [siunitx][siunitx]                 |


## Money and currencies
> `€`, `\$`, `pounds` and `\yen` are not recommended

| Command      | Rendering | Dependency                               |
| ------------ | --------- | ---------------------------------------- |
| `\cEUR{}`    | €         | [currency][currency] + `\DefineCurrency` |
| `\cUSD{}`    | $         | [currency][currency] + `\DefineCurrency` |
| `\cJPY{}`    | ¥         | [currency][currency] + `\DefineCurrency` |
| `\cGBP{}`    | £         | [currency][currency] + `\DefineCurrency` |
| `\dEUR{1.5}` | 1.50 €    | [currency][currency] + `\DefineCurrency` |
| `\dUSD{1.5}` | $ 1.50    | [currency][currency] + `\DefineCurrency` |
| `\dJPY{1.5}` | 2 ¥       | [currency][currency] + `\DefineCurrency` |
| `\dGBP{1.5}` | £ 1.50    | [currency][currency] + `\DefineCurrency` |

- **Define currencies** in the preamble  
  ```latex
  \DefineCurrency{EUR}{name={euro}, plural={euros}, symbol={\euro}, iso={EUR}}
  \DefineCurrency{USD}{name={dollar}, plural={dollars}, symbol={\$}, iso={USD}, pre=true}
  \DefineCurrency{JPY}{name={yen}, plural={yens}, symbol={\yen}, iso={JPY}, cents=false}
  \DefineCurrency{GBP}{name={pound}, plural={pounds}, symbol={\pounds}, iso={GBP}, pre=true}
  \CurrencySetup{kind=symbol}
  ```
- **Format** money by calling `\CurrencySetup{�}` with
  | Key=Default  | Options                           | Affect                                |
  | ------------ | --------------------------------- | ------------------------------------- |
  | `kind=`iso   | `iso`, `plural`, `name`, `symbol` | Representation of the monetary unit   |
  | `pre=`false  | `true`, `false`                   | Print currency before the value?      |
  | `cents=`true | `true`, `false`, `always`         | Control the way the cents are printed |
  
  See [further options][currency] or set decimal marker inside `\sisetup{locale=DE}`


## Degree Symbols
| Command           | Rendering        | Dependency         |
| ----------------- | ---------------- | ------------------ |
| `^\circ`          | $^\circ$         |                    |
| `\unit{\degree}`  | $^\circ$         | [siunitx][siunitx] |
| `\unit{\celsius}` | $^\circ\text{C}$ | [siunitx][siunitx] |

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
| `\digamma`  | $\digamma$  |               | [amssymb][amssymb] |
| `\varkappa` | $\varkappa$ |               | [amssymb][amssymb] |

- Change letter style
    | Preamble Command                       | Rendering     | Original   | Dependency         |
    | -------------------------------------- | ------------- | ---------- | ------------------ |
    | `\renewcommand{\epsilon}{\varepsilon}` | $\varepsilon$ | $\epsilon$ |
    | `\renewcommand{\theta}{\vartheta}`     | $\vartheta$   | $\theta$   |
    | `\renewcommand{\kappa}{\varkappa}`     | $\varkappa$   | $\kappa$   | [amssymb][amssymb] |
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
| Command   | Rendering | Dependency         |
| --------- | --------- | ------------------ |
| `\beth`   | $\beth$   | [amssymb][amssymb] |
| `\gimel`  | $\gimel$  | [amssymb][amssymb] |
| `\daleth` | $\daleth$ | [amssymb][amssymb] |

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

| Command               | Rendering             | Variants                                    | Dependency           |
| --------------------- | --------------------- | ------------------------------------------- | -------------------- |
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
| `\sqsubset`           | $\sqsubset$           | $\not\sqsubset$                             | [latexsym][latexsym] |
| `\sqsupset`           | $\sqsupset$           | $\not\sqsupset$                             | [latexsym][latexsym] |
| `\Join`               | $\Join$               | $\not\Join$                                 | [latexsym][latexsym] |
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
| `\lessdot`            | $\lessdot$            | $\not\lessdot$                              | [amssymb][amssymb]   |
| `\gtrdot`             | $\gtrdot$             | $\not\gtrdot$                               | [amssymb][amssymb]   |
| `\doteqdot`           | $\doteqdot$           | $\not\doteqdot$                             | [amssymb][amssymb]   |
| `\leqslant`           | $\leqslant$           | $\not\leqslant$                             | [amssymb][amssymb]   |
| `\geqslant`           | $\geqslant$           | $\not\geqslant$                             | [amssymb][amssymb]   |
| `\risingdotseq`       | $\risingdotseq$       | $\not\risingdotseq$                         | [amssymb][amssymb]   |
| `\eqslantless`        | $\eqslantless$        | $\not\eqslantless$                          | [amssymb][amssymb]   |
| `\eqslantgtr`         | $\eqslantgtr$         | $\not\eqslantgtr$                           | [amssymb][amssymb]   |
| `\fallingdotseq`      | $\fallingdotseq$      | $\not\fallingdotseq$                        | [amssymb][amssymb]   |
| `\leqq`               | $\leqq$               | $\not\leqq$                                 | [amssymb][amssymb]   |
| `\geqq`               | $\geqq$               | $\not\geqq$                                 | [amssymb][amssymb]   |
| `\eqcirc`             | $\eqcirc$             | $\not\eqcirc$                               | [amssymb][amssymb]   |
| `\lll`                | $\lll$                | $\not\lll$                                  | [amssymb][amssymb]   |
| `\llless`             | $\llless$             | $\not\llless$                               | [amssymb][amssymb]   |
| `\ggg`                | $\ggg$                | $\not\ggg$                                  | [amssymb][amssymb]   |
| `\circeq`             | $\circeq$             | $\not\circeq$                               | [amssymb][amssymb]   |
| `\lesssim`            | $\lesssim$            | $\not\lesssim$                              | [amssymb][amssymb]   |
| `\gtrsim`             | $\gtrsim$             | $\not\gtrsim$                               | [amssymb][amssymb]   |
| `\triangleq`          | $\triangleq$          | $\not\triangleq$                            | [amssymb][amssymb]   |
| `\lessapprox`         | $\lessapprox$         | $\not\lessapprox$                           | [amssymb][amssymb]   |
| `\gtrapprox`          | $\gtrapprox$          | $\not\gtrapprox$                            | [amssymb][amssymb]   |
| `\bumpeq`             | $\bumpeq$             | $\not\bumpeq$                               | [amssymb][amssymb]   |
| `\lessgtr`            | $\lessgtr$            | $\not\lessgtr$                              | [amssymb][amssymb]   |
| `\gtrless`            | $\gtrless$            | $\not\gtrless$                              | [amssymb][amssymb]   |
| `\Bumpeq`             | $\Bumpeq$             | $\not\Bumpeq$                               | [amssymb][amssymb]   |
| `\lesseqgtr`          | $\lesseqgtr$          | $\not\lesseqgtr$                            | [amssymb][amssymb]   |
| `\gtreqless`          | $\gtreqless$          | $\not\gtreqless$                            | [amssymb][amssymb]   |
| `\thicksim`           | $\thicksim$           | $\not\thicksim$                             | [amssymb][amssymb]   |
| `\lesseqqgtr`         | $\lesseqqgtr$         | $\not\lesseqqgtr$                           | [amssymb][amssymb]   |
| `\gtreqqless`         | $\gtreqqless$         | $\not\gtreqqless$                           | [amssymb][amssymb]   |
| `\thickapprox`        | $\thickapprox$        | $\not\thickapprox$                          | [amssymb][amssymb]   |
| `\preccurlyeq`        | $\preccurlyeq$        | $\not\preccurlyeq$                          | [amssymb][amssymb]   |
| `\succcurlyeq`        | $\succcurlyeq$        | $\not\succcurlyeq$                          | [amssymb][amssymb]   |
| `\approxeq`           | $\approxeq$           | $\not\approxeq$                             | [amssymb][amssymb]   |
| `\curlyeqprec`        | $\curlyeqprec$        | $\not\curlyeqprec$                          | [amssymb][amssymb]   |
| `\curlyeqsucc`        | $\curlyeqsucc$        | $\not\curlyeqsucc$                          | [amssymb][amssymb]   |
| `\backsim`            | $\backsim$            | $\not\backsim$                              | [amssymb][amssymb]   |
| `\precsim`            | $\precsim$            | $\not\precsim$                              | [amssymb][amssymb]   |
| `\succsim`            | $\succsim$            | $\not\succsim$                              | [amssymb][amssymb]   |
| `\backsimeq`          | $\backsimeq$          | $\not\backsimeq$                            | [amssymb][amssymb]   |
| `\precapprox`         | $\precapprox$         | $\not\precapprox$                           | [amssymb][amssymb]   |
| `\succapprox`         | $\succapprox$         | $\not\succapprox$                           | [amssymb][amssymb]   |
| `\vDash`              | $\vDash$              | $\not\vDash$                                | [amssymb][amssymb]   |
| `\subseteqq`          | $\subseteqq$          | $\not\subseteqq$                            | [amssymb][amssymb]   |
| `\supseteqq`          | $\supseteqq$          | $\not\supseteqq$                            | [amssymb][amssymb]   |
| `\Vdash`              | $\Vdash$              | $\not\Vdash$                                | [amssymb][amssymb]   |
| `\shortparallel`      | $\shortparallel$      | $\not\shortparallel$                        | [amssymb][amssymb]   |
| `\Supset`             | $\Supset$             | $\not\Supset$                               | [amssymb][amssymb]   |
| `\Vvdash`             | $\Vvdash$             | $\not\Vvdash$                               | [amssymb][amssymb]   |
| `\blacktriangleleft`  | $\blacktriangleleft$  | $\not\blacktriangleleft$                    | [amssymb][amssymb]   |
| `\sqsupset`           | $\sqsupset$           | $\not\sqsupset$                             | [amssymb][amssymb]   |
| `\backepsilon`        | $\backepsilon$        | $\not\backepsilon$                          | [amssymb][amssymb]   |
| `\vartriangleright`   | $\vartriangleright$   | $\not\vartriangleright$                     | [amssymb][amssymb]   |
| `\because`            | $\because$            | $\not\because$                              | [amssymb][amssymb]   |
| `\varpropto`          | $\varpropto$          | $\not\varpropto$                            | [amssymb][amssymb]   |
| `\blacktriangleright` | $\blacktriangleright$ | $\not\blacktriangleright$                   | [amssymb][amssymb]   |
| `\Subset`             | $\Subset$             | $\not\Subset$                               | [amssymb][amssymb]   |
| `\between`            | $\between$            | $\not\between$                              | [amssymb][amssymb]   |
| `\trianglerighteq`    | $\trianglerighteq$    | $\not\trianglerighteq$                      | [amssymb][amssymb]   |
| `\smallfrown`         | $\smallfrown$         | $\not\smallfrown$                           | [amssymb][amssymb]   |
| `\pitchfork`          | $\pitchfork$          | $\not\pitchfork$                            | [amssymb][amssymb]   |
| `\vartriangleleft`    | $\vartriangleleft$    | $\not\vartriangleleft$                      | [amssymb][amssymb]   |
| `\shortmid`           | $\shortmid$           | $\not\shortmid$                             | [amssymb][amssymb]   |
| `\smallsmile`         | $\smallsmile$         | $\not\smallsmile$                           | [amssymb][amssymb]   |
| `\trianglelefteq`     | $\trianglelefteq$     | $\not\trianglelefteq$                       | [amssymb][amssymb]   |
| `\therefore`          | $\therefore$          | $\not\therefore$                            | [amssymb][amssymb]   |
| `\sqsubset`           | $\sqsubset$           | $\not\sqsubset$                             | [amssymb][amssymb]   |

- **Use primitively negated symbol**  
  Not recommended, use [properly negated symbols](#negated-binary-relations-and-arrows) instead.  
  Prefix the command with `\not` like `\not\leq`.  

- **Change** symbol **style**
  | Preamble Command                     | Rendering    | Original  | Dependency         |
  | ------------------------------------ | ------------ | --------- | ------------------ |
  | `\renewcommand{\propto}{\varpropto}` | $\varpropto$ | $\propto$ | [amssymb][amssymb] |

## Negated Binary Relations and Arrows
| Command             | Rendering           | Variants         | Dependency         |
| ------------------- | ------------------- | ---------------- | ------------------ |
| `\neq` <br> `\ne`   | $\neq$ <br> $\ne$   |                  |
| `\notin`            | $\notin$            |                  |
| `\nless`            | $\nless$            |                  | [amssymb][amssymb] |
| `\ngtr`             | $\ngtr$             |                  | [amssymb][amssymb] |
| `\lneq`             | $\lneq$             |                  | [amssymb][amssymb] |
| `\gneq`             | $\gneq$             |                  | [amssymb][amssymb] |
| `\nleq`             | $\nleq$             |                  | [amssymb][amssymb] |
| `\ngeq`             | $\ngeq$             |                  | [amssymb][amssymb] |
| `\nleqslant`        | $\nleqslant$        |                  | [amssymb][amssymb] |
| `\ngeqslant`        | $\ngeqslant$        |                  | [amssymb][amssymb] |
| `\lneqq`            | $\lneqq$            |                  | [amssymb][amssymb] |
| `\gneqq`            | $\gneqq$            |                  | [amssymb][amssymb] |
| `\lvertneqq`        | $\lvertneqq$        |                  | [amssymb][amssymb] |
| `\gvertneqq`        | $\gvertneqq$        |                  | [amssymb][amssymb] |
| `\nleqq`            | $\nleqq$            |                  | [amssymb][amssymb] |
| `\ngeqq`            | $\ngeqq$            |                  | [amssymb][amssymb] |
| `\lnsim`            | $\lnsim$            |                  | [amssymb][amssymb] |
| `\gnsim`            | $\gnsim$            |                  | [amssymb][amssymb] |
| `\lnapprox`         | $\lnapprox$         |                  | [amssymb][amssymb] |
| `\gnapprox`         | $\gnapprox$         |                  | [amssymb][amssymb] |
| `\nprec`            | $\nprec$            |                  | [amssymb][amssymb] |
| `\nsucc`            | $\nsucc$            |                  | [amssymb][amssymb] |
| `\npreceq`          | $\npreceq$          |                  | [amssymb][amssymb] |
| `\nsucceq`          | $\nsucceq$          |                  | [amssymb][amssymb] |
| `\precneqq`         | $\precneqq$         |                  | [amssymb][amssymb] |
| `\succneqq`         | $\succneqq$         |                  | [amssymb][amssymb] |
| `\precnsim`         | $\precnsim$         |                  | [amssymb][amssymb] |
| `\succnsim`         | $\succnsim$         |                  | [amssymb][amssymb] |
| `\precnapprox`      | $\precnapprox$      |                  | [amssymb][amssymb] |
| `\succnapprox`      | $\succnapprox$      |                  | [amssymb][amssymb] |
| `\subsetneq`        | $\subsetneq$        | $\varsubsetneq$  | [amssymb][amssymb] |
| `\supsetneq`        | $\supsetneq$        | $\varsupsetneq$  | [amssymb][amssymb] |
| `\nsubseteq`        | $\nsubseteq$        |                  | [amssymb][amssymb] |
| `\nsupseteq`        | $\nsupseteq$        |                  | [amssymb][amssymb] |
| `\subsetneqq`       | $\subsetneqq$       | $\varsubsetneqq$ | [amssymb][amssymb] |
| `\supsetneqq`       | $\supsetneqq$       | $\varsupsetneqq$ | [amssymb][amssymb] |
| `\nsubseteqq`       | $\nsubseteqq$       |                  | [amssymb][amssymb] |
| `\nsupseteqq`       | $\nsupseteqq$       |                  | [amssymb][amssymb] |
| `\nmid`             | $\nmid$             |                  | [amssymb][amssymb] |
| `\nparallel`        | $\nparallel$        |                  | [amssymb][amssymb] |
| `\nshortmid`        | $\nshortmid$        |                  | [amssymb][amssymb] |
| `\nshortparallel`   | $\nshortparallel$   |                  | [amssymb][amssymb] |
| `\nsim`             | $\nsim$             |                  | [amssymb][amssymb] |
| `\ncong`            | $\ncong$            |                  | [amssymb][amssymb] |
| `\nvdash`           | $\nvdash$           |                  | [amssymb][amssymb] |
| `\nvDash`           | $\nvDash$           |                  | [amssymb][amssymb] |
| `\nVdash`           | $\nVdash$           |                  | [amssymb][amssymb] |
| `\nVDash`           | $\nVDash$           |                  | [amssymb][amssymb] |
| `\ntriangleleft`    | $\ntriangleleft$    |                  | [amssymb][amssymb] |
| `\ntriangleright`   | $\ntriangleright$   |                  | [amssymb][amssymb] |
| `\ntrianglelefteq`  | $\ntrianglelefteq$  |                  | [amssymb][amssymb] |
| `\ntrianglerighteq` | $\ntrianglerighteq$ |                  | [amssymb][amssymb] |
| `\nleftarrow`       | $\nleftarrow$       |                  | [amssymb][amssymb] |
| `\nrightarrow`      | $\nrightarrow$      |                  | [amssymb][amssymb] |
| `\nleftrightarrow`  | $\nleftrightarrow$  |                  | [amssymb][amssymb] |
| `\nLeftarrow`       | $\nLeftarrow$       |                  | [amssymb][amssymb] |
| `\nRightarrow`      | $\nRightarrow$      |                  | [amssymb][amssymb] |
| `\nLeftrightarrow`  | $\nLeftrightarrow$  |                  | [amssymb][amssymb] |

- **Change** symbol **style**
  | Preamble Command                             | Rendering        | Original      |
  | -------------------------------------------- | ---------------- | ------------- |
  | `\renewcommand{\subsetneq}{\varsubsetneq}`   | $\varsubsetneq$  | $\subsetneq$  |
  | `\renewcommand{\supsetneq}{\varsupsetneq}`   | $\varsupsetneq$  | $\supsetneq$  |
  | `\renewcommand{\subsetneqq}{\varsubsetneqq}` | $\varsubsetneqq$ | $\subsetneqq$ |
  | `\renewcommand{\supsetneqq}{\varsupsetneqq}` | $\varsupsetneqq$ | $\supsetneqq$ |

## Binary Operators
| Command               | Rendering             | Variants            | Dependency           |
| --------------------- | --------------------- | ------------------- | -------------------- |
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
| `\lhd`                | $\lhd$                |                     | [latexsym][latexsym] |
| `\rhd`                | $\rhd$                |                     | [latexsym][latexsym] |
| `\ddagger`            | $\ddagger$            |                     |
| `\unlhd`              | $\unlhd$              |                     | [latexsym][latexsym] |
| `\unrhd`              | $\unrhd$              |                     | [latexsym][latexsym] |
| `\wr`                 | $\wr$                 |
| `\dotplus`            | $\dotplus$            |                     | [amssymb][amssymb]   |
| `\centerdot`          | $\centerdot$          |                     | [amssymb][amssymb]   |
| `\ltimes`             | $\ltimes$             |                     | [amssymb][amssymb]   |
| `\rtimes`             | $\rtimes$             |                     | [amssymb][amssymb]   |
| `\divideontimes`      | $\divideontimes$      |                     | [amssymb][amssymb]   |
| `\doublecup`          | $\doublecup$          |                     | [amssymb][amssymb]   |
| `\doublecap`          | $\doublecap$          |                     | [amssymb][amssymb]   |
| `\smallsetminus`      | $\smallsetminus$      |                     | [amssymb][amssymb]   |
| `\veebar`             | $\veebar$             |                     | [amssymb][amssymb]   |
| `\barwedge`           | $\barwedge$           |                     | [amssymb][amssymb]   |
| `\doublebarwedge`     | $\doublebarwedge$     |                     | [amssymb][amssymb]   |
| `\boxplus`            | $\boxplus$            |                     | [amssymb][amssymb]   |
| `\boxminus`           | $\boxminus$           |                     | [amssymb][amssymb]   |
| `\circleddash`        | $\circleddash$        |                     | [amssymb][amssymb]   |
| `\boxtimes`           | $\boxtimes$           |                     | [amssymb][amssymb]   |
| `\boxdot`             | $\boxdot$             |                     | [amssymb][amssymb]   |
| `\circledcirc`        | $\circledcirc$        |                     | [amssymb][amssymb]   |
| `\intercal`           | $\intercal$           |                     | [amssymb][amssymb]   |
| `\circledast`         | $\circledast$         |                     | [amssymb][amssymb]   |
| `\rightthreetimes`    | $\rightthreetimes$    |                     | [amssymb][amssymb]   |
| `\curlyvee`           | $\curlyvee$           |                     | [amssymb][amssymb]   |
| `\curlywedge`         | $\curlywedge$         |                     | [amssymb][amssymb]   |
| `\leftthreetimes`     | $\leftthreetimes$     |                     | [amssymb][amssymb]   |

- **Change** symbol **style**
  | Preamble Command                                   | Rendering           | Original         | Dependency         |
  | -------------------------------------------------- | ------------------- | ---------------- | ------------------ |
  | `\renewcommand{\triangleleft}{\vartriangleleft}`   | $\vartriangleleft$  | $\triangleleft$  | [amssymb][amssymb] |
  | `\renewcommand{\triangleright}{\vartriangleright}` | $\vartriangleright$ | $\triangleright$ | [amssymb][amssymb] |

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
| Command                   | Rendering                 | Dependency           |
| ------------------------- | ------------------------- | -------------------- |
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
| `\leadsto`                | $\leadsto$                | [latexsym][latexsym] |
| `\dashleftarrow`          | $\dashleftarrow$          | [amssymb][amssymb]   |
| `\dashrightarrow`         | $\dashrightarrow$         | [amssymb][amssymb]   |
| `\leftleftarrows`         | $\leftleftarrows$         | [amssymb][amssymb]   |
| `\rightrightarrows`       | $\rightrightarrows$       | [amssymb][amssymb]   |
| `\leftrightarrows`        | $\leftrightarrows$        | [amssymb][amssymb]   |
| `\rightleftarrows`        | $\rightleftarrows$        | [amssymb][amssymb]   |
| `\Lleftarrow`             | $\Lleftarrow$             | [amssymb][amssymb]   |
| `\Rrightarrow`            | $\Rrightarrow$            | [amssymb][amssymb]   |
| `\twoheadleftarrow`       | $\twoheadleftarrow$       | [amssymb][amssymb]   |
| `\twoheadrightarrow`      | $\twoheadrightarrow$      | [amssymb][amssymb]   |
| `\leftarrowtail`          | $\leftarrowtail$          | [amssymb][amssymb]   |
| `\rightarrowtail`         | $\rightarrowtail$         | [amssymb][amssymb]   |
| `\leftrightharpoons`      | $\leftrightharpoons$      | [amssymb][amssymb]   |
| `\rightleftharpoons`      | $\rightleftharpoons$      | [amssymb][amssymb]   |
| `\Lsh`                    | $\Lsh$                    | [amssymb][amssymb]   |
| `\Rsh`                    | $\Rsh$                    | [amssymb][amssymb]   |
| `\looparrowleft`          | $\looparrowleft$          | [amssymb][amssymb]   |
| `\looparrowright`         | $\looparrowright$         | [amssymb][amssymb]   |
| `\curvearrowleft`         | $\curvearrowleft$         | [amssymb][amssymb]   |
| `\curvearrowright`        | $\curvearrowright$        | [amssymb][amssymb]   |
| `\circlearrowleft`        | $\circlearrowleft$        | [amssymb][amssymb]   |
| `\circlearrowright`       | $\circlearrowright$       | [amssymb][amssymb]   |
| `\multimap`               | $\multimap$               | [amssymb][amssymb]   |
| `\upuparrows`             | $\upuparrows$             | [amssymb][amssymb]   |
| `\downdownarrows`         | $\downdownarrows$         | [amssymb][amssymb]   |
| `\upharpoonleft`          | $\upharpoonleft$          | [amssymb][amssymb]   |
| `\upharpoonright`         | $\upharpoonright$         | [amssymb][amssymb]   |
| `\downharpoonright`       | $\downharpoonright$       | [amssymb][amssymb]   |
| `\rightsquigarrow`        | $\rightsquigarrow$        | [amssymb][amssymb]   |
| `\leftrightsquigarrow`    | $\leftrightsquigarrow$    | [amssymb][amssymb]   |

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
| Command             | Rendering             | Dependency                             |
| ------------------- | --------------------- | -------------------------------------- |
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
| `\ulcorner`         | $\ulcorner$           | [amssymb][amssymb]                     |
| `\urcorner`         | $\urcorner$           | [amssymb][amssymb]                     |
| `\llcorner`         | $\llcorner$           | [amssymb][amssymb]                     |
| `\lrcorner`         | $\lrcorner$           | [amssymb][amssymb]                     |
| `\lvert`            | $\lvert$              | [amssymb][amssymb], [amsmath][amsmath] |
| `\rvert`            | $\rvert$              | [amssymb][amssymb], [amsmath][amsmath] |
| `\lVert`            | $\lVert$              | [amssymb][amssymb], [amsmath][amsmath] |
| `\rVert`            | $\rVert$              | [amssymb][amssymb], [amsmath][amsmath] |

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
| Command              | Rendering            | Variants       | Dependency           |
| -------------------- | -------------------- | -------------- | -------------------- |
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
| `\mho`               | $\mho$               |                | [latexsym][latexsym] |
| `\partial`           | $\partial$           |
| `'`                  | $'$                  |
| `\prime`             | $\prime$             |
| `\emptyset`          | $\emptyset$          |
| `\infty`             | $\infty$             |
| `\nabla`             | $\nabla$             |
| `\triangle`          | $\triangle$          | $\vartriangle$ | [amssymb][amssymb]   |
| `\Box`               | $\Box$               |                | [latexsym][latexsym] |
| `\Diamond`           | $\Diamond$           |                | [latexsym][latexsym] |
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
| `\square`            | $\square$            |                | [amssymb][amssymb]   |
| `\vartriangle`       | $\vartriangle$       |                | [amssymb][amssymb]   |
| `\triangledown`      | $\triangledown$      |                | [amssymb][amssymb]   |
| `\lozenge`           | $\lozenge$           |                | [amssymb][amssymb]   |
| `\diagup`            | $\diagup$            |                | [amssymb][amssymb]   |
| `\hslash`            | $\hslash$            |                | [amssymb][amssymb]   |
| `\blacksquare`       | $\blacksquare$       |                | [amssymb][amssymb]   |
| `\blacktriangle`     | $\blacktriangle$     |                | [amssymb][amssymb]   |
| `\blacktriangledown` | $\blacktriangledown$ |                | [amssymb][amssymb]   |
| `\blacklozenge`      | $\blacklozenge$      |                | [amssymb][amssymb]   |
| `\measuredangle`     | $\measuredangle$     |                | [amssymb][amssymb]   |
| `\diagdown`          | $\diagdown$          |                | [amssymb][amssymb]   |
| `\nexists`           | $\nexists$           |                | [amssymb][amssymb]   |
| `\Finv`              | $\Finv$              |                | [amssymb][amssymb]   |
| `\eth`               | $\eth$               |                | [amssymb][amssymb]   |
| `\sphericalangle`    | $\sphericalangle$    |                | [amssymb][amssymb]   |
| `\Bbbk`              | $\Bbbk$              |                | [amssymb][amssymb]   |
| `\circledS`          | $\circledS$          |                | [amssymb][amssymb]   |
| `\complement`        | $\complement$        |                | [amssymb][amssymb]   |
| `\Game`              | $\Game$              |                | [amssymb][amssymb]   |
| `\bigstar`           | $\bigstar$           |                | [amssymb][amssymb]   |
| `\backprime`         | $\backprime$         |                | [amssymb][amssymb]   |
| `\varnothing`        | $\varnothing$        |                | [amssymb][amssymb]   |
| `\mho`               | $\mho$               |                | [amssymb][amssymb]   |

- **Change** symbol **style**
  | Preamble Command                         | Rendering      | Original    | Dependency         |
  | ---------------------------------------- | -------------- | ----------- | ------------------ |
  | `\renewcommand{\triangle}{\vartriangle}` | $\vartriangle$ | $\triangle$ | [amssymb][amssymb] |

## Math Alphabets
> example TEXT: `ABCDEabcde1234`

| Command             | Rendering                     | Dependency                                 |
| ------------------- | ----------------------------- | ------------------------------------------ |
| `\mathrm{TEXT}`     | $\mathrm{ABCDEabcde1234}$     |
| `\mathit{TEXT}`     | $\mathit{ABCDEabcde1234}$     |
| `\mathnormal{TEXT}` | $\mathnormal{ABCDEabcde1234}$ |
| `\mathcal{TEXT}`    | $\mathcal{ABCDE}$             |
| `\mathscr{TEXT}`    | $\mathscr{ABCDE}$             | [mathrsfs][mathrsfs]                       |
| `\mathfrak{TEXT}`   | $\mathfrak{ABCDEabcde1234}$   | [amsfonts][amsfonts] or [amssymb][amssymb] |
| `\mathbb{TEXT}`     | $\mathbb{ABCDE}$              | [amsfonts][amsfonts] or [amssymb][amssymb] |


## Sources
- 2022-06-10: [The Not So Short Introduction to LaTeX2e](https://tobi.oetiker.ch/lshort/lshort.pdf)
- 2022-06-10: [LaTeX Math Symbols Cheat Sheet - Kapeli](https://kapeli.com/cheat_sheets/LaTeX_Math_Symbols.docset/Contents/Resources/Documents/index)
- 2022-06-10: [LaTeX Math for Undergrads](http://tug.ctan.org/info/undergradmath/undergradmath.pdf)
- 2022-06-10: [List of mathematical symbols by subject - Wikipedia](https://en.wikipedia.org/wiki/List_of_mathematical_symbols_by_subject)

[currency]: https://texdoc.org/serve/currency/0
[siunitx]: https://texdoc.org/serve/siunitx/0
[latexsym]: https://texdoc.org/serve/latexsym/0
[amssymb]: https://texdoc.org/serve/amssymb/0
[amsmath]: https://texdoc.org/serve/amsmath/0
[amsfonts]: https://texdoc.org/serve/amsfonts/0
[mathrsfs]: https://texdoc.org/serve/mathrsfs/0