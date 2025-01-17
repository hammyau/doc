 

|Rules|Notes|
|-----|-----|
|**Extra blanks between keywords and expressions** have no effect.|For example, theseÂ IF statements are all the same:```
IF 
  

IF 
    COLUMN =

IF
  
           =
           
                     THEN
                         COLUMN
                          =
                         
                              ENDIF

IF 
    COLUMN =
ENDIF

IF 
   THEN COLUMN  = 
ENDIF

```

**WARNING: Extra blanks change text strings**, for example "ABC" and "A B C" are different strings.

|
|Â |Â |
|Logic text can continue on the next line. A backslash \(\\\) is optional at line end.|In previous versions of SAFR, a backslash \(\\\) was required in order to continue a line of logic text on the next line. This backslash is no longer required. The backslash is still allowed for backwards compatibility. This means the following statements are the same:```
 IF 
    THEN COLUMN =

 IF 
    THEN COLUMN =
          
```

|
|Â |Â |
|The **case of keywords** has no effect.|For example, theseÂ IF statements are all the same:```
 IF 
    THEN COLUMN =
    ELSE COLUMN = COL.2 ENDIF

if 
   then column =
   else column = col.2 endif

If 
    Then Column =
    Else Column = Col.2 Endif                          
```

**WARNING: Case changes text strings**, for example "ABC" and "abc" are different strings.

|
|Â |Â |
|**After a single quote** everything on that line is a **comment**|Examples are: ```
 ' Make col the larger of field1 & col.2
IF 
   THEN COLUMN =
COLUMN =
   
```

**WARNING: comments to the left of keywords result in hiding the keywords**, for example:

```
 IF 
    COLUMN =
' This comment hides keyword:     ENDIF
```

|
|Â |Â |
|Use **curly brackets 
{shipping_date}
{product_category}
{CA_Sales_2009_Logical_File}
{Products_Logical_File}
{Products_USA_File}
{Lookup_Sales_to_Product_Category}
```

|

# Keyboard shortcuts for all logic text screens

See topic "**What are the keyboard shortcuts?**"

A link to this topic is under **Related reference** below.

**Parent topic:**[Logic text 1: Extract Record Filter](../html/WERLTT100ERecFilter.md)

**Parent topic:**[Logic text 2: Extract Column Assignment](../html/WERLTT200EColAssign.md)

**Parent topic:**[Logic text 3: Format Column Calculations](../html/WERLTT300FColCalcs.md)

**Parent topic:**[Logic text 4: Format Record Filter](../html/WERLTT400FRecFilter.md)

**Parent topic:**[Logic text: syntax](../html/WERLTSAAASyntax.md)

