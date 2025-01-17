 

# Examples: IF with SELECT in Extract Record Filter

|Example logic text|Meaning|
|------------------|-------|
|```
IF (CURRENT
    PRIOR
   THEN SELECT
ENDIF
```

|Select only records with unique values for field1. This assumes the input file is sorted into field1 order. This example can also be written:```
SELECTIF(CURRENT
         PRIOR
```

|
|```
IF 
   THEN SELECT
ENDIF
```

|Select for output only those records with field3 greater than 1000. Skip all other records. The code at left can also be written as:```
SELECTIF
```

|
|```
IF 
   THEN SELECT
ENDIF
```

|Select for output only those records with field2 equal to "ABC". Skip all other records.|
|```
IF NOT 
   THEN SELECT
ENDIF

```

|Select those output records with field2 not equal to "ABC". Skip all other records. The code at left gives the same result as:```
SKIPIF
```

|
|```
IF 
   
   THEN SELECT
ENDIF
```

|Select for output only those records with field2 equal to "ABC" or "DEF". Skip all other records.|
|```
IF 
   
   THEN SELECT
ENDIF
```

|Select for output only those records with field2 equal to "ABC" and field3 greater than 1000. Skip all other records.|
|```
IF 
   
   THEN SELECT
ENDIF
```

|Select for output only those records with field3 plus field4 is greater than field5 times 100. Skip all other records.|
|```
IF NOT 
   THEN SELECT
ENDIF
```

|Select for output those records with field6 is not equal to all dashes. Skip all other records. This example gives the same result as:```
SKIPIF
```

|
|```
IF 
   THEN SELECT
ENDIF
```

|Select for output those records with field6 is equal to 13 dashes. Skip all other records.|
|```
IF 
   THEN SELECT
ENDIF
```

|Select for output those records with field6 is equal to hexadecimal FF. Skip all other records.|
|```
IF 
   
THEN SELECT
ELSE IF 
     THEN SELECT
     ELSE IF 
          THEN SELECT
          ENDIF
     ENDIF
ENDIF
```

|Select for output those records with field2 equal to "ABC" and field3 greater than 10.

In addition, select for output those records with field2 equal to "DEF".

In addition, select for output those records with field2 equal to "GHI".

Skip all other records.

Notice that the logic text at left counts as only one IF statement, because the extra IF statements are nested inside the first.

The code at left can also be written as follows \(note the use of brackets to control the evaluation of the conditions\):

```
IF 
  
   
   
   THEN SELECT
ENDIF 
```

|
|```
IF 
   
THEN IF 
       >
     THEN SELECT
     ELSE IF 
          THEN SELECT
          ENDIF
     ENDIF
ENDIF
```

|Consider those records with field2 equal to "ABC" and field3 greater than 10.

Of the considered records, select for output those records with field4 plus field5 is greater then field6.

Of the considered records not yet selected, select also for output those records with field7 equal to zero.

Skip all other records.

Notice that the logic text at left counts as only one IF statement, because the extra IF statements are nested inside the first.

The code at left can also be written as follows \(note the use of brackets to control the evaluation of the conditions\):

```
IF 
   
                          AND
   (
       >
   
   THEN SELECT
ENDIF 
```

|
|```
IF ISFOUND
   THEN SELECT
ENDIF
```

|Select all input records where the lookup path Lookup3 successfully finds a target record, and skip all other records. This example is the same as:```
SELECTIF(ISFOUND
```

|
|```
IF ISFOUND
   THEN SELECT
ENDIF
```

|Select all input records where the lookup path Lookup3 successfully finds a target record using effective date of field7, and skip all other records. This example is the same as:```
SELECTIF(ISFOUND
```

|
|```
IF ISFOUND
   THEN SELECT
ENDIF
```

|Select all input records where the lookup path Lookup3 successfully finds a target record using symbol SYM set to "A", and skip all other records. This example is the same as:```
SELECTIF(ISFOUND
```

|
|```
IF ISFOUND
            field7;$SYM1=3,$SYM2=0})
   THEN SELECT
ENDIF
```

|Select all input records where the lookup path Lookup3 successfully finds a target record using effective date of field7 and symbol SYM1 set to 3 and symbol SYM2 set to zero. Skip all other records. This example is the same as:```
SELECTIF(ISFOUND
         field7;$SYM1=3,$SYM2=0})
```

|
|```
IF DAYSBETWEEN
     > 7
   THEN SELECT
ENDIF
```

|Select only records where there are more than 7 days between field1 and field2, and skip all other records This example can also be written:```
SELECTIF(DAYSBETWEEN
          > 7)
```

|
|```
IF 
   THEN SELECT
ENDIF
```

|Select input records where field1 begins with characters "BBB", and skip all other records. This example can be written:```
SELECTIF
```

It is better to use BEGINS\_WITH because the logic text executes faster.

|
|```
IF 
   THEN SELECT
ENDIF
```

|Select input records where field2 contains characters "CCC", and skip all other records. This example can be written:```
SELECTIF
```

It is better to use CONTAINS because the logic text executes faster.

|
|```
IF 
   THEN SELECT
ENDIF
```

|Select input records where field3 ends with characters "EEE", and skip all other records. This example can be written:```
SELECTIF
```

It is better to use ENDS\_WITH because the logic text executes faster.

|
|```
IF 
   THEN SELECT
ENDIF
```

|Select input records where field4 matches characters "...", and skip all other records. This example can be written:```
SELECTIF
```

|
|```
IF 
   THEN SELECT
ENDIF
```

|Select input records where field1 begins with characters "BBB", and skip all other records. This example has the same effect as:```
SELECTIF
```

It is better to use BEGINS\_WITH because the logic text executes faster.

|
|```
IF 
   THEN SELECT
ENDIF
```

|Select input records where field1 contains characters "CCC", and skip all other records. This example has the same effect as:```
SELECTIF
```

It is better to use CONTAINS because the logic text executes faster.

|
|```
IF 
   THEN SELECT
ENDIF  
```

|Select input records where field1 ends with characters "EEE", and skip all other records. This example has the same effect as:```
SELECTIF
```

It is better to use ENDS\_WITH because the logic text executes faster.

|
|```
IF 
   THEN SELECT
ENDIF
```

|Select input records where field1 begins with "B", contains "C" and ends with "E", and skip all other records.|

**Parent topic:**[Logic text 1: Extract Record Filter](../html/WERLTT100ERecFilter.md)

