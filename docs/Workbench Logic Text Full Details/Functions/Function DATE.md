﻿---
layout: default
title: "Function DATE"
parent: Functions
grand_parent: Workbench Logic Text Full Details
nav_order: 4
---
# Function DATE
{: .no_toc}
TABLE OF CONTENTS 
1. TOC
{:toc}  


# How do I use DATE? 

DATE is used whenever you want to specify some date. You can use DATE to set a value, or as part of a comparison.

DATE can only be used in **Extract Record Filter (ERF)** and **Extract Column Assignment (ECA)*** logic text.


![(Syntax Legend)](../../images/LTZZ_Syntax_legend.gif )

# Syntax 

![(Function DATE 1)](../../images/LTSF_Date_01.gif)

![(Function DATE 2)](../../images/LTSF_DATE_02.gif)

![(Function DATE 3)](../../images/LTSF_DATE_03.gif)

![(Function DATE 4)](../../images/LTSF_DATE_04.gif)

# Rules for the syntax 

DATE can only be used in **Extract Record Filter (ERF)** and **Extract Column Assignment(ECA)** logic text.

See also topic: [Rules for all Logic Text](../Rules for all Logic Text) 


# Examples: DATE function in ERF 

|Example logic text|Meaning|
|------------------|-------|
|**IF {field1} = DATE("20111201",CCYYMMDD)<br>&nbsp;&nbsp;&nbsp;&nbsp;THEN SELECT<br>ENDIF**|Select those input records where<br>field1 is December 1, 2011.<br>The code at left can also be written as:<br>&nbsp;&nbsp;&nbsp;&nbsp;**SELECTIF({field1}= DATE("20111201",CCYYMMDD))**|



# Examples: DATE function in ECA 

|Example logic text|Meaning|
|------------------|-------|
|**COLUMN = DATE("20111201",CCYYMMDD)**|Set the current column to a date of<br>December 1, 2011 in CCYYMMDD format.|

  

  
  (Examples can be copied to the clipboard.)
  

