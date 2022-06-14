# Regular Expressions
[⌂](../README.md) ([Languages](../README.md#languages-encodings)) ›

> .Net Implementation

- [☟ Miscellaneous Constructs](#miscellaneous-constructs)
- [☟ Engine Interpretation Options](#engine-interpretation-options)
- [☟ Single Characters](#single-characters)
- [☟ Control Characters](#control-characters)
- [☟ Non-ASCII Codes](#non-ascii-codes)
- [☟ Character Classes](#character-classes)
- [☟ Quantifiers](#quantifiers)
- [☟ Anchors](#anchors)
- [☟ Groups](#groups)
- [☟ Inline Options](#inline-options)
- [☟ Backreferences](#backreferences)
- [☟ Alternation](#alternation)
- [☟ Substitution](#substitution)
- [☟ Comments](#comments)
- [☟ Supported Unicode Categories](#supported-unicode-categories)
- [☟ .Net Operations](#net-operations)


## Miscellaneous Constructs

| Construct            | Definition                                                                                                                            | Example                                                       |
| -------------------- | ------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------- |
| `(?imnsx-imnsx)`     | Sets or disables options such as case insensitivity in the middle of a pattern. For more information, see Regular Expression Options. | `\bA(?i)b\w+\b` matches `"ABA"`, `"Able"` in `"ABA Able Act"` |
| `(?#` _comment_ `)`  | Inline comment. The comment ends at the first closing parenthesis.                                                                    | `\bA(?#Matches words starting with A)\w+\b`                   |
| `#` [to end of line] | X-mode comment. The comment starts at an unescaped `#` and continues to the end of the line.                                          | `(?x)\bA\w+\b#Matches words starting with A`                  |


## Engine Interpretation Options

> Start pattern with `(?`_enabled options_`-`_disabled options_`)` e.g: `(?imnsx-imnsx)`


| Inline character | RegexOptions member     | Effect                                                                                                                                                                                                |
| ---------------- | ----------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Not available    | None                    | Use default behavior. For more information, see Default Options.                                                                                                                                      |
| `i`              | IgnoreCase              | Use case-insensitive matching. For more information, see Case-Insensitive Matching.                                                                                                                   |
| `m`              | Multiline               | Use multiline mode, where `^` and `$` match the beginning and end of each line (instead of the beginning and end of the input string). For more information, see Multiline Mode.                      |
| `s`              | Singleline              | Use single-line mode, where the period (.) matches every character (instead of every character except `\n`). For more information, see Single-line Mode.                                              |
| `n`              | ExplicitCapture         | Do not capture unnamed groups. The only valid captures are explicitly named or numbered groups of the form `(?&lt;`_name_`&gt;` _subexpression_`)`. For more information, see Explicit Captures Only. |
| Not available    | Compiled                | Compile the regular expression to an assembly. For more information, see Compiled Regular Expressions.                                                                                                |
| `x`              | IgnorePatternWhitespace | Exclude unescaped white space from the pattern, and enable comments after a number sign (`#`). For more information, see Ignore White Space.                                                          |
| Not available    | RightToLeft             | Change the search direction. Search moves from right to left instead of from left to right. For more information, see Right-to-Left Mode.                                                             |
| Not available    | ECMAScript              | Enable ECMAScript-compliant behavior for the expression. For more information, see ECMAScript Matching Behavior.                                                                                      | <tr>  |
| Not available    | CultureInvariant        | Ignore cultural differences in language. For more information, see Comparison Using the Invariant Culture.                                                                                            | </tr> |

## Single Characters

| Use      | To match any character    |
| -------- | ------------------------- |
| `[set]`  | In that set               |
| `[^set]` | Not in that set           |
| `[a–z]`  | In the a-z range          |
| `[^a–z]` | Not in the a-z range      |
| `.`      | Any except \n (new line)  |
| `\char`  | Escaped special character |


## Control Characters

| Use       | To match                | Unicode |
| --------- | ----------------------- | ------- |
| `\t`      | Horizontal tab          | \u0009  |
| `\v`      | Vertical tab            | \u000B  |
| `\b`      | Backspace               | \u0008  |
| `\e`      | Escape                  | \u001B  |
| `\r`      | Carriage return         | \u000D  |
| `\f`      | Form feed               | \u000C  |
| `\n`      | New line                | \u000A  |
| `\a`      | Bell (alarm)            | \u0007  |
| `\c char` | ASCII control character | -       |


## Non-ASCII Codes

| Use      | To match character with        |
| -------- | ------------------------------ |
| `\octal` | 2-3 digit octal character code |
| `\x hex` | 2-digit hex character code     |
| `\u hex` | 4-digit hex character code     |


## Character Classes

| Use         | To match character                    |
| ----------- | ------------------------------------- |
| `\p{ctgry}` | In that Unicode category or block     |
| `\P{ctgry}` | Not in that Unicode category or block |
| `\w`        | Word character                        |
| `\W`        | Non-word character                    |
| `\d`        | Decimal digit                         |
| `\D`        | Not a decimal digit                   |
| `\s`        | White-space character                 |
| `\S`        | Non-white-space char                  |


## Quantifiers

| Greedy <br> _as many as possible_ | Lazy <br> _as few as possible_ | Matches           |
| --------------------------------- | ------------------------------ | ----------------- |
| `*`                               | *?                             | 0 or more times   |
| `+`                               | +?                             | 1 or more times   |
| `?`                               | ??                             | 0 or 1 time       |
| `{n}`                             | {n}?                           | Exactly n times   |
| `{n,}`                            | {n,}?                          | At least n times  |
| `{n,m}`                           | {n,m}?                         | From n to m times |


## Anchors

| Use  | To specify position                            |
| ---- | ---------------------------------------------- |
| `^`  | At start of string or line                     |
| `\A` | At start of string                             |
| `\z` | At end of string                               |
| `\Z` | At end (or before \n at end) of string         |
| `$`  | At end (or before \n at end) of string or line |
| `\G` | Where previous match ended                     |
| `\b` | On word boundary                               |
| `\B` | Not on word boundary                           |


## Groups

| Use                   | To define                      |
| --------------------- | ------------------------------ |
| `(exp)`               | Indexed group                  |
| `(?<name>exp)`        | Named group                    |
| `(?<name1-name2>exp)` | Balancing group                |
| `(?:exp)`             | Noncapturing group             |
| `(?=exp)`             | Zero-width positive lookahead  |
| `(?!exp)`             | Zero-width negative lookahead  |
| `(?<=exp)`            | Zero-width positive lookbehind |
| `(?<!exp)`            | Zero-width negative lookbehind |
| `(?>exp)`             | Non-backtracking (greedy)      |


## Inline Options

| Option | Effect on match    |
| ------ | ------------------ |
| `i`    | Case-insensitive   |
| `m`    | Multiline mode     |
| `n`    | Explicit (named)   |
| `s`    | Single-line mode   |
| `x`    | Ignore white space |

| Use                  | To                                                         |
| -------------------- | ---------------------------------------------------------- |
| `(?imnsx-imnsx)`     | Set or disable the specified options                       |
| `(?imnsx-imnsx:exp)` | Set or disable the specified options within the expression |


## Backreferences

| Use        | To match      |
| ---------- | ------------- |
| `\n`       | Indexed group |
| `\k<name>` | Named group   |


## Alternation

| Use                        | To match                                                 |
| -------------------------- | -------------------------------------------------------- |
| `a\|b`                     | Either a or b                                            |
| `(?(exp)`_yes_`\|`_no_`)`  | _yes_ if exp is matched <br> _no_ if exp isn't matched   |
| `(?(name)`_yes_`\|`_no_`)` | _yes_ if name is matched <br> _no_ if name isn't matched |


## Substitution

| Use       | To substitute                       |
| --------- | ----------------------------------- |
| `$n`      | Substring matched by group number n |
| `${name}` | Substring matched by group name     |
| `$$`      | Literal $ character                 |
| `$&`      | Copy of whole match                 |
| `$`\`     | Text before the match               |
| `$'`      | Text after the match                |
| `$+`      | Last captured group                 |
| `$_`      | Entire input string                 |


## Comments

| Use            | To                 |
| -------------- | ------------------ |
| `(?# comment)` | Add inline comment |
| `#`            | Add x-mode comment |


## Supported Unicode Categories

| Category | Description                     |
| -------- | ------------------------------- |
| `Lu`     | Letter, uppercase               |
| `LI`     | Letter, lowercase               |
| `Lt`     | Letter, title case              |
| `Lm`     | Letter, modifier                |
| `Lo`     | Letter, other                   |
| `L `     | Letter, all                     |
| `Mn`     | Mark, nonspacing combining      |
| `Mc`     | Mark, spacing combining         |
| `Me`     | Mark, enclosing combining       |
| `M `     | Mark, all diacritic             |
| `Nd`     | Number, decimal digit           |
| `Nl`     | Number, letterlike              |
| `No`     | Number, other                   |
| `N `     | Number, all                     |
| `Pc`     | Punctuation, connector          |
| `Pd`     | Punctuation, dash               |
| `Ps`     | Punctuation, opening mark       |
| `Pe`     | Punctuation, closing mark       |
| `Pi`     | Punctuation, initial quote mark |
| `Pf`     | Puntuation, final quote mark    |
| `Po`     | Punctuation, other              |
| `P `     | Punctuation, all                |
| `Sm`     | Symbol, math                    |
| `Sc`     | Symbol, currency                |
| `Sk`     | Symbol, modifier                |
| `So`     | Symbol, other                   |
| `S `     | Symbol, all                     |
| `Zs`     | Separator, space                |
| `Zl`     | Separator, line                 |
| `Zp`     | Separator, paragraph            |
| `Z `     | Separator, all                  |
| `Cc`     | Control code                    |
| `Cf`     | Format control character        |
| `Cs`     | Surrogate code point            |
| `Co`     | Private-use character           |
| `Cn`     | Unassigned                      |
| `C `     | Control characters, all         |


## [.Net Operations](regex-dot-net.md)


# Sources 

- 2022-01-26: [Quick Reference (MS Docs)](https://docs.microsoft.com/en-us/dotnet/standard/base-types/regular-expression-language-quick-reference)
- 2022-04-04: [Regular Expression Language - Quick Reference - Microsoft Docs](https://docs.microsoft.com/en-us/dotnet/standard/base-types/regular-expression-language-quick-reference#regular-expression-options)
- 2022-01-26: [Visual Studio (MS Docs)](https://docs.microsoft.com/en-us/visualstudio/ide/using-regular-expressions-in-visual-studio)
- 2022-01-26: [🗎 .NET Framework Regular Expressions](regex.pdf)