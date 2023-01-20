---
example: Arrows
command: \mathbb{NR}
---

# Favorites

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

# Non-Mathematical Symbols

These symbols can also be used in text mode.

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
| `\unit{\degree}` <br> `\textdegree{}`   | °              | Degree Sign                          | [siunitx](https://texdoc.org/serve/siunitx/0) <br> _built in_ |
| `\ang{5}`                               | 5°             | Angle                                | [siunitx](https://texdoc.org/serve/siunitx/0)                 |
| `\unit{\celsius}` <br> `\textcelsius{}` | ℃              | Degree Celsius                       | [siunitx](https://texdoc.org/serve/siunitx/0) <br> _built in_ |
| `\qty{5}{\celsius}`                     | 5 ℃            |                                      | [siunitx](https://texdoc.org/serve/siunitx/0)                 |


# Money and currencies

`€`, `\$`, `pounds` and `\yen` are not recommended

| Command      | Rendering | Dependency                               |
| ------------ | --------- | ---------------------------------------- |
| `\cEUR{}`    | €         | [currency](https://texdoc.org/serve/currency/0) + [setup](Standardize%20currencies%20and%20monetary%20values.md) |
| `\cUSD{}`    | $         | [currency](https://texdoc.org/serve/currency/0) + [setup](Standardize%20currencies%20and%20monetary%20values.md) |
| `\cJPY{}`    | ¥         | [currency](https://texdoc.org/serve/currency/0) + [setup](Standardize%20currencies%20and%20monetary%20values.md) |
| `\cGBP{}`    | £         | [currency](https://texdoc.org/serve/currency/0) + [setup](Standardize%20currencies%20and%20monetary%20values.md) |
| `\dEUR{1.5}` | 1.50 €    | [currency](https://texdoc.org/serve/currency/0) + [setup](Standardize%20currencies%20and%20monetary%20values.md) |
| `\dUSD{1.5}` | $ 1.50    | [currency](https://texdoc.org/serve/currency/0) + [setup](Standardize%20currencies%20and%20monetary%20values.md) |
| `\dJPY{1.5}` | 2 ¥       | [currency](https://texdoc.org/serve/currency/0) + [setup](Standardize%20currencies%20and%20monetary%20values.md) |
| `\dGBP{1.5}` | £ 1.50    | [currency](https://texdoc.org/serve/currency/0) + [setup](Standardize%20currencies%20and%20monetary%20values.md) |

# Degree Symbols

| Command           | Rendering        | Dependency         |
| ----------------- | ---------------- | ------------------ |
| `^\circ`          | $^\circ$         |                    |
| `\unit{\degree}`  | $^\circ$         | [siunitx](https://texdoc.org/serve/siunitx/0) |
| `\unit{\celsius}` | $^\circ\text{C}$ | [siunitx](https://texdoc.org/serve/siunitx/0) |

# Math Mode Accents

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

# Greek Letters (lowercase)

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
| `\digamma`  | $\digamma$  |               | [amssymb](https://texdoc.org/serve/amssymb/0) |
| `\varkappa` | $\varkappa$ |               | [amssymb](https://texdoc.org/serve/amssymb/0) |

- Change letter style

    | Preamble Command                       | Rendering     | Original   | Dependency         |
    | -------------------------------------- | ------------- | ---------- | ------------------ |
    | `\renewcommand{\epsilon}{\varepsilon}` | $\varepsilon$ | $\epsilon$ |
    | `\renewcommand{\theta}{\vartheta}`     | $\vartheta$   | $\theta$   |
    | `\renewcommand{\kappa}{\varkappa}`     | $\varkappa$   | $\kappa$   | [amssymb](https://texdoc.org/serve/amssymb/0) |
    | `\renewcommand{\pi}{\varpi}`           | $\varpi$      | $\pi$      |
    | `\renewcommand{\rho}{\varrho}`         | $\varrho$     | $\rho$     |
    | `\renewcommand{\sigma}{\varsigma}`     | $\varsigma$   | $\sigma$   |
    | `\renewcommand{\phi}{\varphi}`         | $\varphi$     | $\phi$     |
    
# Greek Letters (uppercase)

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

# Hebrew Letters

| Command   | Rendering | Dependency         |
| --------- | --------- | ------------------ |
| `\beth`   | $\beth$   | [amssymb](https://texdoc.org/serve/amssymb/0) |
| `\gimel`  | $\gimel$  | [amssymb](https://texdoc.org/serve/amssymb/0) |
| `\daleth` | $\daleth$ | [amssymb](https://texdoc.org/serve/amssymb/0) |

# Number sets

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

# Binary Relations


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
| `\sqsubset`           | $\sqsubset$           | $\not\sqsubset$                             | [latexsym](https://texdoc.org/serve/latexsym/0) |
| `\sqsupset`           | $\sqsupset$           | $\not\sqsupset$                             | [latexsym](https://texdoc.org/serve/latexsym/0) |
| `\Join`               | $\Join$               | $\not\Join$                                 | [latexsym](https://texdoc.org/serve/latexsym/0) |
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
| `\lessdot`            | $\lessdot$            | $\not\lessdot$                              | [amssymb](https://texdoc.org/serve/amssymb/0)   |
| `\gtrdot`             | $\gtrdot$             | $\not\gtrdot$                               | [amssymb](https://texdoc.org/serve/amssymb/0)   |
| `\doteqdot`           | $\doteqdot$           | $\not\doteqdot$                             | [amssymb](https://texdoc.org/serve/amssymb/0)   |
| `\leqslant`           | $\leqslant$           | $\not\leqslant$                             | [amssymb](https://texdoc.org/serve/amssymb/0)   |
| `\geqslant`           | $\geqslant$           | $\not\geqslant$                             | [amssymb](https://texdoc.org/serve/amssymb/0)   |
| `\risingdotseq`       | $\risingdotseq$       | $\not\risingdotseq$                         | [amssymb](https://texdoc.org/serve/amssymb/0)   |
| `\eqslantless`        | $\eqslantless$        | $\not\eqslantless$                          | [amssymb](https://texdoc.org/serve/amssymb/0)   |
| `\eqslantgtr`         | $\eqslantgtr$         | $\not\eqslantgtr$                           | [amssymb](https://texdoc.org/serve/amssymb/0)   |
| `\fallingdotseq`      | $\fallingdotseq$      | $\not\fallingdotseq$                        | [amssymb](https://texdoc.org/serve/amssymb/0)   |
| `\leqq`               | $\leqq$               | $\not\leqq$                                 | [amssymb](https://texdoc.org/serve/amssymb/0)   |
| `\geqq`               | $\geqq$               | $\not\geqq$                                 | [amssymb](https://texdoc.org/serve/amssymb/0)   |
| `\eqcirc`             | $\eqcirc$             | $\not\eqcirc$                               | [amssymb](https://texdoc.org/serve/amssymb/0)   |
| `\lll`                | $\lll$                | $\not\lll$                                  | [amssymb](https://texdoc.org/serve/amssymb/0)   |
| `\llless`             | $\llless$             | $\not\llless$                               | [amssymb](https://texdoc.org/serve/amssymb/0)   |
| `\ggg`                | $\ggg$                | $\not\ggg$                                  | [amssymb](https://texdoc.org/serve/amssymb/0)   |
| `\circeq`             | $\circeq$             | $\not\circeq$                               | [amssymb](https://texdoc.org/serve/amssymb/0)   |
| `\lesssim`            | $\lesssim$            | $\not\lesssim$                              | [amssymb](https://texdoc.org/serve/amssymb/0)   |
| `\gtrsim`             | $\gtrsim$             | $\not\gtrsim$                               | [amssymb](https://texdoc.org/serve/amssymb/0)   |
| `\triangleq`          | $\triangleq$          | $\not\triangleq$                            | [amssymb](https://texdoc.org/serve/amssymb/0)   |
| `\lessapprox`         | $\lessapprox$         | $\not\lessapprox$                           | [amssymb](https://texdoc.org/serve/amssymb/0)   |
| `\gtrapprox`          | $\gtrapprox$          | $\not\gtrapprox$                            | [amssymb](https://texdoc.org/serve/amssymb/0)   |
| `\bumpeq`             | $\bumpeq$             | $\not\bumpeq$                               | [amssymb](https://texdoc.org/serve/amssymb/0)   |
| `\lessgtr`            | $\lessgtr$            | $\not\lessgtr$                              | [amssymb](https://texdoc.org/serve/amssymb/0)   |
| `\gtrless`            | $\gtrless$            | $\not\gtrless$                              | [amssymb](https://texdoc.org/serve/amssymb/0)   |
| `\Bumpeq`             | $\Bumpeq$             | $\not\Bumpeq$                               | [amssymb](https://texdoc.org/serve/amssymb/0)   |
| `\lesseqgtr`          | $\lesseqgtr$          | $\not\lesseqgtr$                            | [amssymb](https://texdoc.org/serve/amssymb/0)   |
| `\gtreqless`          | $\gtreqless$          | $\not\gtreqless$                            | [amssymb](https://texdoc.org/serve/amssymb/0)   |
| `\thicksim`           | $\thicksim$           | $\not\thicksim$                             | [amssymb](https://texdoc.org/serve/amssymb/0)   |
| `\lesseqqgtr`         | $\lesseqqgtr$         | $\not\lesseqqgtr$                           | [amssymb](https://texdoc.org/serve/amssymb/0)   |
| `\gtreqqless`         | $\gtreqqless$         | $\not\gtreqqless$                           | [amssymb](https://texdoc.org/serve/amssymb/0)   |
| `\thickapprox`        | $\thickapprox$        | $\not\thickapprox$                          | [amssymb](https://texdoc.org/serve/amssymb/0)   |
| `\preccurlyeq`        | $\preccurlyeq$        | $\not\preccurlyeq$                          | [amssymb](https://texdoc.org/serve/amssymb/0)   |
| `\succcurlyeq`        | $\succcurlyeq$        | $\not\succcurlyeq$                          | [amssymb](https://texdoc.org/serve/amssymb/0)   |
| `\approxeq`           | $\approxeq$           | $\not\approxeq$                             | [amssymb](https://texdoc.org/serve/amssymb/0)   |
| `\curlyeqprec`        | $\curlyeqprec$        | $\not\curlyeqprec$                          | [amssymb](https://texdoc.org/serve/amssymb/0)   |
| `\curlyeqsucc`        | $\curlyeqsucc$        | $\not\curlyeqsucc$                          | [amssymb](https://texdoc.org/serve/amssymb/0)   |
| `\backsim`            | $\backsim$            | $\not\backsim$                              | [amssymb](https://texdoc.org/serve/amssymb/0)   |
| `\precsim`            | $\precsim$            | $\not\precsim$                              | [amssymb](https://texdoc.org/serve/amssymb/0)   |
| `\succsim`            | $\succsim$            | $\not\succsim$                              | [amssymb](https://texdoc.org/serve/amssymb/0)   |
| `\backsimeq`          | $\backsimeq$          | $\not\backsimeq$                            | [amssymb](https://texdoc.org/serve/amssymb/0)   |
| `\precapprox`         | $\precapprox$         | $\not\precapprox$                           | [amssymb](https://texdoc.org/serve/amssymb/0)   |
| `\succapprox`         | $\succapprox$         | $\not\succapprox$                           | [amssymb](https://texdoc.org/serve/amssymb/0)   |
| `\vDash`              | $\vDash$              | $\not\vDash$                                | [amssymb](https://texdoc.org/serve/amssymb/0)   |
| `\subseteqq`          | $\subseteqq$          | $\not\subseteqq$                            | [amssymb](https://texdoc.org/serve/amssymb/0)   |
| `\supseteqq`          | $\supseteqq$          | $\not\supseteqq$                            | [amssymb](https://texdoc.org/serve/amssymb/0)   |
| `\Vdash`              | $\Vdash$              | $\not\Vdash$                                | [amssymb](https://texdoc.org/serve/amssymb/0)   |
| `\shortparallel`      | $\shortparallel$      | $\not\shortparallel$                        | [amssymb](https://texdoc.org/serve/amssymb/0)   |
| `\Supset`             | $\Supset$             | $\not\Supset$                               | [amssymb](https://texdoc.org/serve/amssymb/0)   |
| `\Vvdash`             | $\Vvdash$             | $\not\Vvdash$                               | [amssymb](https://texdoc.org/serve/amssymb/0)   |
| `\blacktriangleleft`  | $\blacktriangleleft$  | $\not\blacktriangleleft$                    | [amssymb](https://texdoc.org/serve/amssymb/0)   |
| `\sqsupset`           | $\sqsupset$           | $\not\sqsupset$                             | [amssymb](https://texdoc.org/serve/amssymb/0)   |
| `\backepsilon`        | $\backepsilon$        | $\not\backepsilon$                          | [amssymb](https://texdoc.org/serve/amssymb/0)   |
| `\vartriangleright`   | $\vartriangleright$   | $\not\vartriangleright$                     | [amssymb](https://texdoc.org/serve/amssymb/0)   |
| `\because`            | $\because$            | $\not\because$                              | [amssymb](https://texdoc.org/serve/amssymb/0)   |
| `\varpropto`          | $\varpropto$          | $\not\varpropto$                            | [amssymb](https://texdoc.org/serve/amssymb/0)   |
| `\blacktriangleright` | $\blacktriangleright$ | $\not\blacktriangleright$                   | [amssymb](https://texdoc.org/serve/amssymb/0)   |
| `\Subset`             | $\Subset$             | $\not\Subset$                               | [amssymb](https://texdoc.org/serve/amssymb/0)   |
| `\between`            | $\between$            | $\not\between$                              | [amssymb](https://texdoc.org/serve/amssymb/0)   |
| `\trianglerighteq`    | $\trianglerighteq$    | $\not\trianglerighteq$                      | [amssymb](https://texdoc.org/serve/amssymb/0)   |
| `\smallfrown`         | $\smallfrown$         | $\not\smallfrown$                           | [amssymb](https://texdoc.org/serve/amssymb/0)   |
| `\pitchfork`          | $\pitchfork$          | $\not\pitchfork$                            | [amssymb](https://texdoc.org/serve/amssymb/0)   |
| `\vartriangleleft`    | $\vartriangleleft$    | $\not\vartriangleleft$                      | [amssymb](https://texdoc.org/serve/amssymb/0)   |
| `\shortmid`           | $\shortmid$           | $\not\shortmid$                             | [amssymb](https://texdoc.org/serve/amssymb/0)   |
| `\smallsmile`         | $\smallsmile$         | $\not\smallsmile$                           | [amssymb](https://texdoc.org/serve/amssymb/0)   |
| `\trianglelefteq`     | $\trianglelefteq$     | $\not\trianglelefteq$                       | [amssymb](https://texdoc.org/serve/amssymb/0)   |
| `\therefore`          | $\therefore$          | $\not\therefore$                            | [amssymb](https://texdoc.org/serve/amssymb/0)   |
| `\sqsubset`           | $\sqsubset$           | $\not\sqsubset$                             | [amssymb](https://texdoc.org/serve/amssymb/0)   |

- **Use primitively negated symbol**  
  Not recommended, use [properly negated symbols](#negated-binary-relations-and-arrows) instead.  
  Prefix the command with `\not` like `\not\leq`.  

- **Change** symbol **style**
  
  | Preamble Command                     | Rendering    | Original  | Dependency         |
  | ------------------------------------ | ------------ | --------- | ------------------ |
  | `\renewcommand{\propto}{\varpropto}` | $\varpropto$ | $\propto$ | [amssymb](https://texdoc.org/serve/amssymb/0) |

# Negated Binary Relations and Arrows

| Command             | Rendering           | Variants         | Dependency         |
| ------------------- | ------------------- | ---------------- | ------------------ |
| `\neq` <br> `\ne`   | $\neq$ <br> $\ne$   |                  |
| `\notin`            | $\notin$            |                  |
| `\nless`            | $\nless$            |                  | [amssymb](https://texdoc.org/serve/amssymb/0) |
| `\ngtr`             | $\ngtr$             |                  | [amssymb](https://texdoc.org/serve/amssymb/0) |
| `\lneq`             | $\lneq$             |                  | [amssymb](https://texdoc.org/serve/amssymb/0) |
| `\gneq`             | $\gneq$             |                  | [amssymb](https://texdoc.org/serve/amssymb/0) |
| `\nleq`             | $\nleq$             |                  | [amssymb](https://texdoc.org/serve/amssymb/0) |
| `\ngeq`             | $\ngeq$             |                  | [amssymb](https://texdoc.org/serve/amssymb/0) |
| `\nleqslant`        | $\nleqslant$        |                  | [amssymb](https://texdoc.org/serve/amssymb/0) |
| `\ngeqslant`        | $\ngeqslant$        |                  | [amssymb](https://texdoc.org/serve/amssymb/0) |
| `\lneqq`            | $\lneqq$            |                  | [amssymb](https://texdoc.org/serve/amssymb/0) |
| `\gneqq`            | $\gneqq$            |                  | [amssymb](https://texdoc.org/serve/amssymb/0) |
| `\lvertneqq`        | $\lvertneqq$        |                  | [amssymb](https://texdoc.org/serve/amssymb/0) |
| `\gvertneqq`        | $\gvertneqq$        |                  | [amssymb](https://texdoc.org/serve/amssymb/0) |
| `\nleqq`            | $\nleqq$            |                  | [amssymb](https://texdoc.org/serve/amssymb/0) |
| `\ngeqq`            | $\ngeqq$            |                  | [amssymb](https://texdoc.org/serve/amssymb/0) |
| `\lnsim`            | $\lnsim$            |                  | [amssymb](https://texdoc.org/serve/amssymb/0) |
| `\gnsim`            | $\gnsim$            |                  | [amssymb](https://texdoc.org/serve/amssymb/0) |
| `\lnapprox`         | $\lnapprox$         |                  | [amssymb](https://texdoc.org/serve/amssymb/0) |
| `\gnapprox`         | $\gnapprox$         |                  | [amssymb](https://texdoc.org/serve/amssymb/0) |
| `\nprec`            | $\nprec$            |                  | [amssymb](https://texdoc.org/serve/amssymb/0) |
| `\nsucc`            | $\nsucc$            |                  | [amssymb](https://texdoc.org/serve/amssymb/0) |
| `\npreceq`          | $\npreceq$          |                  | [amssymb](https://texdoc.org/serve/amssymb/0) |
| `\nsucceq`          | $\nsucceq$          |                  | [amssymb](https://texdoc.org/serve/amssymb/0) |
| `\precneqq`         | $\precneqq$         |                  | [amssymb](https://texdoc.org/serve/amssymb/0) |
| `\succneqq`         | $\succneqq$         |                  | [amssymb](https://texdoc.org/serve/amssymb/0) |
| `\precnsim`         | $\precnsim$         |                  | [amssymb](https://texdoc.org/serve/amssymb/0) |
| `\succnsim`         | $\succnsim$         |                  | [amssymb](https://texdoc.org/serve/amssymb/0) |
| `\precnapprox`      | $\precnapprox$      |                  | [amssymb](https://texdoc.org/serve/amssymb/0) |
| `\succnapprox`      | $\succnapprox$      |                  | [amssymb](https://texdoc.org/serve/amssymb/0) |
| `\subsetneq`        | $\subsetneq$        | $\varsubsetneq$  | [amssymb](https://texdoc.org/serve/amssymb/0) |
| `\supsetneq`        | $\supsetneq$        | $\varsupsetneq$  | [amssymb](https://texdoc.org/serve/amssymb/0) |
| `\nsubseteq`        | $\nsubseteq$        |                  | [amssymb](https://texdoc.org/serve/amssymb/0) |
| `\nsupseteq`        | $\nsupseteq$        |                  | [amssymb](https://texdoc.org/serve/amssymb/0) |
| `\subsetneqq`       | $\subsetneqq$       | $\varsubsetneqq$ | [amssymb](https://texdoc.org/serve/amssymb/0) |
| `\supsetneqq`       | $\supsetneqq$       | $\varsupsetneqq$ | [amssymb](https://texdoc.org/serve/amssymb/0) |
| `\nsubseteqq`       | $\nsubseteqq$       |                  | [amssymb](https://texdoc.org/serve/amssymb/0) |
| `\nsupseteqq`       | $\nsupseteqq$       |                  | [amssymb](https://texdoc.org/serve/amssymb/0) |
| `\nmid`             | $\nmid$             |                  | [amssymb](https://texdoc.org/serve/amssymb/0) |
| `\nparallel`        | $\nparallel$        |                  | [amssymb](https://texdoc.org/serve/amssymb/0) |
| `\nshortmid`        | $\nshortmid$        |                  | [amssymb](https://texdoc.org/serve/amssymb/0) |
| `\nshortparallel`   | $\nshortparallel$   |                  | [amssymb](https://texdoc.org/serve/amssymb/0) |
| `\nsim`             | $\nsim$             |                  | [amssymb](https://texdoc.org/serve/amssymb/0) |
| `\ncong`            | $\ncong$            |                  | [amssymb](https://texdoc.org/serve/amssymb/0) |
| `\nvdash`           | $\nvdash$           |                  | [amssymb](https://texdoc.org/serve/amssymb/0) |
| `\nvDash`           | $\nvDash$           |                  | [amssymb](https://texdoc.org/serve/amssymb/0) |
| `\nVdash`           | $\nVdash$           |                  | [amssymb](https://texdoc.org/serve/amssymb/0) |
| `\nVDash`           | $\nVDash$           |                  | [amssymb](https://texdoc.org/serve/amssymb/0) |
| `\ntriangleleft`    | $\ntriangleleft$    |                  | [amssymb](https://texdoc.org/serve/amssymb/0) |
| `\ntriangleright`   | $\ntriangleright$   |                  | [amssymb](https://texdoc.org/serve/amssymb/0) |
| `\ntrianglelefteq`  | $\ntrianglelefteq$  |                  | [amssymb](https://texdoc.org/serve/amssymb/0) |
| `\ntrianglerighteq` | $\ntrianglerighteq$ |                  | [amssymb](https://texdoc.org/serve/amssymb/0) |
| `\nleftarrow`       | $\nleftarrow$       |                  | [amssymb](https://texdoc.org/serve/amssymb/0) |
| `\nrightarrow`      | $\nrightarrow$      |                  | [amssymb](https://texdoc.org/serve/amssymb/0) |
| `\nleftrightarrow`  | $\nleftrightarrow$  |                  | [amssymb](https://texdoc.org/serve/amssymb/0) |
| `\nLeftarrow`       | $\nLeftarrow$       |                  | [amssymb](https://texdoc.org/serve/amssymb/0) |
| `\nRightarrow`      | $\nRightarrow$      |                  | [amssymb](https://texdoc.org/serve/amssymb/0) |
| `\nLeftrightarrow`  | $\nLeftrightarrow$  |                  | [amssymb](https://texdoc.org/serve/amssymb/0) |

- **Change** symbol **style**
  
  | Preamble Command                             | Rendering        | Original      |
  | -------------------------------------------- | ---------------- | ------------- |
  | `\renewcommand{\subsetneq}{\varsubsetneq}`   | $\varsubsetneq$  | $\subsetneq$  |
  | `\renewcommand{\supsetneq}{\varsupsetneq}`   | $\varsupsetneq$  | $\supsetneq$  |
  | `\renewcommand{\subsetneqq}{\varsubsetneqq}` | $\varsubsetneqq$ | $\subsetneqq$ |
  | `\renewcommand{\supsetneqq}{\varsupsetneqq}` | $\varsupsetneqq$ | $\supsetneqq$ |

# Binary Operators

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
| `\lhd`                | $\lhd$                |                     | [latexsym](https://texdoc.org/serve/latexsym/0) |
| `\rhd`                | $\rhd$                |                     | [latexsym](https://texdoc.org/serve/latexsym/0) |
| `\ddagger`            | $\ddagger$            |                     |
| `\unlhd`              | $\unlhd$              |                     | [latexsym](https://texdoc.org/serve/latexsym/0) |
| `\unrhd`              | $\unrhd$              |                     | [latexsym](https://texdoc.org/serve/latexsym/0) |
| `\wr`                 | $\wr$                 |
| `\dotplus`            | $\dotplus$            |                     | [amssymb](https://texdoc.org/serve/amssymb/0)   |
| `\centerdot`          | $\centerdot$          |                     | [amssymb](https://texdoc.org/serve/amssymb/0)   |
| `\ltimes`             | $\ltimes$             |                     | [amssymb](https://texdoc.org/serve/amssymb/0)   |
| `\rtimes`             | $\rtimes$             |                     | [amssymb](https://texdoc.org/serve/amssymb/0)   |
| `\divideontimes`      | $\divideontimes$      |                     | [amssymb](https://texdoc.org/serve/amssymb/0)   |
| `\doublecup`          | $\doublecup$          |                     | [amssymb](https://texdoc.org/serve/amssymb/0)   |
| `\doublecap`          | $\doublecap$          |                     | [amssymb](https://texdoc.org/serve/amssymb/0)   |
| `\smallsetminus`      | $\smallsetminus$      |                     | [amssymb](https://texdoc.org/serve/amssymb/0)   |
| `\veebar`             | $\veebar$             |                     | [amssymb](https://texdoc.org/serve/amssymb/0)   |
| `\barwedge`           | $\barwedge$           |                     | [amssymb](https://texdoc.org/serve/amssymb/0)   |
| `\doublebarwedge`     | $\doublebarwedge$     |                     | [amssymb](https://texdoc.org/serve/amssymb/0)   |
| `\boxplus`            | $\boxplus$            |                     | [amssymb](https://texdoc.org/serve/amssymb/0)   |
| `\boxminus`           | $\boxminus$           |                     | [amssymb](https://texdoc.org/serve/amssymb/0)   |
| `\circleddash`        | $\circleddash$        |                     | [amssymb](https://texdoc.org/serve/amssymb/0)   |
| `\boxtimes`           | $\boxtimes$           |                     | [amssymb](https://texdoc.org/serve/amssymb/0)   |
| `\boxdot`             | $\boxdot$             |                     | [amssymb](https://texdoc.org/serve/amssymb/0)   |
| `\circledcirc`        | $\circledcirc$        |                     | [amssymb](https://texdoc.org/serve/amssymb/0)   |
| `\intercal`           | $\intercal$           |                     | [amssymb](https://texdoc.org/serve/amssymb/0)   |
| `\circledast`         | $\circledast$         |                     | [amssymb](https://texdoc.org/serve/amssymb/0)   |
| `\rightthreetimes`    | $\rightthreetimes$    |                     | [amssymb](https://texdoc.org/serve/amssymb/0)   |
| `\curlyvee`           | $\curlyvee$           |                     | [amssymb](https://texdoc.org/serve/amssymb/0)   |
| `\curlywedge`         | $\curlywedge$         |                     | [amssymb](https://texdoc.org/serve/amssymb/0)   |
| `\leftthreetimes`     | $\leftthreetimes$     |                     | [amssymb](https://texdoc.org/serve/amssymb/0)   |

- **Change** symbol **style**
  
  | Preamble Command                                   | Rendering           | Original         | Dependency         |
  | -------------------------------------------------- | ------------------- | ---------------- | ------------------ |
  | `\renewcommand{\triangleleft}{\vartriangleleft}`   | $\vartriangleleft$  | $\triangleleft$  | [amssymb](https://texdoc.org/serve/amssymb/0) |
  | `\renewcommand{\triangleright}{\vartriangleright}` | $\vartriangleright$ | $\triangleright$ | [amssymb](https://texdoc.org/serve/amssymb/0) |

# Big Operators

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

# Arrows

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
| `\leadsto`                | $\leadsto$                | [latexsym](https://texdoc.org/serve/latexsym/0) |
| `\dashleftarrow`          | $\dashleftarrow$          | [amssymb](https://texdoc.org/serve/amssymb/0)   |
| `\dashrightarrow`         | $\dashrightarrow$         | [amssymb](https://texdoc.org/serve/amssymb/0)   |
| `\leftleftarrows`         | $\leftleftarrows$         | [amssymb](https://texdoc.org/serve/amssymb/0)   |
| `\rightrightarrows`       | $\rightrightarrows$       | [amssymb](https://texdoc.org/serve/amssymb/0)   |
| `\leftrightarrows`        | $\leftrightarrows$        | [amssymb](https://texdoc.org/serve/amssymb/0)   |
| `\rightleftarrows`        | $\rightleftarrows$        | [amssymb](https://texdoc.org/serve/amssymb/0)   |
| `\Lleftarrow`             | $\Lleftarrow$             | [amssymb](https://texdoc.org/serve/amssymb/0)   |
| `\Rrightarrow`            | $\Rrightarrow$            | [amssymb](https://texdoc.org/serve/amssymb/0)   |
| `\twoheadleftarrow`       | $\twoheadleftarrow$       | [amssymb](https://texdoc.org/serve/amssymb/0)   |
| `\twoheadrightarrow`      | $\twoheadrightarrow$      | [amssymb](https://texdoc.org/serve/amssymb/0)   |
| `\leftarrowtail`          | $\leftarrowtail$          | [amssymb](https://texdoc.org/serve/amssymb/0)   |
| `\rightarrowtail`         | $\rightarrowtail$         | [amssymb](https://texdoc.org/serve/amssymb/0)   |
| `\leftrightharpoons`      | $\leftrightharpoons$      | [amssymb](https://texdoc.org/serve/amssymb/0)   |
| `\rightleftharpoons`      | $\rightleftharpoons$      | [amssymb](https://texdoc.org/serve/amssymb/0)   |
| `\Lsh`                    | $\Lsh$                    | [amssymb](https://texdoc.org/serve/amssymb/0)   |
| `\Rsh`                    | $\Rsh$                    | [amssymb](https://texdoc.org/serve/amssymb/0)   |
| `\looparrowleft`          | $\looparrowleft$          | [amssymb](https://texdoc.org/serve/amssymb/0)   |
| `\looparrowright`         | $\looparrowright$         | [amssymb](https://texdoc.org/serve/amssymb/0)   |
| `\curvearrowleft`         | $\curvearrowleft$         | [amssymb](https://texdoc.org/serve/amssymb/0)   |
| `\curvearrowright`        | $\curvearrowright$        | [amssymb](https://texdoc.org/serve/amssymb/0)   |
| `\circlearrowleft`        | $\circlearrowleft$        | [amssymb](https://texdoc.org/serve/amssymb/0)   |
| `\circlearrowright`       | $\circlearrowright$       | [amssymb](https://texdoc.org/serve/amssymb/0)   |
| `\multimap`               | $\multimap$               | [amssymb](https://texdoc.org/serve/amssymb/0)   |
| `\upuparrows`             | $\upuparrows$             | [amssymb](https://texdoc.org/serve/amssymb/0)   |
| `\downdownarrows`         | $\downdownarrows$         | [amssymb](https://texdoc.org/serve/amssymb/0)   |
| `\upharpoonleft`          | $\upharpoonleft$          | [amssymb](https://texdoc.org/serve/amssymb/0)   |
| `\upharpoonright`         | $\upharpoonright$         | [amssymb](https://texdoc.org/serve/amssymb/0)   |
| `\downharpoonright`       | $\downharpoonright$       | [amssymb](https://texdoc.org/serve/amssymb/0)   |
| `\rightsquigarrow`        | $\rightsquigarrow$        | [amssymb](https://texdoc.org/serve/amssymb/0)   |
| `\leftrightsquigarrow`    | $\leftrightsquigarrow$    | [amssymb](https://texdoc.org/serve/amssymb/0)   |

# Arrows as Accents

| Command                    | Rendering                  |
| -------------------------- | -------------------------- |
| `\overrightarrow{AB}`      | $\overrightarrow{AB}$      |
| `\underrightarrow{AB}`     | $\underrightarrow{AB}$     |
| `\overleftarrow{AB}`       | $\overleftarrow{AB}$       |
| `\underleftarrow{AB}`      | $\underleftarrow{AB}$      |
| `\overleftrightarrow{AB}`  | $\overleftrightarrow{AB}$  |
| `\underleftrightarrow{AB}` | $\underleftrightarrow{AB}$ |

# Delimiters

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
| `\ulcorner`         | $\ulcorner$           | [amssymb](https://texdoc.org/serve/amssymb/0)                     |
| `\urcorner`         | $\urcorner$           | [amssymb](https://texdoc.org/serve/amssymb/0)                     |
| `\llcorner`         | $\llcorner$           | [amssymb](https://texdoc.org/serve/amssymb/0)                     |
| `\lrcorner`         | $\lrcorner$           | [amssymb](https://texdoc.org/serve/amssymb/0)                     |
| `\lvert`            | $\lvert$              | [amssymb](https://texdoc.org/serve/amssymb/0), [amsmath](https://texdoc.org/serve/amssymb](https://texdoc.org/serve/amssymb/0), [amsmath/0) |
| `\rvert`            | $\rvert$              | [amssymb](https://texdoc.org/serve/amssymb/0), [amsmath](https://texdoc.org/serve/amssymb](https://texdoc.org/serve/amssymb/0), [amsmath/0) |
| `\lVert`            | $\lVert$              | [amssymb](https://texdoc.org/serve/amssymb/0), [amsmath](https://texdoc.org/serve/amssymb](https://texdoc.org/serve/amssymb/0), [amsmath/0) |
| `\rVert`            | $\rVert$              | [amssymb](https://texdoc.org/serve/amssymb/0), [amsmath](https://texdoc.org/serve/amssymb](https://texdoc.org/serve/amssymb/0), [amsmath/0) |

# Large Delimiters

| Command       | Rendering     |
| ------------- | ------------- |
| `\lgroup`     | $\lgroup$     |
| `\rgroup`     | $\rgroup$     |
| `\lmoustache` | $\lmoustache$ |
| `\arrowvert`  | $\arrowvert$  |
| `\Arrowvert`  | $\Arrowvert$  |
| `\bracevert`  | $\bracevert$  |
| `\rmoustache` | $\rmoustache$ |

# Miscellaneous Symbols

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
| `\mho`               | $\mho$               |                | [latexsym](https://texdoc.org/serve/latexsym/0) |
| `\partial`           | $\partial$           |
| `'`                  | $'$                  |
| `\prime`             | $\prime$             |
| `\emptyset`          | $\emptyset$          |
| `\infty`             | $\infty$             |
| `\nabla`             | $\nabla$             |
| `\triangle`          | $\triangle$          | $\vartriangle$ | [amssymb](https://texdoc.org/serve/amssymb/0)   |
| `\Box`               | $\Box$               |                | [latexsym](https://texdoc.org/serve/latexsym/0) |
| `\Diamond`           | $\Diamond$           |                | [latexsym](https://texdoc.org/serve/latexsym/0) |
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
| `\square`            | $\square$            |                | [amssymb](https://texdoc.org/serve/amssymb/0)   |
| `\vartriangle`       | $\vartriangle$       |                | [amssymb](https://texdoc.org/serve/amssymb/0)   |
| `\triangledown`      | $\triangledown$      |                | [amssymb](https://texdoc.org/serve/amssymb/0)   |
| `\lozenge`           | $\lozenge$           |                | [amssymb](https://texdoc.org/serve/amssymb/0)   |
| `\diagup`            | $\diagup$            |                | [amssymb](https://texdoc.org/serve/amssymb/0)   |
| `\hslash`            | $\hslash$            |                | [amssymb](https://texdoc.org/serve/amssymb/0)   |
| `\blacksquare`       | $\blacksquare$       |                | [amssymb](https://texdoc.org/serve/amssymb/0)   |
| `\blacktriangle`     | $\blacktriangle$     |                | [amssymb](https://texdoc.org/serve/amssymb/0)   |
| `\blacktriangledown` | $\blacktriangledown$ |                | [amssymb](https://texdoc.org/serve/amssymb/0)   |
| `\blacklozenge`      | $\blacklozenge$      |                | [amssymb](https://texdoc.org/serve/amssymb/0)   |
| `\measuredangle`     | $\measuredangle$     |                | [amssymb](https://texdoc.org/serve/amssymb/0)   |
| `\diagdown`          | $\diagdown$          |                | [amssymb](https://texdoc.org/serve/amssymb/0)   |
| `\nexists`           | $\nexists$           |                | [amssymb](https://texdoc.org/serve/amssymb/0)   |
| `\Finv`              | $\Finv$              |                | [amssymb](https://texdoc.org/serve/amssymb/0)   |
| `\eth`               | $\eth$               |                | [amssymb](https://texdoc.org/serve/amssymb/0)   |
| `\sphericalangle`    | $\sphericalangle$    |                | [amssymb](https://texdoc.org/serve/amssymb/0)   |
| `\Bbbk`              | $\Bbbk$              |                | [amssymb](https://texdoc.org/serve/amssymb/0)   |
| `\circledS`          | $\circledS$          |                | [amssymb](https://texdoc.org/serve/amssymb/0)   |
| `\complement`        | $\complement$        |                | [amssymb](https://texdoc.org/serve/amssymb/0)   |
| `\Game`              | $\Game$              |                | [amssymb](https://texdoc.org/serve/amssymb/0)   |
| `\bigstar`           | $\bigstar$           |                | [amssymb](https://texdoc.org/serve/amssymb/0)   |
| `\backprime`         | $\backprime$         |                | [amssymb](https://texdoc.org/serve/amssymb/0)   |
| `\varnothing`        | $\varnothing$        |                | [amssymb](https://texdoc.org/serve/amssymb/0)   |
| `\mho`               | $\mho$               |                | [amssymb](https://texdoc.org/serve/amssymb/0)   |

- **Change** symbol **style**
  
  | Preamble Command                         | Rendering      | Original    | Dependency         |
  | ---------------------------------------- | -------------- | ----------- | ------------------ |
  | `\renewcommand{\triangle}{\vartriangle}` | $\vartriangle$ | $\triangle$ | [amssymb](https://texdoc.org/serve/amssymb/0) |

# Math Alphabets

example TEXT: `ABCDEabcde1234`

| Command             | Rendering                     | Dependency                                 |
| ------------------- | ----------------------------- | ------------------------------------------ |
| `\mathrm{TEXT}`     | $\mathrm{ABCDEabcde1234}$     |
| `\mathit{TEXT}`     | $\mathit{ABCDEabcde1234}$     |
| `\mathnormal{TEXT}` | $\mathnormal{ABCDEabcde1234}$ |
| `\mathcal{TEXT}`    | $\mathcal{ABCDE}$             |
| `\mathscr{TEXT}`    | $\mathscr{ABCDE}$             | [mathrsfs](https://texdoc.org/serve/mathrsfs/0)                       |
| `\mathfrak{TEXT}`   | $\mathfrak{ABCDEabcde1234}$   | [amsfonts](https://texdoc.org/serve/amsfonts/0) or [amssymb](https://texdoc.org/serve/amsfonts](https://texdoc.org/serve/amsfonts/0) or [amssymb/0) |
| `\mathbb{TEXT}`     | $\mathbb{ABCDE}$              | [amsfonts](https://texdoc.org/serve/amsfonts/0) or [amssymb](https://texdoc.org/serve/amsfonts](https://texdoc.org/serve/amsfonts/0) or [amssymb/0) |



---
Sources:
- 2022-06-10: [The Not So Short Introduction to LaTeX2e](https://tobi.oetiker.ch/lshort/lshort.pdf)
- 2022-06-10: [LaTeX Math Symbols Cheat Sheet - Kapeli](https://kapeli.com/cheat_sheets/LaTeX_Math_Symbols.docset/Contents/Resources/Documents/index)
- 2022-06-10: [LaTeX Math for Undergrads](http://tug.ctan.org/info/undergradmath/undergradmath.pdf)
- 2022-06-10: [List of mathematical symbols by subject - Wikipedia](https://en.wikipedia.org/wiki/List_of_mathematical_symbols_by_subject)

Related:
[Vary the style of mathematical symbols](../Vary%20the%20style%20of%20mathematical%20symbols.md)

Tags:
[Standardize values](../Standardize%20values.md)