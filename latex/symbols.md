# Symbols
[⌂](../README.md) › [LaTeX](../README.md#latex) ›
> Commands for Mathematical Expressions, Symbols, Operators and Relations
- [Favorites](#favorites)
- [Non-Mathematical Symbols](#non-mathematical-symbols)
- [Degree Symbols](#degree-symbols)
- [Math Mode Accents](#math-mode-accents)
- [Greek Letters (lowercase)](#greek-letters-lowercase)
- [Greek Letters (uppercase)](#greek-letters-uppercase)
- [Number sets](#number-sets)
- [Binary Relations](#binary-relations)
- [AMS Negated Binary Relations and Arrows](#ams-negated-binary-relations-and-arrows)
- [Primitively Negated Binary Relations](#primitively-negated-binary-relations)
- [Binary Operators](#binary-operators)
- [Big Operators](#big-operators)
- [Arrows](#arrows)
- [AMS Arrows](#ams-arrows)
- [Arrows as Accents](#arrows-as-accents)
- [Delimiters](#delimiters)
- [Large Delimiters](#large-delimiters)
- [Miscellaneous Symbols](#miscellaneous-symbols)
- [AMS Delimiters](#ams-delimiters)
- [AMS Greek and Hebrew](#ams-greek-and-hebrew)
- [Math Alphabets](#math-alphabets)
- [AMS Binary Operators](#ams-binary-operators)
- [AMS Binary Relations](#ams-binary-relations)
- [AMS Miscellaneous](#ams-miscellaneous)
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

| Command     | Rendering      | Name or _Function_                   | Usage Example                    |
| ----------- | -------------- | ------------------------------------ | -------------------------------- |
| `-`         | -              | hyphen                               | daughter-in-law, X-rated         |
| `--`        | –              | en-dash                              | pages 13–67                      |
| `---`       | —              | em-dash                              | yes—or no?                       |
| `$-1$`      | −              | minus-sign                           | 0, 1 and −1                      |
| `/`         | /              | _prevents hyphenation_               | 5 MB/s                           |
| `\slash{}`  | /              | _supports hyphenation_               | read/write                       |
| `\ldots{}`  | …              | ellipsis                             | a, b, c, …                       |
| `Mr.~Smith` | Mr.&#160;Smith | _suppresses bigger sentence spacing_ | Did ⠀Mr.&#160;Smith ⠀win ⠀today? |
| `\dag{}`    | †              | Dagger                               |
| `\ddag{}`   | ‡              | Double Dagger                        |
| `\S{}`      | §              | Section Sign                         |
| `\P{}`      | ¶              | Pilcrow Sign                         |
| `\%{}`      | %              | Percent Sign                         |
`\textdegree{}`
| `\textsuperscript{\copyright}` <br> `\textsuperscript{\textcopyright}` | © <br> ©       | Copyright Sign                       |
| `\textsuperscript{\textregistered}`                                    | ®              | Registered Trade Mark Sign           |
| `\texttrademark{}`                                                     | ™              | Trade Mark Sign                      |
| `\textdegree{}`                                                        | °              |


## Currencies
> `€`, `\$`, `pounds` and `\yen` are not recommended

| Command                         | Rendering | Dependency |
| ------------------------------- | --------- | ---------- |
| `\texteuro{}`                   | €         |
| `\textdollar{}`                 | $         |
| `\textsterling{}`               | £         |
| `\textyen{}`                    | ¥         |
| `\SI{5}{\text\texteuro}`        | 15 €      | siunitx    |
| `\SI{15}[\text\textdollar]{}`   | $15       | siunitx    |
| `\SI{15}[\text\textsterling]{}` | £15       | siunitx    |
| `\SI{15}[\text\textyen]{}`      | £15       | siunitx    |


- Simplified Currencies
    ```latex
    \DeclareSIUnit{\euro}{\text{\texteuro}}
    \DeclareSIUnit{\dollar}{\text{\textdollar}}
    \DeclareSIUnit{\sterling}{\text{\textsterling}}
    \DeclareSIUnit{\yen}{\text{\textyen}}
    ```
    | Command                | Rendering | Dependency |
    | ---------------------- | --------- | ---------- |
    | `\SI{5}{\euro}`        | 15 €      | siunitx    |
    | `\SI{15}[\dollar]{}`   | $15       | siunitx    |
    | `\SI{15}[\sterling]{}` | £15       | siunitx    |
    | `\SI{15}[\yen]{}`      | ¥15       | siunitx    |
- Change EURO symbol
    ```latex
    \usepackage{eurosym} % provide different euro symbol style
    ```
    ```latex
    \renewcommand{\texteuro}{\text{\officialeuro}}
    ```

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
| Command       | Rendering     |
| ------------- | ------------- |
| `\alpha`      | $\alpha$      |
| `\beta`       | $\beta$       |
| `\gamma`      | $\gamma$      |
| `\delta`      | $\delta$      |
| `\epsilon`    | $\epsilon$    |
| `\varepsilon` | $\varepsilon$ |
| `\zeta`       | $\zeta$       |
| `\eta`        | $\eta$        |
| `\theta`      | $\theta$      |
| `\vartheta`   | $\vartheta$   |
| `\iota`       | $\iota$       |
| `\kappa`      | $\kappa$      |
| `\lambda`     | $\lambda$     |
| `\mu`         | $\mu$         |
| `\nu`         | $\nu$         |
| `\xi`         | $\xi$         |
| `o`           | $o$           |
| `\pi`         | $\pi$         |
| `\varpi`      | $\varpi$      |
| `\rho`        | $\rho$        |
| `\varrho`     | $\varrho$     |
| `\sigma`      | $\sigma$      |
| `\varsigma`   | $\varsigma$   |
| `\tau`        | $\tau$        |
| `\upsilon`    | $\upsilon$    |
| `\phi`        | $\phi$        |
| `\varphi`     | $\varphi$     |
| `\chi`        | $\chi$        |
| `\psi`        | $\psi$        |
| `\omega`      | $\omega$      |

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

| Command            | Rendering          | Dependency |
| ------------------ | ------------------ | ---------- |
| `<`                | $<$                |
| `>`                | $>$                |
| `=`                | $=$                |
| `\leq` <br> `\le`  | $\leq$ <br> $\le$  |
| `\geq` <br> `\ge`  | $\geq$ <br> $\ge$  |
| `\equiv`           | $\equiv$           |
| `\ll`              | $\ll$              |
| `\gg`              | $\gg$              |
| `\doteq`           | $\doteq$           |
| `\prec`            | $\prec$            |
| `\succ`            | $\succ$            |
| `\sim`             | $\sim$             |
| `\preceq`          | $\preceq$          |
| `\succeq`          | $\succeq$          |
| `\simeq`           | $\simeq$           |
| `\subset`          | $\subset$          |
| `\supset`          | $\supset$          |
| `\approx`          | $\approx$          |
| `\subseteq`        | $\subseteq$        |
| `\supseteq`        | $\supseteq$        |
| `\cong`            | $\cong$            |
| `\sqsubset`        | $\sqsubset$        | latexsym   |
| `\sqsupset`        | $\sqsupset$        | latexsym   |
| `\Join`            | $\Join$            | latexsym   |
| `\sqsubseteq`      | $\sqsubseteq$      |
| `\sqsupseteq`      | $\sqsupseteq$      |
| `\bowtie`          | $\bowtie$          |
| `\in`              | $\in$              |
| `\ni` <br> `\owns` | $\ni$ <br> $\owns$ |
| `\propto`          | $\propto$          |
| `\vdash`           | $\vdash$           |
| `\dashv`           | $\dashv$           |
| `\models`          | $\models$          |
| `\mid`             | $\mid$             |
| `\parallel`        | $\parallel$        |
| `\perp`            | $\perp$            |
| `\smile`           | $\smile$           |
| `\frown`           | $\frown$           |
| `\asymp`           | $\asymp$           |
| `:`                | $:$                |
| `\notin`           | $\notin$           |
| `\neq` <br> `\ne`  | $\neq$ <br> $\ne$  |

## AMS Negated Binary Relations and Arrows
| Command             | Rendering           |
| ------------------- | ------------------- |
| `\nless`            | $\nless$            |
| `\ngtr`             | $\ngtr$             |
| `\lneq`             | $\lneq$             |
| `\gneq`             | $\gneq$             |
| `\nleq`             | $\nleq$             |
| `\ngeq`             | $\ngeq$             |
| `\nleqslant`        | $\nleqslant$        |
| `\ngeqslant`        | $\ngeqslant$        |
| `\lneqq`            | $\lneqq$            |
| `\gneqq`            | $\gneqq$            |
| `\lvertneqq`        | $\lvertneqq$        |
| `\gvertneqq`        | $\gvertneqq$        |
| `\nleqq`            | $\nleqq$            |
| `\ngeqq`            | $\ngeqq$            |
| `\lnsim`            | $\lnsim$            |
| `\gnsim`            | $\gnsim$            |
| `\lnapprox`         | $\lnapprox$         |
| `\gnapprox`         | $\gnapprox$         |
| `\nprec`            | $\nprec$            |
| `\nsucc`            | $\nsucc$            |
| `\npreceq`          | $\npreceq$          |
| `\nsucceq`          | $\nsucceq$          |
| `\precneqq`         | $\precneqq$         |
| `\succneqq`         | $\succneqq$         |
| `\precnsim`         | $\precnsim$         |
| `\succnsim`         | $\succnsim$         |
| `\precnapprox`      | $\precnapprox$      |
| `\succnapprox`      | $\succnapprox$      |
| `\subsetneq`        | $\subsetneq$        |
| `\supsetneq`        | $\supsetneq$        |
| `\varsubsetneq`     | $\varsubsetneq$     |
| `\varsupsetneq`     | $\varsupsetneq$     |
| `\nsubseteq`        | $\nsubseteq$        |
| `\nsupseteq`        | $\nsupseteq$        |
| `\subsetneqq`       | $\subsetneqq$       |
| `\supsetneqq`       | $\supsetneqq$       |
| `\varsubsetneqq`    | $\varsubsetneqq$    |
| `\varsupsetneqq`    | $\varsupsetneqq$    |
| `\nsubseteqq`       | $\nsubseteqq$       |
| `\nsupseteqq`       | $\nsupseteqq$       |
| `\nmid`             | $\nmid$             |
| `\nparallel`        | $\nparallel$        |
| `\nshortmid`        | $\nshortmid$        |
| `\nshortparallel`   | $\nshortparallel$   |
| `\nsim`             | $\nsim$             |
| `\ncong`            | $\ncong$            |
| `\nvdash`           | $\nvdash$           |
| `\nvDash`           | $\nvDash$           |
| `\nVdash`           | $\nVdash$           |
| `\nVDash`           | $\nVDash$           |
| `\ntriangleleft`    | $\ntriangleleft$    |
| `\ntriangleright`   | $\ntriangleright$   |
| `\ntrianglelefteq`  | $\ntrianglelefteq$  |
| `\ntrianglerighteq` | $\ntrianglerighteq$ |
| `\nleftarrow`       | $\nleftarrow$       |
| `\nrightarrow`      | $\nrightarrow$      |
| `\nleftrightarrow`  | $\nleftrightarrow$  |
| `\nLeftarrow`       | $\nLeftarrow$       |
| `\nRightarrow`      | $\nRightarrow$      |
| `\nLeftrightarrow`  | $\nLeftrightarrow$  |

## Primitively Negated Binary Relations
| Command                    | Rendering                  | Dependency |
| -------------------------- | -------------------------- | ---------- |
| `\not<`                    | $\not<$                    |
| `\not>`                    | $\not>$                    |
| `\not=`                    | $\not=$                    |
| `\not\leq` <br> `\not\le`  | $\not\leq$ <br> $\not\le$  |
| `\not\geq` <br> `\not\ge`  | $\not\geq$ <br> $\not\ge$  |
| `\not\equiv`               | $\not\equiv$               |
| `\not\ll`                  | $\not\ll$                  |
| `\not\gg`                  | $\not\gg$                  |
| `\not\doteq`               | $\not\doteq$               |
| `\not\prec`                | $\not\prec$                |
| `\not\succ`                | $\not\succ$                |
| `\not\sim`                 | $\not\sim$                 |
| `\not\preceq`              | $\not\preceq$              |
| `\not\succeq`              | $\not\succeq$              |
| `\not\simeq`               | $\not\simeq$               |
| `\not\subset`              | $\not\subset$              |
| `\not\supset`              | $\not\supset$              |
| `\not\approx`              | $\not\approx$              |
| `\not\subseteq`            | $\not\subseteq$            |
| `\not\supseteq`            | $\not\supseteq$            |
| `\not\cong`                | $\not\cong$                |
| `\not\sqsubset`            | $\not\sqsubset$            | latexsym   |
| `\not\sqsupset`            | $\not\sqsupset$            | latexsym   |
| `\not\Join`                | $\not\Join$                | latexsym   |
| `\not\sqsubseteq`          | $\not\sqsubseteq$          |
| `\not\sqsupseteq`          | $\not\sqsupseteq$          |
| `\not\bowtie`              | $\not\bowtie$              |
| `\not\in`                  | $\not\in$                  |
| `\not\ni` <br> `\not\owns` | $\not\ni$ <br> $\not\owns$ |
| `\not\propto`              | $\not\propto$              |
| `\not\vdash`               | $\not\vdash$               |
| `\not\dashv`               | $\not\dashv$               |
| `\not\models`              | $\not\models$              |
| `\not\mid`                 | $\not\mid$                 |
| `\not\parallel`            | $\not\parallel$            |
| `\not\perp`                | $\not\perp$                |
| `\not\smile`               | $\not\smile$               |
| `\not\frown`               | $\not\frown$               |
| `\not\asymp`               | $\not\asymp$               |

## Binary Operators
| Command               | Rendering             | Dependency |
| --------------------- | --------------------- | ---------- |
| `+`                   | $+$                   |
| `-`                   | $-$                   |
| `\pm`                 | $\pm$                 |
| `\mp`                 | $\mp$                 |
| `\triangleleft`       | $\triangleleft$       |
| `\cdot`               | $\cdot$               |
| `\div`                | $\div$                |
| `\triangleright`      | $\triangleright$      |
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
| `\lhd`                | $\lhd$                | latexsym   |
| `\rhd`                | $\rhd$                | latexsym   |
| `\ddagger`            | $\ddagger$            |
| `\unlhd`              | $\unlhd$              | latexsym   |
| `\unrhd`              | $\unrhd$              | latexsym   |
| `\wr`                 | $\wr$                 |

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

## AMS Arrows
| Command                | Rendering              |
| ---------------------- | ---------------------- |
| `\dashleftarrow`       | $\dashleftarrow$       |
| `\dashrightarrow`      | $\dashrightarrow$      |
| `\leftleftarrows`      | $\leftleftarrows$      |
| `\rightrightarrows`    | $\rightrightarrows$    |
| `\leftrightarrows`     | $\leftrightarrows$     |
| `\rightleftarrows`     | $\rightleftarrows$     |
| `\Lleftarrow`          | $\Lleftarrow$          |
| `\Rrightarrow`         | $\Rrightarrow$         |
| `\twoheadleftarrow`    | $\twoheadleftarrow$    |
| `\twoheadrightarrow`   | $\twoheadrightarrow$   |
| `\leftarrowtail`       | $\leftarrowtail$       |
| `\rightarrowtail`      | $\rightarrowtail$      |
| `\leftrightharpoons`   | $\leftrightharpoons$   |
| `\rightleftharpoons`   | $\rightleftharpoons$   |
| `\Lsh`                 | $\Lsh$                 |
| `\Rsh`                 | $\Rsh$                 |
| `\looparrowleft`       | $\looparrowleft$       |
| `\looparrowright`      | $\looparrowright$      |
| `\curvearrowleft`      | $\curvearrowleft$      |
| `\curvearrowright`     | $\curvearrowright$     |
| `\circlearrowleft`     | $\circlearrowleft$     |
| `\circlearrowright`    | $\circlearrowright$    |
| `\multimap`            | $\multimap$            |
| `\upuparrows`          | $\upuparrows$          |
| `\downdownarrows`      | $\downdownarrows$      |
| `\upharpoonleft`       | $\upharpoonleft$       |
| `\upharpoonright`      | $\upharpoonright$      |
| `\downharpoonright`    | $\downharpoonright$    |
| `\rightsquigarrow`     | $\rightsquigarrow$     |
| `\leftrightsquigarrow` | $\leftrightsquigarrow$ |

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
| Command             | Rendering             |
| ------------------- | --------------------- |
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
| Command             | Rendering           | Dependency |
| ------------------- | ------------------- | ---------- |
| `\dots`             | $\dots$             |
| `\cdots`            | $\cdots$            |
| `\vdots`            | $\vdots$            |
| `\ddots`            | $\ddots$            |
| `\hbar`             | $\hbar$             |
| `\imath`            | $\imath$            |
| `\jmath`            | $\jmath$            |
| `\ell`              | $\ell$              |
| `\Re`               | $\Re$               |
| `\Im`               | $\Im$               |
| `\aleph`            | $\aleph$            |
| `\wp`               | $\wp$               |
| `\forall`           | $\forall$           |
| `\exists`           | $\exists$           |
| `\mho`              | $\mho$              | latexsym   |
| `\partial`          | $\partial$          |
| `'`                 | $'$                 |
| `\prime`            | $\prime$            |
| `\emptyset`         | $\emptyset$         |
| `\infty`            | $\infty$            |
| `\nabla`            | $\nabla$            |
| `\triangle`         | $\triangle$         |
| `\Box`              | $\Box$              | latexsym   |
| `\Diamond`          | $\Diamond$          | latexsym   |
| `\bot`              | $\bot$              |
| `\top`              | $\top$              |
| `\angle`            | $\angle$            |
| `\surd`             | $\surd$             |
| `\diamondsuit`      | $\diamondsuit$      |
| `\heartsuit`        | $\heartsuit$        |
| `\clubsuit`         | $\clubsuit$         |
| `\spadesuit`        | $\spadesuit$        |
| `\neg` <br> `\lnot` | $\neg$ <br> $\lnot$ |
| `\flat`             | $\flat$             |
| `\natural`          | $\natural$          |
| `\sharp`            | $\sharp$            |

## AMS Delimiters
| Command     | Rendering   |
| ----------- | ----------- |
| `\ulcorner` | $\ulcorner$ |
| `\urcorner` | $\urcorner$ |
| `\llcorner` | $\llcorner$ |
| `\lrcorner` | $\lrcorner$ |
| `\lvert`    | $\lvert$    |
| `\rvert`    | $\rvert$    |
| `\lVert`    | $\lVert$    |
| `\rVert`    | $\rVert$    |

## AMS Greek and Hebrew
| Command     | Rendering   |
| ----------- | ----------- |
| `\digamma`  | $\digamma$  |
| `\varkappa` | $\varkappa$ |
| `\beth`     | $\beth$     |
| `\gimel`    | $\gimel$    |
| `\daleth`   | $\daleth$   |

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

## AMS Binary Operators
| Command            | Rendering          |
| ------------------ | ------------------ |
| `\dotplus`         | $\dotplus$         |
| `\centerdot`       | $\centerdot$       |
| `\ltimes`          | $\ltimes$          |
| `\rtimes`          | $\rtimes$          |
| `\divideontimes`   | $\divideontimes$   |
| `\doublecup`       | $\doublecup$       |
| `\doublecap`       | $\doublecap$       |
| `\smallsetminus`   | $\smallsetminus$   |
| `\veebar`          | $\veebar$          |
| `\barwedge`        | $\barwedge$        |
| `\doublebarwedge`  | $\doublebarwedge$  |
| `\boxplus`         | $\boxplus$         |
| `\boxminus`        | $\boxminus$        |
| `\circleddash`     | $\circleddash$     |
| `\boxtimes`        | $\boxtimes$        |
| `\boxdot`          | $\boxdot$          |
| `\circledcirc`     | $\circledcirc$     |
| `\intercal`        | $\intercal$        |
| `\circledast`      | $\circledast$      |
| `\rightthreetimes` | $\rightthreetimes$ |
| `\curlyvee`        | $\curlyvee$        |
| `\curlywedge`      | $\curlywedge$      |
| `\leftthreetimes`  | $\leftthreetimes$  |

## AMS Binary Relations
| Command               | Rendering             |
| --------------------- | --------------------- |
| `\lessdot`            | $\lessdot$            |
| `\gtrdot`             | $\gtrdot$             |
| `\doteqdot`           | $\doteqdot$           |
| `\leqslant`           | $\leqslant$           |
| `\geqslant`           | $\geqslant$           |
| `\risingdotseq`       | $\risingdotseq$       |
| `\eqslantless`        | $\eqslantless$        |
| `\eqslantgtr`         | $\eqslantgtr$         |
| `\fallingdotseq`      | $\fallingdotseq$      |
| `\leqq`               | $\leqq$               |
| `\geqq`               | $\geqq$               |
| `\eqcirc`             | $\eqcirc$             |
| `\lll`                | $\lll$                |
| `\llless`             | $\llless$             |
| `\ggg`                | $\ggg$                |
| `\circeq`             | $\circeq$             |
| `\lesssim`            | $\lesssim$            |
| `\gtrsim`             | $\gtrsim$             |
| `\triangleq`          | $\triangleq$          |
| `\lessapprox`         | $\lessapprox$         |
| `\gtrapprox`          | $\gtrapprox$          |
| `\bumpeq`             | $\bumpeq$             |
| `\lessgtr`            | $\lessgtr$            |
| `\gtrless`            | $\gtrless$            |
| `\Bumpeq`             | $\Bumpeq$             |
| `\lesseqgtr`          | $\lesseqgtr$          |
| `\gtreqless`          | $\gtreqless$          |
| `\thicksim`           | $\thicksim$           |
| `\lesseqqgtr`         | $\lesseqqgtr$         |
| `\gtreqqless`         | $\gtreqqless$         |
| `\thickapprox`        | $\thickapprox$        |
| `\preccurlyeq`        | $\preccurlyeq$        |
| `\succcurlyeq`        | $\succcurlyeq$        |
| `\approxeq`           | $\approxeq$           |
| `\curlyeqprec`        | $\curlyeqprec$        |
| `\curlyeqsucc`        | $\curlyeqsucc$        |
| `\backsim`            | $\backsim$            |
| `\precsim`            | $\precsim$            |
| `\succsim`            | $\succsim$            |
| `\backsimeq`          | $\backsimeq$          |
| `\precapprox`         | $\precapprox$         |
| `\succapprox`         | $\succapprox$         |
| `\vDash`              | $\vDash$              |
| `\subseteqq`          | $\subseteqq$          |
| `\supseteqq`          | $\supseteqq$          |
| `\Vdash`              | $\Vdash$              |
| `\shortparallel`      | $\shortparallel$      |
| `\Supset`             | $\Supset$             |
| `\Vvdash`             | $\Vvdash$             |
| `\blacktriangleleft`  | $\blacktriangleleft$  |
| `\sqsupset`           | $\sqsupset$           |
| `\backepsilon`        | $\backepsilon$        |
| `\vartriangleright`   | $\vartriangleright$   |
| `\because`            | $\because$            |
| `\varpropto`          | $\varpropto$          |
| `\blacktriangleright` | $\blacktriangleright$ |
| `\Subset`             | $\Subset$             |
| `\between`            | $\between$            |
| `\trianglerighteq`    | $\trianglerighteq$    |
| `\smallfrown`         | $\smallfrown$         |
| `\pitchfork`          | $\pitchfork$          |
| `\vartriangleleft`    | $\vartriangleleft$    |
| `\shortmid`           | $\shortmid$           |
| `\smallsmile`         | $\smallsmile$         |
| `\trianglelefteq`     | $\trianglelefteq$     |
| `\therefore`          | $\therefore$          |
| `\sqsubset`           | $\sqsubset$           |

## AMS Miscellaneous
| Command              | Rendering            |
| -------------------- | -------------------- |
| `\hbar`              | $\hbar$              |
| `\square`            | $\square$            |
| `\vartriangle`       | $\vartriangle$       |
| `\triangledown`      | $\triangledown$      |
| `\lozenge`           | $\lozenge$           |
| `\angle`             | $\angle$             |
| `\diagup`            | $\diagup$            |
| `\hslash`            | $\hslash$            |
| `\blacksquare`       | $\blacksquare$       |
| `\blacktriangle`     | $\blacktriangle$     |
| `\blacktriangledown` | $\blacktriangledown$ |
| `\blacklozenge`      | $\blacklozenge$      |
| `\measuredangle`     | $\measuredangle$     |
| `\diagdown`          | $\diagdown$          |
| `\nexists`           | $\nexists$           |
| `\Finv`              | $\Finv$              |
| `\eth`               | $\eth$               |
| `\sphericalangle`    | $\sphericalangle$    |
| `\Bbbk`              | $\Bbbk$              |
| `\circledS`          | $\circledS$          |
| `\complement`        | $\complement$        |
| `\Game`              | $\Game$              |
| `\bigstar`           | $\bigstar$           |
| `\backprime`         | $\backprime$         |
| `\varnothing`        | $\varnothing$        |
| `\mho`               | $\mho$               |


# Sources

- 2022-06-10: [The Not So Short Introduction to LaTeX2e](https://tobi.oetiker.ch/lshort/lshort.pdf)
- 2022-06-10: [LaTeX Math Symbols Cheat Sheet - Kapeli](https://kapeli.com/cheat_sheets/LaTeX_Math_Symbols.docset/Contents/Resources/Documents/index)
- 2022-06-10: [LaTeX Math for Undergrads](http://tug.ctan.org/info/undergradmath/undergradmath.pdf)
- 2022-06-10: [List of mathematical symbols by subject - Wikipedia](https://en.wikipedia.org/wiki/List_of_mathematical_symbols_by_subject)