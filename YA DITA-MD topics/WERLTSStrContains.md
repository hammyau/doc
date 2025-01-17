 

# How do I use CONTAINS?

CONTAINS is a keyword that is used as a string comparison operator. You can check a string contains with certain characters.

For example, a field with "LONDON" contains the string "ON" and "DO" and even "LONDON".

CONTAINS is an example of string comparisons that return a true or false value that can be part of an IF statement.

CONTAINS can only be used in **Extract Record Filter** or **Extract Column Assignment** logic text.

[//]: # ( Comment on old image - PLEASE KEEP - <img src="../images/LTZZ_Syntax_legend.gif" alt="Missing image" width="100" height="100"/> )

# Syntax

[//]: # ( Comment on old image - PLEASE KEEP - <img src="../images/LTSStr_CONTAINS_01.gif" alt="Missing image" width="100" height="100"/> )

# Rules for the syntax

CONTAINS can only be used in **Extract Record Filter** or **Extract Column Assignment** logic text.

See also topic "**Rules for all logic text**". A link is under **Related reference** below.

# Examples: CONTAINS in Extract Record Filter

|Example logic text|Meaning|
|------------------|-------|
|```
SELECTIF
        CONTAINS "CCC")
```

|Select input records where field2 contains characters "CCC", and skip all other records.|
|```
IF 
   CONTAINS "CCC")
   THEN SELECT
ENDIF
```

|Select input records where field2 contains characters "CCC", and skip all other records. This example can be written:```
SELECTIF
```

|

# Examples: CONTAINS in Extract Column Assignment

|Example logic text|Meaning|
|------------------|-------|
|```
IF 
   CONTAINS "CCC")
   THEN COLUMN =
   ELSE COLUMN = " "
ENDIF
```

|If field2 contains characters "CCC" then set the current column to field2, otherwise set the current column to blank.|

**Parent topic:**[Syntax: string comparison](../html/WERLTSStrAAStrComp.md)

