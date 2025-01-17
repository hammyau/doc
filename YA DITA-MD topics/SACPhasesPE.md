 

# Summary of this topic

The sections in this topic are as follows:

-   [What are SAFR phases?](SACPhasesPE.md#02)
-   [1. Select phase](SACPhasesPE.md#10)
-   [2. Compile phase](SACPhasesPE.md#20)
-   [3. Logic phase](SACPhasesPE.md#30)
-   [4. Reference phase](SACPhasesPE.md#40)
-   [5. Extract phase](SACPhasesPE.md#50)
-   [6. Format phase](SACPhasesPE.md#60)
-   [100 Need more on this page?](SACPhasesPE.md#100)

# What are SAFR phases?

The phases are shown below:

[//]: # ( Comment on old image - PLEASE KEEP - <img src="../images/PM_All_Progs_05_Thin.gif" alt="Missing image" width="100" height="100"/> )

# 1. Select phase

This phase selects views for this run of PE. The JCL lists the ID numbers of the views.

This phase produces a VDP XML file.

For more, see these overviews:

-   "**Select phase overview**"
-   "**VDP File overview**"
-   "**XML structure for VDP overview**"

Links to the above overviews are under **Related concepts** below.

# 2. Compile phase

This phase converts a VDP XML file to a VDP file. During this conversion, the logic text is recompiled to ensure the latest compiler is used for this run of PE.

For more, see these overviews:

-   "**Compile phase overview**"
-   "**Compiler overview**"
-   "**VDP file overview**"
-   "**XML structure for VDP overview**"

Links to the above overviews are under **Related concepts** below.

# 3. Logic phase

This phase does the following:

1.  Creates the XLT and JLT files for the selected views.
2.  Translates the VDP file into EBCDIC format \(from ASCII\).
3.  Translates the XLT file into EBCDIC format \(from ASCII\).
4.  Translates the JLT file into EBCDIC format \(from ASCII\).
5.  Updates the VDP file with VSAM details.

For more, see these overviews:

-   "**Logic phase overview**"
-   "**Logic tables and codes overview**"
-   "**JLT file overview**"
-   "**VDP file overview**"
-   "**XLT file overview**"

Links to the above overviews are under **Related concepts** below.

# 4. Reference phase

This phase does the following:

1.  Creates a report of the JLT file which is useful in debugging problems.
2.  Prepares reference file data for processing in the next phase.
3.  Creates a Reference File Creation Control Report \(Extract\)
4.  Creates a Reference File Creation Control Report \(Sort Title\)

For more, see these overviews:

-   "**Reference phase overview**"
-   "**JLT file overview**"
-   "**VDP file overview**"

Links to the above overviews are under **Related concepts** below.

# 5. Extract phase

This phase does the following:

1.  Creates a report of the XLT file which is useful in debugging problems.
2.  Perform the extract processing, which may be most of the processing done in PE.

For more, see these overviews:

-   "**Extract phase overview**"
-   "**VDP file overview**"
-   "**XLT file overview**"

Links to the above overviews are under **Related concepts** below.

# 6. Format phase

This phase is optional and formats output files from the extract phase. There can be multiple format phases - one phase per output. file.

For more, see these overviews:

-   "**Format phase overview**"
-   "**VDP file overview**"

Links to the above overviews are under **Related concepts** below.

