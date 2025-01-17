 

# 10 Program name

The full name of the program is **GVBMR95** and the short name is **MR95**.

This program is part of the SAFR Performance Engine.

# 20 What MR95 does

The program MR95 uses logic tables in the reference phase and the extract phase.

In the reference phase, the JLT file ensures MR95 does preparation to process lookup paths very quickly.

In the extract phase, the XLT ensures MR95 processes the source files, executes lookup paths and produces the output very quickly.

MR95 uses the logic table instructions to generate machine code. Effectively, MR95 is "interpreting" logic tables and does not "know" which phase the program is running in. This is the reason that the reference phase and the extract phase both use MR95 - in both phases a logic table is processed - the JLT for the reference phase and the XLT for the extract phase.

# 30 MR95 and phases of the Performance Engine

[//]: # ( Comment on old image - PLEASE KEEP - <img src="../images/MR95_Phases_01.gif" alt="Missing image" width="100" height="100"/> )

MR95 runs in the **reference and extract phases** of the Performance Engine.

For more, see help topics "**Reference phase overview**" and "**Extract phase overview**". Links to these overviews are under **Related concepts** below.

# 40 MR95 Report

This is DDNAME **MR95RPT** in the job step for MR95.

To be completed

# 50 How to run MR95 in Reference phase

See topic "**Program Runbook: MR95 Reference Data**". A link to that topic is under **Related reference** below.

# 60 How to run MR95 in Extract phase

See help topic "**Program Runbook: MR95 Extract Data**". A link to that topic is under **Related reference** below.

