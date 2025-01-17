 

# How do I use BEGINS\_WITH?

BEGINS\_WITH are keywords that are used as string comparison operators. You can check a string begins with certain characters.

For example, a field with "LONDON" begins with the string "L" and "LO" and even "LONDON".

BEGINS\_WITH is an example of string comparisons that return a true or false value that can be part of an IF statement.

BEGINS\_WITH can only be used in **Extract Record Filter** or **Extract Column Assignment** logic text.

[//]: # ( Comment on old image - PLEASE KEEP - <img src="../images/LTZZ_Syntax_legend.gif" alt="Missing image" width="100" height="100"/> )

# Syntax

[//]: # ( Comment on old image - PLEASE KEEP - <img src="../images/LTSStr_BEGINSWITH_01.gif" alt="Missing image" width="100" height="100"/> )

# Rules for the syntax

BEGINS\_WITH can only be used in **Extract Record Filter** or **Extract Column Assignment** logic text.

See also topic "**Rules for all logic text**". A link is under **Related reference** below.

# Examples: BEGINS\_WITH in Extract Record Filter

|Example logic text|Meaning|
|------------------|-------|
|```
SELECTIF
        BEGINS_WITH "BBB")
```

|Select input records where field1 begins with characters "BBB", and skip all other records.|
|```
IF 
   BEGINS_WITH "BBB")
   THEN SELECT
ENDIF
```

|Select input records where field1 begins with characters "BBB", and skip all other records. This example can be written:```
SELECTIF
```

|

# Examples: BEGINS\_WITH in Extract Column Assignment

|Example logic text|Meaning|
|------------------|-------|
|```
IF 
   BEGINS_WITH "BBB")
   THEN COLUMN =
   ELSE COLUMN = " "
ENDIF
```

|If field1 begins with characters "BBB" then set the current column to field1, otherwise set the current column to blank.|

**Parent topic:**[Syntax: string comparison](../html/WERLTSStrAAStrComp.md)

