 

# Examples: SELECTIF in Extract Record Filter

|Example logic text|Meaning|
|------------------|-------|
|```
SELECTIF(CURRENT
         PRIOR
```

|Select only records with unique values for field1. This assumes the input file is sorted into field1 order.|
|```
SELECTIF
```

|Select for output only those records with field2 greater than 1000. Skip all other records. The code at left is a shorthand for:```
IF
   THEN SELECT
ENDIF
```

|
|```
SELECTIF
```

|Select for output only those records with field3 equal to "ABC". Skip all other records.|
|```
SELECTIF(NOT
```

|Select those output records with field3 not equal to "ABC". Skip all other records. This example gives the same result as:```
SKIPIF
```

|
|```
SELECTIF
        
```

|Select for output only those records with field3 equal to "A" or "D". Skip all other records.|
|```
SELECTIF
        
```

|Select for output only those records with field3 equal to "A" and field4 greater than 10. Skip all other records.|
|```
SELECTIF
          >
```

|Select for output only those records with field4 plus field5 is greater than field6. Skip all other records.|
|```
SELECTIF(NOT
```

|Select for output those records with field7 is not equal to all dashes. Skip all other records. This example gives the same result as:```
SKIPIF
```

|
|```
SELECTIF(NOT
         REPEAT("-", 13))
```

|Select for output those records with field7 is not equal to 13 dashes. Skip all other records. This example gives the same result as:```
SKIPIF
```

|
|```
SELECTIF(NOT
```

|Select for output those records with field7 is not equal to hexadecimal FF. Skip all other records. This example gives the same result as:```
SKIPIF
```

|
|```
SELECTIF(ISFOUND
```

|Select all input records where the lookup path Lookup1 successfully finds a target record, and skip all other records.|
|```
SELECTIF(ISFOUND
```

|Select all input records where the lookup path Lookup1 successfully finds a target record using effective date of field7, and skip all other records.|
|```
SELECTIF(ISFOUND
```

|Select all input records where the lookup path Lookup1 successfully finds a target record using symbol SYM set to "A", and skip all other records.|
|```
SELECTIF(ISFOUND
         field7;$SYM1=3,$SYM2=0})
```

|Select all input records where the lookup path Lookup1 successfully finds a target record using effective date of field7 and symbol SYM1 set to 3 and symbol SYM2 set to zero. Skip all other records.|
|```
SELECTIF(ISNOTNULL
```

|Select all input records where field1 does not contain null values, and skip all other records.|
|```
SELECTIF(ISNUMERIC
```

|Select all input records where field2 is numeric, and skip all other records.|
|```
SELECTIF(ISNOTSPACES
```

|Select all input records where field3 is not spaces, and skip all other records.|
|```
SELECTIF(DAYSBETWEEN
          > 7)
```

|Select only records where there are more than 7 days between field1 and field2, and skip all other records.|
|```
SELECTIF
```

|Select input records where field1 begins with characters "BBB", and skip all other records.|
|```
SELECTIF
```

|Select input records where field2 contains characters "CCC", and skip all other records.|
|```
SELECTIF
```

|Select input records where field3 ends with characters "EEE", and skip all other records.|
|```
SELECTIF
```

|Select input records where field4 matches characters "...", and skip all other records.|
|```
SELECTIF
```

|Select input records where field5 is exactly 5 characters starting with "MA", and skip all other records.|
|```
SELECTIF
```

|Select input records where field6 is exactly 6 characters with characters 3 and 4 as "VA", and skip all other records.|
|```
SELECTIF
```

|Select input records where field7 is exactly 6 characters ending in "NA", and skip all other records.|
|```
SELECTIF
```

|Select input records where field8 begins with characters "BBB", and skip all other records. This example has the same effect as:```
SELECTIF
```

It is better to use BEGINS\_WITH because the logic text executes faster.

|
|```
SELECTIF
```

|Select input records where field9 contains characters "CCC", and skip all other records. This example has the same effect as:```
SELECTIF
```

It is better to use CONTAINS because the logic text executes faster.

|
|```
SELECTIF
```

|Select input records where field1 ends with characters "EEE", and skip all other records. This example has the same effect as:```
SELECTIF
```

It is better to use ENDS\_WITH because the logic text executes faster.

|
|```
SELECTIF
```

|Select input records where field2 begins with "B", contains "C" and ends with "E", and skip all other records.|

**Parent topic:**[Logic text 1: Extract Record Filter](../html/WERLTT100ERecFilter.md)

