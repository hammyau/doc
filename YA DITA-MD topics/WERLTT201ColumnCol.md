 

# Examples: COLUMN and COL.nnn in Extract Column Assignment

In all the following examples, **COLUMN can be replaced by COL.nnn**, for example COL.3. You can set the value of any COL.nnn from any other column. You can create multiple COL.nnn statements in Extract Column Assignment logic text.

|Example logic text|Meaning|
|------------------|-------|
|```
COLUMN = 
COL.27 =
COL.28 =
COL.29 = 0
COL.30 = "ABC"
```

|Set the current column to field2 divided by field1 all multiplied by 100. Set column 27 to field1 times field26. Set column 28 to field14 plus field1. Set column 29 to zero. Set column 30 to "ABC".|
|```
COLUMN = ALL("-")
```

|Set the current column to all dashes.|
|```
COLUMN = REPEAT("-", 13)
```

|Set the current column to 13 dashes.|
|```
COLUMN = "\xFF"
```

|Set the current column to hexadecimal FF.|
|```
COLUMN =
```

|Set the current column to Field3 found by lookup path Lookup1|
|```
COLUMN =
```

|Set the current column to Field3 found by lookup path Lookup1 using effective date of field7.|
|```
COLUMN =
```

|Set the current column to Field3 found by lookup path Lookup1 using symbol SYM set to "A".|
|```
COLUMN =
```

|Set the current column to Field3 found by lookup path Lookup1 using effective date of field7 and symbols SYM1 set to 3 and SYM2 set to zero.|
|```
COLUMN = DAYSBETWEEN
```

|Set the current column to the days between the transaction date and the shipping date.|

**Parent topic:**[Logic text 2: Extract Column Assignment](../html/WERLTT200EColAssign.md)

