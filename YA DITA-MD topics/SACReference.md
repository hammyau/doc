 

# 10 Diagram

[//]: # ( Comment on old image - PLEASE KEEP - <img src="../images/PM_4Ref_Progs_01.gif" alt="Missing image" width="100" height="100"/> )

# 20 Inputs and outputs

The reference phase is the fourth phase of PE, and consists of these programs.

-   **UT90** .
-   **MR95** .
-   **MR71** .

The reference phase prepares reference files for processing in the extract phase of PE. **Input** to the reference phase is:

-   VDP file
-   JLT file
-   Reference data files for the views in the VDP.

The reference phase does the following:

1.  Creates a report of the JLT file which is useful in debugging problems.
2.  Prepares reference file data for processing in the next phase in MR95. This creates the RED, REH and RTH files.
3.  Creates a Reference File Creation Control Report \(Extract\) using the REH file.
4.  Creates a Reference File Creation Control Report \(Sort Title\) using the RTH file.

MR95 works as follows

-   Inputs:
    -   VDP file
    -   **JLT file** \(effectively, this file "drives" the reference phase\)
    -   Reference data files
-   Outputs:
    -   RED files
    -   REH file
    -   RTH file

# 30 Why is it called "reference"?

The word "**reference**" in the phase "**reference phase**" refers to the input reference files and the output RED, REH and RTH files. The RED, REH and RTH files are input to the extract phase and allow the extract phase to achieve many of the performance advantages of SAFR.

For more, see these overviews:

-   "**JLT file overview**"
-   "**Logic tables and codes overview**"
-   "**MR71 Reference Report overview**"
-   "**MR95 Reference and Extract overview**"
-   "**RED file overview**"
-   "**REH file overview**"
-   "**RTH file overview**"
-   "**SAFR phases overview**"
-   "**UT90 Logic Table Report overview**"
-   "**VDP file overview**"

Links to the above overviews are under **Related concepts** below.

