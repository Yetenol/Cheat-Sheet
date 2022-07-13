<h1> Microsoft OneNote </h1>

[⌂](../README.md) ([Apps](../README.md#applications)) ›

Table of Contents
- **[Keyboard Shortcuts](#keyboard-shortcuts)**  
    Links to Keyboard Shortcut Lists  
    Apply _Heading 1_ | `[Ctrl + Alt + 2]`
  - [Windows 10 App 🔗](https://support.microsoft.com/en-us/office/keyboard-shortcuts-in-onenote-44b8b3f4-c274-4bcc-a089-e80fdcc87950#PickTab=Windows_10_app)
  - [Windows 🔗](https://support.microsoft.com/en-us/office/keyboard-shortcuts-in-onenote-44b8b3f4-c274-4bcc-a089-e80fdcc87950#PickTab=Windows)
- [Mathematical Typesetting](#mathematical-typesetting)
  - [Supported input languages](#supported-input-languages)
  - [Basics](#basics)
  - [Number sets](#number-sets)
  - [Quotient](#quotient)
  - [Integral](#integral)
  - [Arrays and Matrices](#arrays-and-matrices)
  - [Multiple equations](#multiple-equations)
- [Sources](#sources)


# Mathematical Typesetting

> Microsoft Office uses MS Equation 3.0 (_MathType Equation Editor_)  
> The character `·` indicated to press `[Space]` and  
> the character `→` indicated to press `[Right]`.  
> `[Ctrl + Alt + 0]` clears the formatting of the selection or current line.

## Supported input languages
To typing equations in linear format use the following input language:
- [UnicodeMath](https://www.unicode.org/notes/tn28/UTN28-PlainTextMath-v3.1.pdf)
- [LaTeX](http://tug.ctan.org/info/short-math-guide/short-math-guide.pdf)
  - Symbol integration in all Office applications<>
  - Environments integration only supported in Word

## Basics
- **Enter math mode** by pressing  
  `[Alt + +]` in _OneNote for Windows 10_ (UWP) or  
  `[Alt + =]` in _OneNote_ and other _Office Suite_ applications.  

  Example: `[Alt + +]` `\iff·` `[Alt + +]` renders as $\iff$

- **Evaluate a symbol** (expression without parameters) by pressing  
  `[Space]` once or by pressing  
  `\` to start a new expression.  

  Example: `\alpha\cdot\beta·` renders as $\alpha\cdot\beta$

- **Enter a function** (expression with parameters) by pressing  
  `[Space]` once to enter the first parameter and pressing  
  `[Space]` again to evaluate the function.  

  Example: `\sqrt·a+b·+c` renders as $\sqrt{a+b}+c$

- **Leave math mode** by  
  pressing `[Space]` until all commands are evaluated and  
  then close math mode by pressing  
  `[Alt + +]` in _OneNote for Windows 10_ (UWP) or  
  `[Alt + =]` in _OneNote_ and other _Office Suite_ applications.  

Example: `[Alt + +]` `\sqrt·a+b·-c\cdot\alpha·` `[Alt + +]` renders as $\sqrt{a+b}-c\cdot\alpha$
## Number sets
| Example input | Renders as   |
| ------------- | ------------ |
| `\doubleC`    | $\mathbb{C}$ |
| `\doubleN`    | $\mathbb{N}$ |
| `\doubleQ`    | $\mathbb{Q}$ |
| `\doubleR`    | $\mathbb{R}$ |
| `\doubleZ`    | $\mathbb{Z}$ |

## Quotient
> ⟨dividend⟩`/`⟨divisor⟩

| Example input      | Renders as                            | Format      |
| ------------------ | ------------------------------------- | ----------- |
| `dx/a+b·`          | $\displaystyle\frac{dx}{a+b}$         | UnicodeMath |
| `y^2·/\partial·x·` | $\displaystyle\frac{y^2}{\partial x}$ | UnicodeMath |
| `\frac{dx}{a+b}`   | $\displaystyle\frac{dx}{a+b}$         | LaTeX       |

## Integral
> `\int`⟨interval⟩⟨integrand⟩ [⟨with respect to⟩]
- Press `[Right]` to leave the ⟨integrand⟩ as it opens a new scope
- Type `\int··` for indefinite integral which skips the ⟨interval⟩
    | Example input        | Renders as                        |
    | -------------------- | --------------------------------- |
    | `\int·_a^b·f(x)·→dx` | $\displaystyle\int_a^b{f(x)}\ dx$ |
    | `\int··f(x)·→dx`     | $\displaystyle\int{f(x)}\ dx$     |

## Arrays and Matrices
> `\bmatrix(`⟨entries⟩`)`  
> `&` separates cells within a row  
> `@` starts a new row    
- Enclosing Delimiter:  
    _Github cannot yet display inline matrices correctly_
    | Delimiter                         | Example input                  | Renders as                                               |
    | --------------------------------- | ------------------------------ | -------------------------------------------------------- |
    | Plain                             | `\matrix(1&2@a&b)·`            | $\begin{matrix}1&2\\a&b\end{matrix}$                     |
    | Parentheses <br> _round brackets_ | `\pmatrix(1&2@a&b)·`           | $\begin{pmatrix}1&2\\a&b\end{pmatrix}$                   |
    | Brackets <br> _square brackets_   | `\bmatrix(1&2@a&b)·`           | $\begin{bmatrix}1&2\\a&b\end{bmatrix}$                   |
    | Braces <br> _curly brackets_      | `\Bmatrix(1&2@a&b)·`           | $\begin{Bmatrix}1&2\\a&b\end{Bmatrix}$                   |
    | Absolute Value <br> _pipes_       | `\vmatrix(1&2@a&b)·`           | $\begin{vmatrix}1&2\\a&b\end{vmatrix}$                   |
    | Norm <br> _double pipes_          | `\Vmatrix(1&2@a&b)·`           | $\begin{Vmatrix}1&2\\a&b\end{Vmatrix}$                   |
    | Custom Delimiter                  | `\langle·\matrix(1&2@a&b)·\|·` | $\left\langle\begin{matrix}1&2\\a&b\end{matrix}\right\|$ |
- Display Style:
    | Style                                    | Example input               | Renders as                         |
    | ---------------------------------------- | --------------------------- | ---------------------------------- |
    | typeset in **paragraphs**                | `\textstyle·a=1/2·`         | $\textstyle a=\frac{1}{2}$         |
    | typeset on lines by **themselves**       | `\displaystyle·a=1/2·`      | $\displaystyle a=\frac{1}{2}$      |
    | **sub**scripts or **sup**erscripts       | `\scriptstyle·a=1/2·`       | $\scriptstyle a=\frac{1}{2}$       |
    | **2nd-order** subscripts or superscripts | `\scriptscriptstyle·a=1/2·` | $\scriptscriptstyle a=\frac{1}{2}$ |

## Multiple equations
> `\eqarray(`⟨equations⟩`)`  
> `&` separates alignment columns  
> `@` starts a new line  
- `\eqarray(x&=102@a+b&=x@3/x&=6-1)·` renders as
  $$
  \begin{align*}
  x &= 102 \\
  a+b &= x \\
  \frac{3}{x} &=6-1
  \end{align*}
  $$


# Sources
- 2022-06-10: [Using OneNote to Write Equations – Blake Margolis](https://sites.utexas.edu/margolis/2019/04/09/using-onenote/)
- 2022-06-14: [Keyboard shortcuts in OneNote](https://support.microsoft.com/en-us/office/keyboard-shortcuts-in-onenote-44b8b3f4-c274-4bcc-a089-e80fdcc87950)
- 2022-07-04: [Linear format equations using UnicodeMath and LaTeX in Word](https://support.microsoft.com/en-us/office/linear-format-equations-using-unicodemath-and-latex-in-word-2e00618d-b1fd-49d8-8cb4-8d17f25754f8)
- 2022-07-04: [What's the difference between the OneNote versions-](https://support.microsoft.com/en-us/office/what-s-the-difference-between-the-onenote-versions-a624e692-b78b-4c09-b07f-46181958118f)