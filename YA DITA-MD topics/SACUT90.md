 

# 10 Utility name

The full name of the program is **GVBUT90** and the short name is **UT90**.

This program is part of the SAFR Performance Engine.

# 20 What UT90 does

LT means Logic Table, and there are two examples:

-   JLT - the Join Logic Table. This file drives the Reference phase.
-   XLT - the Extract Logic Table. This file drives the Extract phase.

UT90 prints a report of one of these files, so the instructions in the logic tables can be easily read. The UT90 report is an essential resource for troubleshooting problems in the Performance Engine especially for problems in the extract phase.

For more information about JLT, see help topic "**JLT overview**". A link to that overview is under **Related concepts** below.

For more information about XLT, see help topic "**XLT overview**". A link to that overview is under **Related concepts** below.

# 30 UT90 and phases of the Performance Engine

UT90 runs in the **reference and extract phases** of the Performance Engine.

For more, see help topics "**Reference phase overview**" and "**Extract phase overview**". Links to these overviews are under **Related concepts** below.

# 40 UT90 Report

This is DDNAME **UT90RPT** in the job step for UT90.

To help support, it is recommended to send this report to output such as:

-   EJES \(a systems management tool\), or
-   SAVRS \(System Accumulation Viewing and Retrieval System\)

An example of this report is below.

# 50 Example of UT90 Report for an XLT

**IMPORTANT**: in the example below, some rows are not shown, due to page breaks in the report. The rows not shown are:

-   Row 1: "**HD**" code = Header that starts all logic tables
-   Row 2: "**RENX**" code = REad NeXt source file record.
-   Row 13 " **ES**" code = End Source file record.
-   Row 14 "**EN**" code = End of logic table.

[//]: # ( Comment on old image - PLEASE KEEP - <img src="../images/UT90RPT_01_XLT.gif" alt="Missing image" width="100" height="100"/> )

For examples of full reports on JLT and XLT files, see these topics:

-   "**JLT file overview**"
-   "**XLT file overview**"

Links to these overviews are under **Related concepts** below.

# 60 How to run UT90

See help topic "**Utility Runbook: UT90 Logic Table Report**". A link to that topic is under **Related reference** below.

