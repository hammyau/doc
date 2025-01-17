 

# How do I use ENDS\_WITH?

ENDS\_WITH are keywords that are used as string comparison operators. You can check a string ends with certain characters.

For example, a field with "LONDON" begins with the string "N" and "ON" and even "LONDON".

ENDS\_WITH is an example of string comparisons that return a true or false value that can be part of an IF statement.

ENDS\_WITH can only be used in **Extract Record Filter** or **Extract Column Assignment** logic text.

[//]: # ( Comment on old image - PLEASE KEEP - <img src="../images/LTZZ_Syntax_legend.gif" alt="Missing image" width="100" height="100"/> )

# Syntax

[//]: # ( Comment on old image - PLEASE KEEP - <img src="../images/LTSStr_ENDSWITH_01.gif" alt="Missing image" width="100" height="100"/> )

# Rules for the syntax

ENDS\_WITH can only be used in **Extract Record Filter** or **Extract Column Assignment** logic text.

See also topic "**Rules for all logic text**". A link is under **Related reference** below.

# Examples: ENDS\_WITH in Extract Record Filter

|Example logic text|Meaning|
|------------------|-------|
|```
SELECTIF
        ENDS_WITH "EEE")
```

|Select input records where field3 ends with characters "EEE", and skip all other records.|
|```
IF 
   ENDS_WITH "EEE")
   THEN SELECT
ENDIF
```

|Select input records where field3 ends with characters "EEE", and skip all other records. This example can be written:```
SELECTIF
```

|

# Examples: ENDS\_WITH in Extract Column Assignment

|Example logic text|Meaning|
|------------------|-------|
|```
IF 
   ENDS_WITH "EEE")
   THEN COLUMN =
   ELSE COLUMN = " "
ENDIF
```

|If field3 ends with characters "EEE" then set the current column to field3, otherwise set the current column to blank.|

**Parent topic:**[Syntax: string comparison](../html/WERLTSStrAAStrComp.md)

