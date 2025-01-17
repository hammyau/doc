 

# The purpose of WRITE in Extract Record Filter

A WRITE in Extract Record Filter is essentially making a copy of input records in a Logical File. You may write all input records, or you may write only the selected input records.

The purpose of these WRITE statements might be:

-   Create an audit trail or backup of input records.
-   Create a trace for debugging purposes

Any records written to extract logical files by these WRITE statements are not processed any further in the extract phase or the format phase. The logical files for the written input records are considered view output files.

The SOURCE parameter of the WRITE statement must be INPUT, and there is no choice of DESTINATION=EXTRACT. Full details of the syntax are below.

[//]: # ( Comment on old image - PLEASE KEEP - <img src="../images/LTZZ_Syntax_legend.gif" alt="Missing image" width="100" height="100"/> )

# Syntax

[//]: # ( Comment on old image - PLEASE KEEP - <img src="../images/LTS_WRITE_01_Stmt.gif" alt="Missing image" width="100" height="100"/> )

[//]: # ( Comment on old image - PLEASE KEEP - <img src="../images/LTS_WRITE_02_Source_1ERF.gif" alt="Missing image" width="100" height="100"/> )

[//]: # ( Comment on old image - PLEASE KEEP - <img src="../images/LTS_WRITE_03_Dest_1ERF.gif" alt="Missing image" width="100" height="100"/> )

[//]: # ( Comment on old image - PLEASE KEEP - <img src="../images/LTS_WRITE_04_Exit.gif" alt="Missing image" width="100" height="100"/> )

[//]: # ( Comment on old image - PLEASE KEEP - <img src="../images/LTS_WRITE_05_Ext_File_Num.gif" alt="Missing image" width="100" height="100"/> )

[//]: # ( Comment on old image - PLEASE KEEP - <img src="../images/LTS_WRITE_06_Names.gif" alt="Missing image" width="100" height="100"/> )

[//]: # ( Comment on old image - PLEASE KEEP - <img src="../images/LTS_WRITE_07_String.gif" alt="Missing image" width="100" height="100"/> )

# Rules for the syntax

-   You can have as many WRITE statements as required in your logic text.
-   If the WRITE is **before** any selects or skips in your Extract Record Filter, then the WRITE covers **all input records.**
-   If the WRITE is **after** any selects or skips in your Extract Record Filter, then the WRITE covers **only selected input records.**
-   Do not include WRITE statements in an IF statement that uses SELECT or SKIP. This means WRITE statements may be before or after \(or both before and after\) any selects or skips.
-   For **Extract Record Filter**, then **SOURCE=INPUT** is a mandatory parameter.
-   **PROCEDURE** and **USEREXIT** are both optional parameters. The WRITE statement can have one or the other **but not both**. If you use a **PROCEDURE** or **USEREXIT** parameter, then the DESTINATION may not be necessary.

See also topic "**Rules for all logic text**". A link is under **Related reference** below.

# What is the difference between PROCEDURE and USEREXIT?

The idea of a procedure is the same as for a user-exit routine.

Both a procedure and a user-exit routine have an executable name on your mainframe. The executable name must conform to mainframe standards, which makes them short and often unfriendly. For example, the executable name might be ABCSYBKUP that performs a backup for the ABC system.

A procedure is the executable name. A user-exit routine allows a longer name to apply to the same executable - for example: "ABC System Backup".

Your WRITE statement can use this parameter:

```
     PROCEDURE
```

If you define a user-exit routine called "ABC System Backup" that points to ABCSYBKUP, then your WRITE statement can use this USEREXIT parameter:

```
     USEREXIT
```

User-exit routines are recommended for all situations like this.

For more, see topic "**User-exit routines overview**". A link is under **Related concepts** below.

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

**Parent topic:**[Syntax: WRITE statements](../html/WERLTSWrite0.md)

