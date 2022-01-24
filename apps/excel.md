# [⌂](../README.md) ([Apps](../README.md#apps)) › **Microsoft Excel**


## Set common names

- **SELECT** `A1`
- open Name Manager (`Ctrl + F3`)
- click `New...`
- add the following entries

Name: | Scope: | Refers to:
--- | --- | ---
`THIS_CELL` | _current sheet_ | `=A1`
`THIS_ROW` | _current sheet_ | `=ROW(THIS_CELL)`
`THIS_COLUMN_NUMBER` | _current sheet_ | `=COLUMN(THIS_CELL)`
`THIS_COLUMN` | _current sheet_ | `=SUBSTITUTE(ADDRESS(THIS_ROW, THIS_COLUMN_NUMBER,4),THIS_ROW,"")`

- repeat for every sheet


### Get cell information

- **REQUIRES** [Set common names](#set-common-names)

Description | Command | Example
--- | --- | ---
Get current cell | `=THIS_CELL` | C2 => `0` <br> throws circular reference
Get current row | `=THIS_ROW` | C2 => `2`
Get current column | `=THIS_COLUMN` | C2 => `C`
Get current column number | `=THIS_COLUMN_NUMBER` | C2 => `3`
Get current address | `=ADDRESS(THIS_ROW,THIS_COLUMN_NUMBER)` | C2 => `$C$2`
Get current address | `=ADDRESS(THIS_ROW,THIS_COLUMN_NUMBER,4)` | C2 => `C2`


### Get neighboring cells

- **REQUIRES** [Set common names](#set-common-names)

Description | Command | Example
--- | --- | ---
Get current cell | `=INDIRECT(THIS_COLUMN & THIS_ROW)` <br> `=INDIRECT(ADDRESS(THIS_ROW,THIS_COLUMN_NUMBER))` | C2 => `=C2` <br> throws circular reference
Get E column in current row | `=INDIRECT("E" & THIS_ROW)` | C2 => `=E2`
Get 5th row in current column | `=INDIRECT(THIS_COLUMN & 5)` | C2 => `=C5`
Get right neighbor | `=INDIRECT(ADDRESS(THIS_ROW,THIS_COLUMN_NUMBER+1))` | C2 => `=C3`
Get left neighbor | `=INDIRECT(ADDRESS(THIS_ROW,THIS_COLUMN_NUMBER-1))` | C2 => `=C1`
Get upper neighbor | `=INDIRECT(ADDRESS(THIS_ROW-1,THIS_COLUMN_NUMBER))` | C2 => `=B2`
Get lower neighbor | `=INDIRECT(ADDRESS(THIS_ROW+1,THIS_COLUMN_NUMBER))` | C2 => `=D2`


Is a range of cells empty
```
=IF(SUMPRODUCT(--(D16:G16<>""))<>0,"not empty","empty")
```

Get last non-empty cell in a given range
```
=SUM(A4:INDEX(A4:A10,MATCH(TRUE,(A4:A10=""),0)))
```

Sum column values until next blank cell?
```
=SUM(A4:INDEX(A4:A10,MATCH(TRUE,(A4:A10=""),0)))
```