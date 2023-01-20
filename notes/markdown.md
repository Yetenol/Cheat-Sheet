---
example: LaTeX Render
command: ![](https://render.githubusercontent.com/render/math?math=e^{i\pi}=-1)
---

## LaTeX Rendering

1. Comparison

| Code                                                                                                                                                                              | Native Rendering                                                                                                                             | Image Rendering                                                                                                                                                                                                                      |
| --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `$\int_0^1{\pi^2} \geq 0$`                                                                                                                                                        | $\int_0^1{\pi^2} \geq 0$                                                                                                                     | ![equation](https://render.githubusercontent.com/render/math?math=\int_0^1{\pi^2}\geq{}0)                                                                                                                                            |
| `$\begin{bmatrix}` <br> `1 & 2 & \ldots & n \\` <br> `10 & 20 & \ldots & 10n \\` <br> `\vdots & \vdots & \ddots & \vdots \\` <br> `m & 2m & \ldots & 10^nm` <br> `\end{bmatrix}$` | $\begin{bmatrix} 1 & 2 & \ldots & n \\ 10 & 20 & \ldots & 10n \\ \vdots & \vdots & \ddots & \vdots \\ m & 2m & \ldots & 10^nm \end{bmatrix}$ | <img src="https://render.githubusercontent.com/render/math?math=\begin{bmatrix} 1 %26 2 %26 \ldots %26 n \\ 10 %26 20 %26 \ldots %26 10n \\ \vdots %26 \vdots %26 \ddots %26 \vdots \\ m %26 2m %26 \ldots %26 10^nm \end{bmatrix}"> |

1. Native Markdown Solution

    ```latex
    $\int_0^1{\pi^2} \geq 0$
    ```

    $\int_0^1{\pi^2} \geq 0$

1. Image Rendering

    ```markdown
    ![equation](https://render.githubusercontent.com/render/math?math=)                                                                                                                                           
    ```

    ![equation](https://render.githubusercontent.com/render/math?math=\int_0^1{\pi^2}\geq{}0)                                                                                                                                           


2. HTML Image Rendering

    > Allows spaces in url.

    ```html
    <img src="https://render.githubusercontent.com/render/math?math=">
    ```

    <img src="https://render.githubusercontent.com/render/math?math=\int_0^1{\pi^2} \geq 0">

## Special Character Escaping

| Character | Escape Code                 | Name                |
| --------- | --------------------------- | ------------------- |
| \         | `\\\\`                      | backslash           |
| &#96;     | \\&#96; <br> `&#96;`        | backtick            |
| &#96;     | &#96;&#96; &#96; &#96;&#96; | backtick in code    |
| \*        | `\*`                        | asterisk            |
| \_        | `\_`                        | underscore          |
| \{ \}     | `\{` `\}`                   | curly braces        |
| \[ \]     | `\[` `\]`                   | brackets            |
| \< \>     | `\<` `\>`                   | angle brackets      |
| \( \)     | `\(` `\)`                   | parentheses         |
| \#        | `\#`                        | pound sign          |
| \+        | `\+`                        | plus sign           |
| \-        | `\-`                        | minus sign (hyphen) |
| \.        | `\.`                        | dot                 |
| \!        | `\!`                        | exclamation mark    |
| \|        | `\\|` <br> `&#124;`         | pipe                |


---


Sources:
- 2022-04-04: [A hack for showing LaTeX formulas in GitHub markdown.md · GitHub](https://gist.github.com/a-rodin/fef3f543412d6e1ec5b6cf55bf197d7b)

Related:

Tags:
[Languages and Encodings](../notes/Languages%20and%20Encodings.md)