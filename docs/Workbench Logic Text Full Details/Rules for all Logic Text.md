---
layout: default
title: "Rules for all Logic Text"
parent: Workbench Logic Text Full Details

nav_order: 99
---
# Rules for all logic text 
{: .no_toc}
TABLE OF CONTENTS 
1. TOC
{:toc}  

# Rule 1 - Extra blanks
  
|Rule 1|Notes|
|-----|-----|
|**Extra blanks between keywords<br> and expressions** have no effect.|For example, these IF statements are all the same:<br> <br>IF ({field1}={field2}) THEN COLUMN=<br>&nbsp;&nbsp;&nbsp;{field1} ENDIF<br><br>IF ({field1} = {field2}) THEN<br>&nbsp;&nbsp;&nbsp;COLUMN = {field1} ENDIF<br><br>IF<br>&nbsp;&nbsp;({field1}<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;=<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;{field2})<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;THEN<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;COLUMN<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;=<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;{field1}<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;ENDIF<br><br>IF ({field1} = {field2})THEN<br>&nbsp;&nbsp;&nbsp;&nbsp;COLUMN = {field1}<br>ENDIF<br><br>IF ({field1} = {field2})<br>&nbsp;&nbsp;&nbsp;THEN COLUMN&nbsp; = &nbsp;{field1}<br>ENDIF<br><br>**WARNING: Extra blanks change text strings**,<br>for example "ABC" and "A B C" are different strings.<br>|
  
# Rule 2 - Continue on next line
  
|Rule 2|Notes|
|-----|-----|
|**Logic text can continue<br> on the next line.**<br> A backslash \(\\) is<br> optional at line end.|In previous versions of SAFR, a backslash \(\\) was required in order to continue a line<br>of logic text on the next line. This backslash is no longer required.<br>The backslash is still allowed for backwards compatibility.<br>This means the following statements are the same:<br><br> IF ({FIELD1} >= 2)\ <br>&nbsp;&nbsp;&nbsp;&nbsp;THEN COLUMN = {FIELD1} ENDIF<br><br>IF ({FIELD1} >= 2) <br>&nbsp;&nbsp;&nbsp;&nbsp;THEN COLUMN = {FIELD1} ENDIF<br>|
  
# Rule 3 - Case of keywords has no effect
  
|Rule 3|Notes|
|-----|-----|
|The **case of keywords**<br> has no effect.|For example, these IF statements are all the same:<br> <br>IF ({FIELD1} >= COL.2)<br>    THEN COLUMN = {FIELD1}<br>    ELSE COLUMN = COL.2 ENDIF<br>  <br>if ({field1} >= col.2)<br>   then column = {field1}<br>   else column = col.2 endif<br>  <br>If ({Field1} >= Col.2)<br>    Then Column = {Field1}<br>    Else Column = Col.2 Endif<br>  <br>**WARNING: Case changes text strings**,<br> for example "ABC" and "abc" are different strings.<br>  <br>|
  
# Rule 4 - Single quote is line comment
  
|Rule 4|Notes|
|-----|-----|
|**After a single quote**<br> everything on that line<br> is a **comment**|Examples are:<br> ' Make col the larger of field1 & col.2<br>COLUMN = COL.2  ' Rest is comment (OK).<br>IF ({FIELD1} > COL.2)<br>&nbsp;&nbsp;&nbsp;&nbsp;THEN COLUMN = {FIELD1} ENDIF<br><br>  **WARNING: comments to the left of keywords<br> result in hiding the keywords**, for example:<br> IF ({field1} = {field2})THEN<br>&nbsp;&nbsp;&nbsp;&nbsp;COLUMN = {field1}<br>' This comment hides keyword:&nbsp;&nbsp;&nbsp;&nbsp;ENDIF<br>  <br>|
  
# Rule 5 - Input fields in curly brackets
  
|Rule 5|Notes|
|-----|-----|
|Use **curly brackets \{ \}** to enclose<br> **input fields** or names of metadata<br> from the SAFR Workbench<br> \(such as a lookup path,<br> logical file, physical file\).|Examples are:<br>&nbsp;&nbsp;&nbsp;&nbsp;{shipping_date}<br>&nbsp;&nbsp;&nbsp;&nbsp;{product_category}<br>&nbsp;&nbsp;&nbsp;&nbsp;{CA_Sales_2009_Logical_File}<br>&nbsp;&nbsp;&nbsp;&nbsp;{Products_Logical_File}<br>&nbsp;&nbsp;&nbsp;&nbsp;{Products_USA_File}<br>&nbsp;&nbsp;&nbsp;&nbsp;{Lookup_Sales_to_Product_Category}<br>|
  
  
# Keyboard shortcuts for logic text screens 
  
See topic [Keyboard Shortcuts Logic Text](Keyboard Shortcuts Logic Text)
  
