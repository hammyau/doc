 

# Examples: IF with SKIP in Extract Record Filter

|Example logic text|Meaning|
|------------------|-------|
|```
IF (CURRENT
    PRIOR
   THEN SKIP
ENDIF
```

|Skip records where field1 is the same as the previous record. This assumes the input file is sorted into field1 order. This example can also be written:```
SKIPIF(CURRENT
       PRIOR
```

|
|```
IF 
   THEN SKIP
ENDIF
```

|Skip for output those records with field3 greater than 1000. Select all other records. The code at left can also be written as:```
SKIPIF
```

|
|```
IF 
   THEN SKIP
ENDIF
```

|Skip for output those records with field2 equal to "ABC". Select all other records.|
|```
IF NOT 
   THEN SKIP
ENDIF
```

|Skip those output records with field2 not equal to "ABC". Select all other records. The code at left gives the same result as:```
SELECTIF
```

|
|```
IF 
   
   THEN SKIP
ENDIF
```

|Skip for output those records with field2 equal to "A" or "D". Select all other records.|
|```
IF 
   
   THEN SKIP
ENDIF
```

|Skip for output those records with field2 equal to "A" and field3 greater than 10. Select all other records.|
|```
IF 
    >
   THEN SKIP
ENDIF
```

|Skip for output those records with field3 plus field4 is greater than field5. Select all other records.|
|```
IF 
   THEN SKIP
ENDIF
```

|Skip for output those records with field6 is equal to all dashes. Select all other records. This example gives the same result as:```
SKIPIF
```

|
|```
IF 
   THEN SKIP
ENDIF
```

|Skip for output those records with field6 is equal to 13 dashes. Select all other records. This example gives the same result as:```
SKIPIF
```

|
|```
IF 
   THEN SKIP
ENDIF
```

|Skip for output those records with field6 is equal to hexadecimal FF. Select all other records. This example gives the same result as:```
SKIPIF
```

|
|```
IF 
   
THEN SKIP
ELSE IF 
     THEN SKIP
     ELSE IF 
          THEN SKIP
          ENDIF
     ENDIF
ENDIF
```

|Skip for output those records with field2 equal to "A" and field3 greater than 10.

In addition, skip for output those records with field2 equal to "D".

In addition, skip for output those records with field2 equal to "G".

Select all other records.

Notice that the logic text at left counts as only one IF statement, because the extra IF statements are nested inside the first.

The code at left can also be written as follows \(note the use of brackets to control the evaluation of the conditions\):

```
IF 
   
   
   
   THEN SKIP
ENDIF
```

|
|```
IF ISNOTFOUND
   THEN SKIP
ENDIF
```

|Skip all input records where the lookup path Lookup4 does not successfully find a target record, and select all other records. This example is the same as:```
SKIPIF(ISNOTFOUND
```

|
|```
IF ISNOTFOUND
   THEN SKIP
ENDIF
```

|Skip all input records where the lookup path Lookup4 does not successfully find a target record using effective date of field7, and select all other records. This example is the same as:```
SKIPIF(ISNOTFOUND
```

|
|```
IF ISNOTFOUND
   THEN SKIP
ENDIF
```

|Skip all input records where the lookup path Lookup4 does not successfully find a target record using symbol SYM set to "A", and select all other records. This example is the same as:```
SKIPIF(ISNOTFOUND
```

|
|```
IF ISNOTFOUND
   
   THEN SKIP
ENDIF
```

|Skip all input records where the lookup path Lookup4 does not successfully find a target record using effective date of field7 and symbol SYM1 set to 3 and symbol SYM2 set to zero. Select all other records. This example is the same as:```
SKIPIF(ISNOTFOUND
                 field7;$SYM1=3,$SYM2=0})
```

|
|```
IF DAYSBETWEEN
     > 7
   THEN SKIP
ENDIF
```

|Skip records where there are more than 7 days between field1 and field2, and select all other records. This example can also be written:```
SKIPIF(DAYSBETWEEN
       > 7)
```

|
|```
IF 
   THEN SKIP
ENDIF
```

|Skip input records where field1 begins with characters "BBB", and select all other records. This example can be written:```
SKIPIF
```

It is better to use BEGINS\_WITH because the logic text executes faster.

|
|```
IF 
   THEN SKIP
ENDIF
```

|Skip input records where field2 contains characters "CCC", and select all other records. This example can be written:```
SKIPIF
```

It is better to use CONTAINS because the logic text executes faster.

|
|```
IF 
   THEN SKIP
ENDIF
```

|Skip input records where field3 ends with characters "EEE", and select all other records. This example can be written:```
SKIPIF
```

It is better to use ENDS\_WITH because the logic text executes faster.

|
|```
IF 
   THEN SKIP
ENDIF
```

|Skip input records where field4 matches characters "...", and select all other records. This example can be written:```
SKIPIF
```

|
|```
IF 
   THEN SKIP
ENDIF
```

|Skip input records where field1 begins with characters "BBB", and select all other records. This example has the same effect as:```
SKIPIF
```

It is better to use BEGINS\_WITH because the logic text executes faster.

|
|```
IF 
   THEN SKIP
ENDIF
```

|Skip input records where field1 contains characters "CCC", and select all other records. This example has the same effect as:```
SKIPIF
```

It is better to use CONTAINS because the logic text executes faster.

|
|```
IF 
   THEN SKIP
ENDIF
```

|Skip input records where field1 ends with characters "EEE", and select all other records. This example has the same effect as:```
SKIPIF
```

It is better to use ENDS\_WITH because the logic text executes faster.

|
|```
IF 
   THEN SKIP
ENDIF
```

|Skip input records where field1 begins with "B", contains "C" and ends with "E", and select all other records.|

**Parent topic:**[Logic text 1: Extract Record Filter](../html/WERLTT100ERecFilter.md)

