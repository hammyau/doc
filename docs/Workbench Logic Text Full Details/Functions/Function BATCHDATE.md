﻿---
layout: default
title: "Function BATCHDATE"
parent: Functions
grand_parent: Workbench Logic Text Full Details
nav_order: 2
---
# Function BATCHDATE
{: .no_toc}
TABLE OF CONTENTS 
1. TOC
{:toc}  


# How do I use BATCHDATE? 

The BATCHDATE returns a date in CCYYMMDD format that is when the view is run. The group of views all running in the same batch in the Performance Engine all use the same BATCHDATE.

The parameter for BATCHDATE is a number of days to add or delete from the default BATCHDATE. For example, BATCHDATE\(-5\) provides the day five days before the date the view is run.

BATCHDATE can only be used in **Extract Record Filter (ERF)** and **Extract Column Assignment (ECA)** logic text.


![(Syntax Legend)](../../images/LTZZ_Syntax_legend.gif )

# Syntax 

![Function BATCHDATE](../../images/LTSF_BATCHDATE_01.gif)

# Rules for the syntax 

BATCHDATE can only be used in **Extract Record Filter (ERF)** and **Extract Column Assignment(ECA)** logic text.

See also topic: [Rules for all Logic Text](../Rules for all Logic Text) 


# Examples: BATCHDATE function in ERF

|Example logic text|Meaning|
|------------------|-------|
|**IF ({field1} < BATCHDATE(-7))<br>&nbsp;&nbsp;&nbsp;&nbsp;THEN SKIP<br>ENDIF**|Skip any input records where field1 is more than 7 days before the<br>date of running this view. Select all other records.<br> This example can also be written:<br>&nbsp;&nbsp;&nbsp;&nbsp;**SKIPIF({field1} < BATCHDATE(-7))**|



# Examples: BATCHDATE function in ECA

|Example logic text|Meaning|
|------------------|-------|
|**COLUMN = BATCHDATE()**|Set the current column to the date<br> that this view is run.|
|**COLUMN = BATCHDATE(-7)**|Set the current column to the date<br> that is 7 days before the view is run.|
|**COLUMN = {Lookup3.Field4,BATCHDATE(-32)**|Set the current column to Field4 found by Lookup3<br> as of 32 days before the view is run.|

  

  
  (Examples can be copied to the clipboard.)
  
