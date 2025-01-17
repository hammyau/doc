 

# Examples: WRITE in Extract Record Filter

|Example logic text|Meaning|
|------------------|-------|
|```
' This WRITE statement is before
' any SELECT or SKIP.
WRITE (SOURCE = INPUT,
       USEREXIT =
```

|This WRITE sends all input records to the UserExit Routine called Backup.|
|Â |Â |
|```
' This WRITE statement is before
' any SELECT or SKIP.
WRITE (SOURCE = INPUT,
       USEREXIT =
```

|This WRITE decrypts all input records and puts the results "in place" so that the input records are processed later in the extract phase.|
|Â |Â |
|```
SELECTIF (
            = "ABC" )
WRITE (SOURCE = INPUT,
       DEST = FILE =
```

|The WRITE sends only input records with product\_code = "ABC" to the logical file "All\_ABC".|
|Â |Â |
|```
IF (
   THEN SELECT
ENDIF
WRITE (SOURCE = INPUT,
       DEST = FILE =
 
```

|This example has the same effect as the previous example. Ensure the IF statement is purely for SELECT statements only.|

**Parent topic:**[Logic text 1: Extract Record Filter](../html/WERLTT100ERecFilter.md)

