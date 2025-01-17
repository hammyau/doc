 

# 10 Program name

The full name of the program is **GVBMR77** and the short name is **MR77**.

This program is part of the SAFR Performance Engine.

# 20 What MR77 does

DB2 databases are supported by underlying VSAM files. PE programs access the underlying VSAM files directly, rather than using the usual DB2 software methods.

MR77 provides the details of the relevant VSAM files. MR77 reads the VDP output from MR75 and checks the selected views for any DB2 databases accessed. MR77 finds the relevant VSAM files and updates the VDP with those extra details.

For more information about VDP, see help topic "**VDP overview**". A link to that overview is under **Related concepts** below.

# 30 MR77 and phases of the Performance Engine

[//]: # ( Comment on old image - PLEASE KEEP - <img src="../images/MR77_Phases_01.gif" alt="Missing image" width="100" height="100"/> )

MR77 runs in the **Logic phase** of the Performance Engine.

For more, see help topic "**Logic phase overview**". A link to that overview is under **Related concepts** below.

# 50 How to run MR77

See help topic "**Program Runbook: MR77 VDP VSAM Update**". A link to that topic is under **Related reference** below.

