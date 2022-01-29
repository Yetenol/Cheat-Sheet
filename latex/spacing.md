# [⌂](../README.md) › [LaTeX](../README.md#latex) › **Spacing**


| Command                                                                                            | Description                                                      |
| -------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------- |
| `\\` <br> `\newline`                                                                               | starts a new line without starting a new paragraph               |
| `\\*`                                                                                              | additionally prohibits a page break after the forced line break. |
| `newpage`                                                                                          | starts a new page                                                |
| `\linebreak[`_n_`]` <br> `\nolinebreak[`_n_`]` <br> `\pagebreak[`_n_`]` <br> `\nopagebreak[`_n_`]` | suggest places where a break may (or may not) happen             |


## Hyphenation

- define the hyphenation of a word list
```latex
\hyphenation{FORTRAN Hy-phen-a-tion}
```

| .            | Meaning                                                                                                          |
| ------------ | ---------------------------------------------------------------------------------------------------------------- |
| `\-`         | inserts a discretionary hyphen into a word. This also becomes the only point hyphenation is allowed in this word |
| `mbox{text}` | be kept together under all circumstances (e.g. phone number)                                                     |
| `\fbox`      | is similar to `\mbox`, but in addition there will be a visible box drawn around the content.                     |
