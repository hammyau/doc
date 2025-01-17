 

# How do I use lookup paths?

A lookup path is a method to use one logical file to lookup a record in another logical file. For an introduction, see topic "**Lookup paths overview**". A link to that topic is under **Related concepts** below.

In logic text, lookup paths are only used in the extract phase, where you can use lookup paths to provide values for columns in view data. You can also use the ISFOUND and ISNOTFOUND functions to check if the lookup path is successful in each particular case.

Lookup paths are used in the format phase only in the Sort Key Title field, which is part of the definition of a sort column in a view. There is no logic text syntax for lookup paths in the format phase.

[//]: # ( Comment on old image - PLEASE KEEP - <img src="../images/LTZZ_Syntax_legend.gif" alt="Missing image" width="100" height="100"/> )

# Syntax

[//]: # ( Comment on old image - PLEASE KEEP - <img src="../images/LTS_Lookups_01.gif" alt="Missing image" width="100" height="100"/> )

[//]: # ( Comment on old image - PLEASE KEEP - <img src="../images/LTS_Lookups_02.gif" alt="Missing image" width="100" height="100"/> )

[//]: # ( Comment on old image - PLEASE KEEP - <img src="../images/LTS_Lookups_03.gif" alt="Missing image" width="100" height="100"/> )

[//]: # ( Comment on old image - PLEASE KEEP - <img src="../images/LTS_Lookups_04.gif" alt="Missing image" width="100" height="100"/> )

# Rules for the syntax

Lookups can only be used in **Extract Record Filter** or **Extract Column Assignment** logic text.

See also topic "**Rules for all logic text**". A link is under **Related reference** below.

# Examples: lookup paths in Extract Record Filter

|Example logic text|Meaning|
|------------------|-------|
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

|Select all input records where the lookup path Lookup3 successfully finds a target field of Field4, and skip all other records. This example is the same as:```
SELECTIF(ISFOUND
```

|
|```
IF ISFOUND
   THEN SELECT
ENDIF
```

|Select all input records where the lookup path Lookup2 successfully finds a target record using effective date of field7, and skip all other records. This example is the same as:```
SELECTIF(ISFOUND
```

|
|```
IF ISFOUND
   THEN SELECT
ENDIF
```

|Select all input records where the lookup path Lookup2 successfully finds a target record using symbol SYM set to "ABC", and skip all other records. This example is the same as:```
SELECTIF(ISFOUND
```

|
|```
IF ISFOUND
            field7;$SYM1=3,$SYM2=0})
   THEN SELECT
ENDIF
```

|Select all input records where the lookup path Lookup5 successfully finds a target record using effective date of field7 and symbol SYM1 set to 3 and symbol SYM2 set to zero. Skip all other records. This example is the same as:```
SELECTIF(ISFOUND
                 field7;$SYM1=3,$SYM2=0})
```

|
|```
IF ISNOTFOUND
   THEN SKIP
ENDIF
```

|Skip all input records where the lookup path Lookup1 does not successfully find a target record, and select all other records. This example is the same as:```
SKIPIF(ISNOTFOUND
```

|
|```
IF ISNOTFOUND
   THEN SKIP
ENDIF
```

|Skip all input records where the lookup path Lookup1 does not successfully find a target record using effective date of field7, and select all other records. This example is the same as:```
SKIPIF(ISNOTFOUND
```

|
|```
IF ISNOTFOUND
   THEN SKIP
ENDIF
```

|Skip all input records where the lookup path Lookup5 does not successfully find a target record using symbol SYM1 set to "ABC", and select all other records. This example is the same as:```
SKIPIF(ISNOTFOUND
```

|
|```
IF ISNOTFOUND
              field7;$SYM1=3,$SYM2=0})
   THEN SKIP
ENDIF
```

|Skip all input records where the lookup path Lookup2 does not successfully find a target record using effective date of field7 and symbol SYM1 set to 3 and symbol SYM2 set to zero. Select all other records. This example is the same as:```
SKIPIF(ISNOTFOUND
                  field7;$SYM1=3,$SYM2=0})
```

|

# Examples: lookup paths in Extract Column Assignment

|Example logic text|Meaning|
|------------------|-------|
|```
COLUMN =
```

|Set the current column using lookup path Lookup1 to provide Field2 in the target logical record.|
|```
COLUMN =
```

|Set the current column using lookup path Lookup1 to provide Field2 in the target logical record using effective date of Field7.|
|```
COLUMN =
```

|Set the current column using lookup path Lookup1 to provide Field2 in the target logical record using symbol SYM set to 'ABC".|
|```
COLUMN =
          Field7;$SYM1=3,$SYM2=0}
```

|Set the current column using lookup path Lookup3 to provide Field4 in the target logical record using effective date of Field7 and symbols SYM1 set to 3 and SYM2 set to zero.|
|```
IF ISFOUND
   THEN COLUMN =
                  ;$SYM="A"}
   ELSE COLUMN = 0
ENDIF
```

|If lookup path Lookup4 successfully finds a value using symbol SYM set to "A", then set the current column to that lookup field, otherwise set the current column to zero.|

**Parent topic:**[Logic text: syntax](../html/WERLTSAAASyntax.md)

