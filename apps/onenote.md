# Microsoft OneNote
[⌂](../README.md) ([Apps](../README.md#applications)) ›
- **[Keyboard Shortcuts](#keyboard-shortcuts)**  
    Links to Keyboard Shortcut Lists  
    Apply _Heading 1_ | `[Ctrl + Alt + 2]`
  - [Windows 10 App ›](https://support.microsoft.com/en-us/office/keyboard-shortcuts-in-onenote-44b8b3f4-c274-4bcc-a089-e80fdcc87950#PickTab=Windows_10_app)
  - [Windows ›](https://support.microsoft.com/en-us/office/keyboard-shortcuts-in-onenote-44b8b3f4-c274-4bcc-a089-e80fdcc87950#PickTab=Windows)
- [Mathematical Typesetting](#mathematical-typesetting)
  - [Basics](#basics)
  - [Number sets](#number-sets)
  - [Derivatives](#derivatives)
  - [Integral](#integral)
  - [Arrays and Matrices](#arrays-and-matrices)
- [Sources](#sources)


# Mathematical Typesetting

> Microsoft Office uses MS Equation 3.0 (_MathType Equation Editor_)

## Basics
- To enter math mode press
    - `[Alt + +]` in _OneNote for Windows 10_ (UWP) or 
    - `[Alt + =]` in _OneNote_ (Office Suite)
- To leave math mode press `[Right]` until the surrounding box disappears
- To evaluate an expression or close a scope press a `[Space]`.
  - E.g: Typing `\sqrt` and **one** `[Space]` opens a scope (the radicand). 
    Everything you type now will be displayed under the square root.
    To write next to the square root again, press `[Space]` which leaves the scope.

    Type: `\sqrt a+b -c\cdot \alpha ` to render $\sqrt{a+b}-c\cdot\alpha$

## Number sets
| Command    | Rendering    |
| ---------- | ------------ |
| `\doubleC` | $\mathbb{C}$ |
| `\doubleN` | $\mathbb{N}$ |
| `\doubleQ` | $\mathbb{Q}$ |
| `\doubleR` | $\mathbb{R}$ |
| `\doubleZ` | $\mathbb{Z}$ |

## Derivatives
- derivates don't require a command, just type `/`
    | Example Input      | Renders as                            |
    | ------------------ | ------------------------------------- |
    | `dy/dx `           | $\displaystyle\frac{dy}{dx}$          |
    | `y^2 /\partial x ` | $\displaystyle\frac{y^2}{\partial x}$ |
- regular LaTeX like `\frac {1}{2}` renders as $\displaystyle\frac{1}{2}$

## Integral
- Press `[Space]` twice for indefinite integrals, to make sure you are inside the integral
- Press `[Right]` (indicated by →) to leave the inside of the integral to write the differential
    | Example Input        | Renders as                        |
    | -------------------- | --------------------------------- |
    | `\int _a^b f(x) →dx` | $\displaystyle\int_a^b{f(x)}\ dx$ |
    | `\int  f(x) →dx`     | $\displaystyle\int{f(x)}\ dx$     |

## Arrays and Matrices
- `&` separates cells within a row
- `@` starts a new row    
- Enclosing Delimiter:  
    _Github cannot yet display inline matrices correctly_
    | Delimiter                         | OneNote markup                 | Renders as                                               |
    | --------------------------------- | ------------------------------ | -------------------------------------------------------- |
    | Plain                             | `\matrix(1&2@a&b) `            | $\begin{matrix}1&2\\a&b\end{matrix}$                     |
    | Parentheses <br> _round brackets_ | `\pmatrix(1&2@a&b) `           | $\begin{pmatrix}1&2\\a&b\end{pmatrix}$                   |
    | Brackets <br> _square brackets_   | `\bmatrix(1&2@a&b) `           | $\begin{bmatrix}1&2\\a&b\end{bmatrix}$                   |
    | Braces <br> _curly brackets_      | `\Bmatrix(1&2@a&b) `           | $\begin{Bmatrix}1&2\\a&b\end{Bmatrix}$                   |
    | Absolute Value <br> _pipes_       | `\vmatrix(1&2@a&b) `           | $\begin{vmatrix}1&2\\a&b\end{vmatrix}$                   |
    | Norm <br> _double pipes_          | `\Vmatrix(1&2@a&b) `           | $\begin{Vmatrix}1&2\\a&b\end{Vmatrix}$                   |
    | Custom Delimiter                  | `\langle \matrix(1&2@a&b) \| ` | $\left\langle\begin{matrix}1&2\\a&b\end{matrix}\right\|$ |
- Display Style:
    | Style                                    | OneNote markup              | Renders as                         |
    | ---------------------------------------- | --------------------------- | ---------------------------------- |
    | typeset in **paragraphs**                | `\textstyle a=1/2 `         | $\textstyle a=\frac{1}{2}$ Text    |
    | typeset on lines by **themselves**       | `\displaystyle a=1/2 `      | $\displaystyle a=\frac{1}{2}$      |
    | **sub**scripts or **sup**erscripts       | `\scriptstyle a=1/2 `       | $\scriptstyle a=\frac{1}{2}$       |
    | **2nd-order** subscripts or superscripts | `\scriptscriptstyle a=1/2 ` | $\scriptscriptstyle a=\frac{1}{2}$ |

# Sources
- 2022-06-10: [Using OneNote to Write Equations – Blake Margolis](https://sites.utexas.edu/margolis/2019/04/09/using-onenote/)
- 2022-06-14: [Keyboard shortcuts in OneNote](https://support.microsoft.com/en-us/office/keyboard-shortcuts-in-onenote-44b8b3f4-c274-4bcc-a089-e80fdcc87950)