# Microsoft OneNote
[⌂](../README.md) ([Apps](../README.md#applications)) ›

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

# Keyboard Shortcuts

## Frequently used shortcuts
| To do this                                                                                | Press                                              |
| ----------------------------------------------------------------------------------------- | -------------------------------------------------- |
| Open a new OneNote window.                                                                | Ctrl+M                                             |
| Create a Quick Note.                                                                      | Ctrl+Shift+M or Alt+Windows logo key+N             |
| Dock the OneNote window.                                                                  | Ctrl+Alt+D                                         |
| Undo the previous action.                                                                 | Ctrl+Z                                             |
| Redo the previous action, if possible.                                                    | Ctrl+Y                                             |
| Select all items on the current page.                                                     | Ctrl+ATo expand the selection, press Ctrl+A again. |
| Cut the selected text or item.                                                            | Ctrl+X                                             |
| Copy the selected text or item to the clipboard.                                          | Ctrl+C                                             |
| Paste the contents of the clipboard.                                                      | Ctrl+V                                             |
| Move to the beginning of the line.                                                        | Home                                               |
| Move to the end of the line.                                                              | End                                                |
| Move one word to the left.                                                                | Ctrl+Left arrow key                                |
| Move one word to the right.                                                               | Ctrl+Right arrow key                               |
| Delete one character to the left.                                                         | Backspace                                          |
| Delete one character to the right.                                                        | Delete                                             |
| Delete one word to the left.                                                              | Ctrl+Backspace                                     |
| Delete one word to the right.                                                             | Ctrl+Delete                                        |
| Insert a line break without starting a new paragraph.                                     | Shift+Enter                                        |
| Check spelling.                                                                           | F7                                                 |
| Open the thesaurus for the currently selected word.                                       | Shift+F7                                           |
| Display the context menu for the currently focused object.                                | Shift+F10 or Windows Menu key                      |
| Perform the action suggested on the Information Bar when it appears at the top of a page. | Ctrl+Shift+W                                       |
| Play the selected audio recording.                                                        | Ctrl+Alt+P                                         |
| Stop audio recording playback.                                                            | Ctrl+Alt+S                                         |
| Skip the current audio recording backward by 10 seconds.                                  | Ctrl+Alt+Y                                         |
| Skip the current audio recording forward by 10 seconds.                                   | Ctrl+Alt+U                                         |

## Format notes
| To do this                                                                   | Press                                                                    |
| ---------------------------------------------------------------------------- | ------------------------------------------------------------------------ |
| Highlight the selected text.                                                 | Ctrl+Alt+H                                                               |
| Insert a hyperlink.                                                          | Ctrl+K                                                                   |
| Copy the formatting of the selected text (Format Painter).                   | Ctrl+Shift+C                                                             |
| Paste the formatting to the selected text (Format Painter).                  | Ctrl+Shift+V                                                             |
| Open a hyperlink.                                                            | Enter when on the hyperlink text                                         |
| Apply or remove bold formatting.                                             | Ctrl+B                                                                   |
| Apply or remove italics formatting.                                          | Ctrl+I                                                                   |
| Apply or remove underline formatting.                                        | Ctrl+U                                                                   |
| Apply or remove strikethrough formatting.                                    | Ctrl+Hyphen (-)                                                          |
| Apply or remove superscript formatting.                                      | Ctrl+Shift+Equal sign ( = )                                              |
| Apply or remove subscript formatting.                                        | Ctrl+Equal sign ( = )                                                    |
| Apply or remove bulleted list formatting.                                    | Ctrl+Period (.)                                                          |
| Apply or remove numbered list formatting.                                    | Ctrl+Forward slash (/)                                                   |
| Apply a Heading 1 style to the current note.                                 | Ctrl+Alt+1                                                               |
| Apply a Heading 2 style to the current note.                                 | Ctrl+Alt+2                                                               |
| Apply a Heading 3 style to the current note.                                 | Ctrl+Alt+3                                                               |
| Apply a Heading 4 style to the current note.                                 | Ctrl+Alt+4                                                               |
| Apply a Heading 5 style to the current note.                                 | Ctrl+Alt+5                                                               |
| Apply a Heading 6 style to the current note.                                 | Ctrl+Alt+6                                                               |
| Clear all formatting applied to the selected text. (Apply the Normal style.) | Ctrl+Shift+N                                                             |
| Increase the paragraph indent.                                               | Alt+Shift+Right arrow key or the Tab key when at the beginning of a line |
| Decrease the paragraph indent.                                               | Alt+Shift+Left arrow key or Shift+Tab when at the beginning of a line    |
| Align the paragraph to the left.                                             | Ctrl+L                                                                   |
| Align the paragraph to the right.                                            | Ctrl+R                                                                   |
| Increase the font size of the selected text.                                 | Ctrl+Shift+Right angle bracket (>)                                       |
| Decrease the font size of the selected text.                                 | Ctrl+Shift+Left angle bracket (<)                                        |
| Show or hide the rule lines on the current page.                             | Ctrl+Shift+R                                                             |

## Insert items on a page
| To do this                                                                                                                                              | Press                                                                                 |
| ------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------- |
| Insert a document or file on the current page.                                                                                                          | Alt+N, F                                                                              |
| Insert a document or file as a printout on the current page.                                                                                            | Alt+N, O                                                                              |
| Show or hide document printouts on the current page when the high contrast mode on Windows 10 or one of the contrast themes on Windows 11 is activated. | Alt+Shift+P                                                                           |
| Insert a picture from a file.                                                                                                                           | Alt+N, P                                                                              |
| Insert a sticker.                                                                                                                                       | Alt+N, S                                                                              |
| Insert a screen clipping.Note: The OneNote icon must be active in the Windows taskbar notification area.                                                | Windows logo key+Shift+S, and then Ctrl+VIn OneNote 2007 and 2010, Windows logo key+S |
| Insert the current date.                                                                                                                                | Alt+Shift+D                                                                           |
| Insert the current date and time.                                                                                                                       | Alt+Shift+F                                                                           |
| Insert the current time.                                                                                                                                | Alt+Shift+T                                                                           |
| Insert a line break.                                                                                                                                    | Shift+Enter                                                                           |
| Start a math equation or convert selected text to a math equation.                                                                                      | Alt+Equal sign ( = )                                                                  |

## Work with tables
| To do this                                                     | Press                                                                          |
| -------------------------------------------------------------- | ------------------------------------------------------------------------------ |
| Create a table.                                                | Tab key after typing a new line of text                                        |
| Create another column in a table with a single row.            | Tab key                                                                        |
| Create another row when at the end cell of a table.            | EnterNote: Press Enter again to finish creating the table.                     |
| Insert a row below the current row.                            | Ctrl+Enter when in a table cell                                                |
| Create another paragraph in the same cell in a table.          | Alt+Enter                                                                      |
| Create a column to the right of the current column in a table. | Ctrl+Alt+R                                                                     |
| Create a column to the left of the current column in a table.  | In OneNote 2010, Ctrl+Alt+E                                                    |
| Create a row above the current one in a table.                 | Enter when the cursor is at the beginning of any row, except for the first row |
| Create a new cell or row.                                      | Tab key when in the last cell of the table                                     |
| Delete the current empty row in a table.                       | Delete, then Delete again, when the cursor is at the beginning of the row      |

## Select text and objects
| To do this                                                      | Press                                                                |
| --------------------------------------------------------------- | -------------------------------------------------------------------- |
| Select all items on the current page.                           | Ctrl+ATo expand the selection, press Ctrl+A again.                   |
| Select to the end of the line from the current cursor location. | Shift+End                                                            |
| Select the whole line.                                          | Shift+Down arrow key when the cursor is at the beginning of the line |
| Jump to the title of the page and select it.                    | Ctrl+Shift+T                                                         |
| Cancel selecting the outline or page.                           | Esc                                                                  |
| Move the selected paragraphs upward.                            | Alt+Shift+Up arrow key                                               |
| Move the selected paragraphs downward.                          | Alt+Shift+Down arrow key                                             |
| Increase the paragraph indent.                                  | Alt+Shift+Left arrow key                                             |
| Decrease the paragraph indent.                                  | Alt+Shift+Right arrow key                                            |
| Select the current paragraph and its subordinate paragraphs.    | Ctrl+Shift+Hyphen (-)                                                |
| Delete the selected note or object.                             | Delete                                                               |
| Move to the beginning of the line.                              | Home                                                                 |
| Move to the end of the line.                                    | End                                                                  |
| Go back to the last page visited.                               | Alt+Left arrow key                                                   |
| Go forward to the next page visited.                            | Alt+Right arrow key                                                  |




# Sources
- 2022-06-10: [Using OneNote to Write Equations – Blake Margolis](https://sites.utexas.edu/margolis/2019/04/09/using-onenote/)