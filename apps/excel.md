# [⌂](../README.md) ([Apps](../README.md#apps)) › **Microsoft Excel**

Is a range of cells empty
```
=IF(SUMPRODUCT(--(D16:G16<>""))<>0;"not empty";"empty")
```

Get last non-empty cell in a given range
```
=SUM(A4:INDEX(A4:A10;MATCH(TRUE;(A4:A10="");0)))
```

Sum column values until next blank cell?
```
=SUM(A4:INDEX(A4:A10;MATCH(TRUE;(A4:A10="");0)))
```