 

# What is the purpose of this?

A WRITE in Extract Column Assignment has many options:

-   Write a full **copy of the selected input record** to a view output file \(SOURCE=INPUT, DEST=FILE=LogicalFile\).
-   Write **all columns up to that point to a logical file** that is a view output file \(SOURCE=DATA, DEST=FILE=LogicalFile\)
-   Write **all columns up to that point to an extract work file \(EXT file\)** that can be processed in the format phase \(SOURCE=VIEW, DEST=EXT=number\). The number for the EXT files must be within a limit \(see below\). An EXT file is optimized for the format phase and so the structure of an EXT file is different from what is specified in the view. See your IBM representative if you have questions about the structure of an EXT file.
-   Write records to s**ome other location** determined by a **procedure or user-exit routine**.
-   Some combination of the above.

Only the EXT files are processed in the format phase. All other records written in the above choices are written to view output files and not processed any further after the extract phase.

These WRITE options provide great flexibility in view processing. For more information, see "**Extract Phase overview**". A link is under **Related concepts** below.

[//]: # ( Comment on old image - PLEASE KEEP - <img src="../images/LTZZ_Syntax_legend.gif" alt="Missing image" width="100" height="100"/> )

# Syntax

[//]: # ( Comment on old image - PLEASE KEEP - <img src="../images/LTS_WRITE_01_Stmt.gif" alt="Missing image" width="100" height="100"/> )

[//]: # ( Comment on old image - PLEASE KEEP - <img src="../images/LTS_WRITE_02_Source_2ECA.gif" alt="Missing image" width="100" height="100"/> )

[//]: # ( Comment on old image - PLEASE KEEP - <img src="../images/LTS_WRITE_03_Dest_2ECA.gif" alt="Missing image" width="100" height="100"/> )

[//]: # ( Comment on old image - PLEASE KEEP - <img src="../images/LTS_WRITE_04_Exit.gif" alt="Missing image" width="100" height="100"/> )

[//]: # ( Comment on old image - PLEASE KEEP - <img src="../images/LTS_WRITE_05_Ext_File_Num.gif" alt="Missing image" width="100" height="100"/> )

[//]: # ( Comment on old image - PLEASE KEEP - <img src="../images/LTS_WRITE_06_Names.gif" alt="Missing image" width="100" height="100"/> )

[//]: # ( Comment on old image - PLEASE KEEP - <img src="../images/LTS_WRITE_07_String.gif" alt="Missing image" width="100" height="100"/> )

# Rules

-   You can have as many WRITE statements as required in your logic text for a column. The WRITE statements can be positioned anywhere a statement is valid in your logic text.
-   If you do not put a SOURCE parameter then **VIEW** is assumed.
-   For SOURCE = VIEW or SOURCE = DATA, the WRITE includes **only the columns up to that point \(the current column\)**. If the WRITE is not in the last column then the record created is truncated compared to all the columns in the view.
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

# Examples: IF with WRITE in Extract Column Assignment

|Example logic text|Meaning|
|------------------|-------|
|```
IF (ISNUMERIC
   
   (ISNOTSPACE
   THEN WRITE (SOURCE=DATA,
               USEREXIT
ENDIF 
```

|If field4 is numeric and field5 is greater than field6 times 10 and field7 is not spaces, then call the user-exit routine DB2\_Update for the columns up to the current point. This effectively does a writes to a DB2 table the columns in that record up to the current point.|
|Â |Â |
|```
IF (ISNOTNULL
   
   THEN WRITE (SOURCE=INPUT,
               DEST=FILE=
                 
ENDIF 
```

|If field3 is not nulls and field2 equals field1 plus field 5 then write the entire input record to LogicalFile3. All columns in the input record are included, no matter what column contains this logic text.|
|Â |Â |
|```
IF (DAYSBETWEEN
     > 10) AND
   (ISFOUND
   THEN WRITE (SOURCE=VIEW,
               DEST=EXT=03)
ENDIF 
```

|If field12 and field15 are more than 10 days apart and the lookup path Lookup3 works with symbol SYM set to "A", then write the columns up to the current point to extract work file \(EXT\) 3. This assumes that the control record for this environment has a Maximum Extract File Number that is at least 3, or any overwrite of the VDP has also set this parameter to at least 3.|

**Parent topic:**[Syntax: WRITE statements](../html/WERLTSWrite0.md)

