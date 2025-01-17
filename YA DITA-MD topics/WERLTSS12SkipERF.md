 

# The purpose of SKIP and SKIPIF in Extract Record Filter

In this logic text, SKIP or SKIPIF define the input records to be excluded in the extract phase.

If there are **no SELECT, SELECTIF, SKIP or SKIPIF statements** in Extract Record Filter, then **all input records** are selected.

The idea is that you either SELECT or SKIP but you cannot do both in the same logic text. Once you have selected records then all others are skipped. Alternatively, once you skip records then all others are selected.

SKIPIF defines the input records to skip based on a condition.

SKIP must always be inside an IF statement, in a THEN or ELSE case. The path through the IF statement decides which records reach the SKIP statement.

Extract Record Filter can have **one SKIPIF** or **one IF that contains one or more SKIP statements**. Once either of these is present, no SELECT or SELECTIF statements are allowed.

[//]: # ( Comment on old image - PLEASE KEEP - <img src="../images/LTZZ_Syntax_legend.gif" alt="Missing image" width="100" height="100"/> )

# Syntax

[//]: # ( Comment on old image - PLEASE KEEP - <img src="../images/LTSSS_SkipIF_01_ERF.gif" alt="Missing image" width="100" height="100"/> )

[//]: # ( Comment on old image - PLEASE KEEP - <img src="../images/LTSSS_IF_Skip_01_ERF.gif" alt="Missing image" width="100" height="100"/> )

# Rules for the syntax

-   Extract Record Filter can have one SKIPIF statement or one IF statement that contains one or more SKIP statements. When one SKIPIF or SKIP is present, then no SELECT or SELECTIF statements are allowed.
-   One IF statement can have a SKIP for the THEN or ELSE case. One IF statement can have other IF statements nested inside, which may also have SKIP statements inside. All this counts as one IF statement.

The best way to learn is the examples below. See also the topic "**Syntax: IF Statements in Extract Record Filter**".

A link is under **Related reference** below.

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

**Parent topic:**[Syntax: SELECT, SELECTIF, SKIP and SKIPIF statements](../html/WERLTSS0SelectSkip.md)

