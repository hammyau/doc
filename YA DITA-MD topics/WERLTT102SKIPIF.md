 

# Examples: SKIPIF in Extract Record Filter

|Example logic text|Meaning|
|------------------|-------|
|```
SKIPIF(CURRENT
       PRIOR
```

|Skip records where the new field4 value is the same as the previous field4. This assumes the input file is sorted into field4 order. This selects only the input records where field4 is a new value \(compared to the previous record\).|
|```
SKIPIF
```

|Skip for output those records with field1 greater than 1000. Select all other records. The code at left is a shorthand for:```
IF 
   THEN SKIP
ENDIF
```

|
|```
SKIPIF
```

|Skip for output those records with field2 equal to "ABC". Select all other records.|
|```
SKIPIF(NOT
```

|Skip those output records with field2 not equal to "ABC". Select all other records. This example gives the same result as:```
SELECTIF
```

|
|```
SKIPIF
```

|Skip for output those records with field3 equal to "A" or "D". Select all other records.|
|```
SKIPIF
```

|Skip for output those records with field4 equal to "A" and field5 greater than 10. Select all other records.|
|```
SKIPIF
```

|Skip for output those records with field6 times 2 is greater than field8 plus 5. Select all other records.|
|```
SKIPIF

```

|Skip for output those records with field6 is equal to all dashes. Select all other records.|
|```
SKIPIF
```

|Skip for output those records with field6 is equal to 13 dashes. Select all other records.|
|```
SKIPIF
```

|Skip for output those records with field6 is equal to hexadecimal FF. Select all other records.|
|```
SKIPIF(ISNOTFOUND
```

|Skip all input records where the lookup path Lookup2 does not successfully find a target record, and select all other records.|
|```
SKIPIF(ISNOTFOUND
```

|Skip all input records where the lookup path Lookup2 does not successfully finds a target record using effective date of field7, and select all other records.|
|```
SKIPIF(ISNOTFOUND
```

|Skip all input records where the lookup path Lookup2 using symbol SYM set to "A" does not successfully finds a target record, and select all other records.|
|```
SKIPIF(ISNOTFOUND
                  field8;$SYM1=3,$SYM2=0})
```

|Skip all input records where the lookup path Lookup2 using effective date of field8 and symbol SYM1 set to 3 and symbol SYM2 set to zero does not successfully finds a target record. Select all other records.|
|```
SKIPIF(ISNULL
```

|Skip all input records where field1 contains null values, and select all other records.|
|```
SKIPIF(ISNOTNUMERIC
```

|Skip all input records where field2 is not numeric, and select all other records.|
|```
SKIPIF(ISSPACES
```

|Skip all input records where field3 is spaces, and select all other records.|
|```
SKIPIF(DAYSBETWEEN
        > 7)   
```

|Skip only records where there are more than 7 days between field4 and field5, and select all other records.|
|```
SKIPIF
```

|Skip input records where field1 begins with characters "BBB", and select all other records.|
|```
SKIPIF
```

|Skip input records where field2 contains characters "CCC", and select all other records.|
|```
SKIPIF
```

|Skip input records where field3 ends with characters "EEE", and select all other records.|
|```
SKIPIF
```

|Skip input records where field4 matches characters "...", and select all other records.|
|```
SKIPIF
```

|Skip input records where field5 is exactly 5 characters starting with "MA", and select all other records.|
|```
SKIPIF
```

|Skip input records where field6 is exactly 6 characters with characters 3 and 4 as "VA", and select all other records.|
|```
SKIPIF
```

|Skip input records where field7 is exactly 6 characters ending in "NA", and select all other records.|
|```
SKIPIF
```

|Skip input records where field8 begins with characters "BBB", and select all other records. This example has the same effect as:```
SKIPIF
```

It is better to use BEGINS\_WITH because the logic text executes faster.

|
|```
SKIPIF
```

|Skip input records where field9 contains characters "CCC", and select all other records. This example has the same effect as:```
SKIPIF
```

It is better to use CONTAINS because the logic text executes faster.

|
|```
SKIPIF
```

|Skip input records where field1 ends with characters "EEE", and select all other records. This example has the same effect as:```
SKIPIF
```

It is better to use ENDS\_WITH because the logic text executes faster.

|
|```
SKIPIF
```

|Skip input records where field2 begins with "B", contains "C" and ends with "E", and select all other records.|

**Parent topic:**[Logic text 1: Extract Record Filter](../html/WERLTT100ERecFilter.md)

