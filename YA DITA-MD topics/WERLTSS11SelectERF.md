 

# The purpose of SELECT and SELECTIF in Extract Record Filter

In this logic text, SELECT or SELECTIF define the input records to be included in the extract phase.

If there are **no SELECT, SELECTIF, SKIP or SKIPIF statements** in Extract Record Filter, then **all input records** are selected.

The idea is that you either SELECT or SKIP but you cannot do both in the same logic text. Once you have selected records then all others are skipped. Alternatively, once you skip records then all others are selected.

SELECTIF defines the input records to select based on a condition.

SELECT must always be inside an IF statement, in a THEN or ELSE case. The path through the IF statement decides which records reach the SELECT statement.

Extract Record Filter can have **one SELECTIF** or **one IF that contains one or more SELECT statements**. Once either of these is present, no SKIP or SKIPIF statements are allowed.

[//]: # ( Comment on old image - PLEASE KEEP - <img src="../images/LTZZ_Syntax_legend.gif" alt="Missing image" width="100" height="100"/> )

# Syntax

[//]: # ( Comment on old image - PLEASE KEEP - <img src="../images/LTSSS_SelectIF_01_ERF.gif" alt="Missing image" width="100" height="100"/> )

[//]: # ( Comment on old image - PLEASE KEEP - <img src="../images/LTSSS_IF_Select_01_ERF.gif" alt="Missing image" width="100" height="100"/> )

# Rules for the syntax

-   Extract Record Filter can have one SELECTIF statement or one IF statement that contains one or more SELECT statements. When one SELECTIF or SELECT is present, then no SKIP or SKIPIF statements are allowed.
-   One IF statement can have a SELECT for the THEN or ELSE case. One IF statement can have other IF statements nested inside, which may also have SELECT statements inside. All this counts as one IF statement.

The best way to learn is the examples below. See also the topic "**Syntax: IF Statements in Extract Record Filter**".

A link is under **Related reference** below.

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

**Parent topic:**[Syntax: SELECT, SELECTIF, SKIP and SKIPIF statements](../html/WERLTSS0SelectSkip.md)

