﻿---
layout: default
title: "IF statements (ERF)"
nav_order: 1
parent: IF statements
grand_parent: Workbench Logic Text Full Details
---
# IF statements (ERF)
{: .no_toc}
TABLE OF CONTENTS 
1. TOC
{:toc}  
 


# How do I use IF statements in ERF? 

IF statements can be part of any logic text. An IF statement allows a condition to control if one or more statements are executed.

Even though IF statements are allowed in all logic text, the statements that can be called in an IF statement change depending on the particular logic text.

An IF statement can call another IF statement - this is called "nesting" of IF statements, and is allowed in all logic text.

The syntax details of an IF statement in **Extract Record Filtger** are shown below.

![(Syntax Legend)](../../images/LTZZ_Syntax_legend.gif )

# Syntax 

![Function IF ERF 01](../../images/LTS_IF_1ERF_01.gif)

![Function IF ERF 02](../../images/LTS_IF_1ERF_02.gif)

![Function IF ERF 03](../../images/LTS_IF_1ERF_03.gif)

![Function IF ERF 04](../../images/LTS_IF_1ERF_04.gif)

![Function IF ERF 05](../../images/LTS_IF_1ERF_05.gif)

![Function IF ERF 06](../../images/LTS_IF_1ERF_06.gif)

![Function IF ERF 07](../../images/LTS_IF_1ERF_07.gif)

![Function IF ERF 08](../../images/LTS_IF_1ERF_08.gif)

![Function IF ERF 09](../../images/LTS_IF_1ERF_09.gif)

![Function IF ERF 10](../../images/LTS_IF_1ERF_10.gif)


# Rules for the syntax 

See also topic: [Rules for all Logic Text](../Rules for all Logic Text) 


# Examples: IF with SELECT (ERF)

|Example logic text|Meaning|
|------------------|-------|
|**IF (CURRENT({field1})<br>&nbsp;&nbsp;&nbsp;&nbsp;<> PRIOR({field1}))<br>&nbsp;&nbsp;&nbsp;&nbsp;THEN SELECT<br>ENDIF**|Select for output records where field1 changes from the previous record.<br>This assumes the input file is sorted into field1 order.<br>This example can also be written:<br>&nbsp;&nbsp;&nbsp;&nbsp;**SELECTIF(CURRENT({field1}) <> PRIOR({field1}))**|
|**IF ({field3} > 1000)<br>&nbsp;&nbsp;&nbsp;&nbsp;THEN SELECT<br>ENDIF**|Select for output only those records with<br>field3 greater than 1000. Skip all other records.<br>This example can also be written:<br>&nbsp;&nbsp;&nbsp;&nbsp;**SELECTIF({field3} > 1000)**|
|**IF ({field2} = 'ABC')<br>&nbsp;&nbsp;&nbsp;&nbsp;THEN SELECT<br>ENDIF**|Select for output only those records with<br>field2 equal to "ABC". Skip all other records.<br>This example can also be written:<br>&nbsp;&nbsp;&nbsp;&nbsp;**SELECTIF({field2} = "ABC")**|
|**IF NOT ({field2} =<br>&nbsp;&nbsp;&nbsp;&nbsp; 'ABC')<br>&nbsp;&nbsp;&nbsp;&nbsp;THEN SELECT<br>ENDIF**|Select for output only those records with<br> field2 not equal to "ABC". Skip all other records.<br>This example can also be written:<br>&nbsp;&nbsp;&nbsp;&nbsp;**SKIPIF({field2} = "ABC")**|
|**IF ({field2} = "ABC") OR<br>&nbsp;&nbsp;&nbsp;&nbsp;({field2} = "DEF")<br>&nbsp;&nbsp;&nbsp;&nbsp;THEN SELECT<br>ENDIF**|Select for output only those records with<br>field2 equal to "ABC" or "DEF". Skip all other records.|
|**IF ({field2} = "ABC") AND<br>&nbsp;&nbsp;&nbsp;&nbsp;({field3} > 1000)<br>&nbsp;&nbsp;&nbsp;&nbsp;THEN SELECT<br>ENDIF**|Select for output only those records with<br>field2 equal to "ABC" and field3 greater than 1000.<br>Skip all other records.|
|**IF ({field3} + {field4} ><br>&nbsp;&nbsp;&nbsp;&nbsp;{field5} \* 100)<br>&nbsp;&nbsp;&nbsp;&nbsp;THEN SELECT<br>ENDIF**|Select for output only those records with<br>field3 plus field4 is greater than field5 times 100.<br>Skip all other records.|
|**IF NOT ({field1} = ALL("-"))<br>&nbsp;&nbsp;&nbsp;&nbsp;THEN SELECT<br>ENDIF**|Select for output those records with field1 is not equal<br> to all dashes. Skip all other records.<br>This example gives the same result as:<br>&nbsp;&nbsp;&nbsp;&nbsp;**SKIPIF({field1} = ALL("-"))**|
|**IF NOT ({field7} =<br>&nbsp;&nbsp;&nbsp;&nbsp;REPEAT("-", 13))<br>&nbsp;&nbsp;&nbsp;&nbsp;THEN SELECT<br>ENDIF**|Select for output those records with field7 is not equal<br>to 13 dashes. This example is the same as:<br>&nbsp;&nbsp;&nbsp;&nbsp;**SKIPIF({field7} = REPEAT("-", 13))**|
|**IF ({field6} = "\xFF")<br>&nbsp;&nbsp;&nbsp;&nbsp;THEN SELECT<br>ENDIF**|Select for output only those records with<br> field6 equal to hexadecimal FF. Skip all other records.|
|**IF ({field2} = "ABC") AND<br>&nbsp;&nbsp;&nbsp;&nbsp;({field3} > 10)<br>THEN SELECT<br>ELSE IF ({field2} = "DEF")<br>&nbsp;&nbsp;&nbsp;&nbsp;THEN SELECT<br>&nbsp;&nbsp;&nbsp;&nbsp;ELSE IF ({field2} = "GHI")<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;THEN SELECT<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;ENDIF<br>&nbsp;&nbsp;&nbsp;&nbsp;ENDIF<br>ENDIF**|Select for output those records with field2 equal to "ABC" and<br>field3 greater than 10. In addition, select for output those records<br>with field2 equal to "DEF". In addition, select for output those records<br>with field2 equal to "GHI". Skip all other records.<br>Notice that the logic text at left counts as only one IF statement,<br>because the extra IF statements are nested inside the first.<br>The code at left can also be written as below<br>\(note how brackets control the evaluation of the conditions\)<br>**IF ({field2} = "ABC" AND<br>&nbsp;&nbsp;&nbsp;&nbsp;{field3} > 10)&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;OR<br>&nbsp;&nbsp;&nbsp;&nbsp;({field2} = "DEF")&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;OR<br>&nbsp;&nbsp;&nbsp;&nbsp;({field2} = "GHI")<br>&nbsp;&nbsp;&nbsp;&nbsp;THEN SELECT<br>ENDIF**|
|**IF ({field2} = "ABC") AND<br>&nbsp;&nbsp;&nbsp;&nbsp;({field3} > 10)<br>THEN IF ({field4} + {field5}<br>&nbsp;&nbsp;&nbsp;&nbsp;> {field6}<br>&nbsp;&nbsp;&nbsp;&nbsp;THEN SELECT<br>&nbsp;&nbsp;&nbsp;&nbsp;ELSE IF ({field7} = 0")<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;THEN SELECT<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;ENDIF<br>&nbsp;&nbsp;&nbsp;&nbsp;ENDIF<br>ENDIF**|Consider those records with field2 equal to "ABC"<br>and field3 greater than 10.  Of the considered records,<br>select for output those records with field4 plus field5<br>greater then field6. Of the considered records not yet selected,<br>select also for output those records with field7 equal to zero.<br>Skip all other records.<br>Notice that the logic text at left counts as only one IF statement,<br>because the extra IF statements are nested inside the first.<br>The code at left can also be written as below<br>\(note how brackets control the evaluation of the conditions\)<br>**IF ({field2} = "ABC" AND<br>&nbsp;&nbsp;&nbsp;&nbsp;{field3} > 10)&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;AND<br>&nbsp;&nbsp;&nbsp;&nbsp;(({field4} + {field5}<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;> {field6})&nbsp;&nbsp;&nbsp;&nbsp;OR<br>&nbsp;&nbsp;&nbsp;&nbsp;({field7} = 0))<br>&nbsp;&nbsp;&nbsp;&nbsp;THEN SELECT<br>ENDIF**|
|**IF ISFOUND({Lookup3})<br>&nbsp;&nbsp;&nbsp;&nbsp;THEN SELECT<br>ENDIF**|Select all input records where lookup path Lookup3 successfully<br>finds a target record, and skip all other records.<br>This example is the same as:<br>&nbsp;&nbsp;&nbsp;&nbsp;**SELECTIF(ISFOUND({Lookup3}))**|
|**IF ISFOUND({Lookup3,field7})<br>&nbsp;&nbsp;&nbsp;&nbsp;THEN SELECT<br>ENDIF**|Select all input records where lookup path Lookup3 successfully<br>finds a target record using effective date of field7,<br>and skip all other records. This example is the same as:<br>&nbsp;&nbsp;&nbsp;&nbsp;**SELECTIF(ISFOUND({Lookup3,field7}))**|
|**IF ISFOUND({Lookup3;$SYM="A"})<br>&nbsp;&nbsp;&nbsp;&nbsp;THEN SELECT<br>ENDIF**|Select all input records where lookup path Lookup3 successfully<br>finds a target record using symbol SYM set to "A",<br>and skip all other records. This example is the same as:<br>&nbsp;&nbsp;&nbsp;&nbsp;**SELECTIF(ISFOUND({Lookup3;$SYM="A"}))**|
|**IF ISFOUND({Lookup3,<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;field7;$SYM1=3,$SYM2=0})<br>&nbsp;&nbsp;&nbsp;&nbsp;THEN SELECT<br>ENDIF**|Select all input records where lookup path Lookup3 successfully<br>finds a target record using effective date of field7<br>and symbol SYM1 set to 3 and symbol SYM2 set to zero.<br>Skip all other records. This example is the same as:<br>&nbsp;&nbsp;&nbsp;&nbsp;**SELECTIF(ISFOUND({Lookup3,<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;field7;$SYM1=3,$SYM2=0}))**|


# Examples: IF with SKIP (ERF)

|Example logic text|Meaning|
|------------------|-------|
|**IF (CURRENT({field1})<br>&nbsp;&nbsp;&nbsp;&nbsp;= PRIOR({field1}))<br>&nbsp;&nbsp;&nbsp;&nbsp;THEN SKIP<br>ENDIF**|Skip records where field1 is the same as the previous record.<br>This assumes the input file is sorted into field1 order.<br>This example can also be written:<br>&nbsp;&nbsp;&nbsp;&nbsp;**SKIPIF(CURRENT({field1}) = PRIOR({field1}))**|
|**IF ({field3} > 1000)<br>&nbsp;&nbsp;&nbsp;&nbsp;THEN SKIP<br>ENDIF**|Skip for output those records with field3 greater than 1000.<br>Select all other records.<br>This example can also be written:<br>&nbsp;&nbsp;&nbsp;&nbsp;**SKIPIF({field3} > 1000)**|
|**IF ({field2} = 'ABC')<br>&nbsp;&nbsp;&nbsp;&nbsp;THEN SKIP<br>ENDIF**|Skip for output those records with<br>field2 equal to "ABC". Select all other records.<br>This example can also be written:<br>&nbsp;&nbsp;&nbsp;&nbsp;**SKIPIF({field2} = "ABC")**|
|**IF NOT ({field2} = 'ABC')<br>&nbsp;&nbsp;&nbsp;&nbsp;THEN SKIP<br>ENDIF**|Skip for output those records with<br>field2 not equal to "ABC". Select all other records.<br>This example can also be written:<br>&nbsp;&nbsp;&nbsp;&nbsp;**SELECTIF({field2} = "ABC")**|
|**IF ({field2} = "A") OR<br>&nbsp;&nbsp;&nbsp;&nbsp;({field2} = "D")<br>&nbsp;&nbsp;&nbsp;&nbsp;THEN SKIP<br>ENDIF**|Skip for output those records with<br>field2 equal to "A" or "D".<br>Select all other records.|
|**IF ({field2} = "A") AND<br>&nbsp;&nbsp;&nbsp;&nbsp;({field3} > 10)<br>&nbsp;&nbsp;&nbsp;&nbsp;THEN SKIP<br>ENDIF**|Skip for output those records with<br>field2 equal to "A" and field3 greater than 10.<br>Select all other records.|
|**IF ({field3} + {field4} ><br>&nbsp;&nbsp;&nbsp;&nbsp;{field5} \* 100)<br>&nbsp;&nbsp;&nbsp;&nbsp;THEN SKIP<br>ENDIF**|Skip for output those records with<br>field3 plus field4 greater than field5 times 100.<br>Select all other records.|
|**IF ({field2} = ALL("-"))<br>&nbsp;&nbsp;&nbsp;&nbsp;THEN SKIP<br>ENDIF**|Skip for output those records with field2 is equal to all dashes.<br> Select all other records.<br>This example gives the same result as:<br>&nbsp;&nbsp;&nbsp;&nbsp;**SKIPIF({field2} = ALL("-"))**|
|**IF ({field8} =<br>&nbsp;&nbsp;&nbsp;&nbsp;REPEAT("-", 13))<br>&nbsp;&nbsp;&nbsp;&nbsp;THEN SKIP<br>ENDIF**|Skip for output those records with field8 is equal<br>to 13 dashes. Select all other records.<br>This example is the same as:<br>&nbsp;&nbsp;&nbsp;&nbsp;**SKIPIF({field8} = REPEAT("-", 13))**|
|**IF ({field6} = "\xFF")<br>&nbsp;&nbsp;&nbsp;&nbsp;THEN SKIP<br>ENDIF**|Skip for output those records with<br>field6 equal to hexadecimal FF. Select all other records.<br>This example is the same as:<br>&nbsp;&nbsp;&nbsp;&nbsp;**SKIPIF({field6} = "\xFF")**|
|**IF ({field2} = "A") AND<br>&nbsp;&nbsp;&nbsp;&nbsp;({field3} > 10)<br>THEN SKIP<br>ELSE IF ({field2} = "D")<br>&nbsp;&nbsp;&nbsp;&nbsp;THEN SKIP<br>&nbsp;&nbsp;&nbsp;&nbsp;ELSE IF ({field2} = "G")<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;THEN SKIP<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;ENDIF<br>&nbsp;&nbsp;&nbsp;&nbsp;ENDIF<br>ENDIF**|Skip for output those records with field2 equal to "A" and<br>field3 greater than 10. In addition, skip for output those records<br>with field2 equal to "D". In addition, skip for output those records<br>with field2 equal to "G". Select all other records.<br>Notice that the logic text at left counts as only one IF statement,<br>because the extra IF statements are nested inside the first.<br>The code at left can also be written as below<br>\(note how brackets control the evaluation of the conditions\)<br>**IF ({field2} = "A" AND<br>&nbsp;&nbsp;&nbsp;&nbsp;{field3} > 10)&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;OR<br>&nbsp;&nbsp;&nbsp;&nbsp;({field2} = "D")&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;OR<br>&nbsp;&nbsp;&nbsp;&nbsp;({field2} = "G")<br>&nbsp;&nbsp;&nbsp;&nbsp;THEN SKIP<br>ENDIF**|
|**IF ISNOTFOUND({Lockup4})<br>&nbsp;&nbsp;&nbsp;&nbsp;THEN SKIP<br>ENDIF**|Skip all input records where lookup path Lockup4 does<br>not successfully find a target record, and select all other records.<br>This example is the same as:<br>&nbsp;&nbsp;&nbsp;&nbsp;**SKIPIF(ISNOTFOUND({Lockup4}))**|
|**IF ISNOTFOUND({Lockup4,field7})<br>&nbsp;&nbsp;&nbsp;&nbsp;THEN SKIP<br>ENDIF**|Skip all input records where lookup path Lockup4 does<br>not successfully find a target record using effective date of field7,<br>and select all other records. This example is the same as:<br>&nbsp;&nbsp;&nbsp;&nbsp;**SKIPIF(ISNOTFOUND({Lockup4,field7}))**|
|**IF ISNOTFOUND({Lockup4;$SYM="A"})<br>&nbsp;&nbsp;&nbsp;&nbsp;THEN SKIP<br>ENDIF**|Skip all input records where lookup path Lockup4 does<br>not successfully find a target record using symbol SYM set to "A",<br>and select all other records. This example is the same as:<br>&nbsp;&nbsp;&nbsp;&nbsp;**SKIPIF(ISNOTFOUND({Lockup4;$SYM="A"}))**|
|**IF ISNOTFOUND({Lockup4,<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;field7;$SYM1=3,$SYM2=0})<br>&nbsp;&nbsp;&nbsp;&nbsp;THEN SKIP<br>ENDIF**|Skip all input records where lookup path Lockup4 does<br>not successfully find a target record using effective date of field7<br>and symbol SYM1 set to 3 and symbol SYM2 set to zero.<br>Select all other records. This example is the same as:<br>&nbsp;&nbsp;&nbsp;&nbsp;**SKIPIF(ISNOTFOUND({Lockup4,<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;field7;$SYM1=3,$SYM2=0}))**|



  
  (Examples can be copied to the clipboard.)
  




