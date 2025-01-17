 

# 10 What is a view output file?

A view output file is a file of SAFR results. View output files are the objective for running SAFR in your company.

A view output file can be a report, a new file or an updated file. The file may be in any mainframe file format, and can also be a delimited file that could be used by a spreadsheet on a PC.

View output files are described in a view. By selecting that view and running PE, SAFR produces the results in the form of view output files.

[//]: # ( Comment on old image - PLEASE KEEP - <img src="../images/VOutF_Concept_01.gif" alt="Missing image" width="100" height="100"/> )

View output files can be produced in two places in PE:

-   In the extract phase using program MR95
-   In the format phase using program MR88.

[//]: # ( Comment on old image - PLEASE KEEP - <img src="../images/VOutF_Action_01.gif" alt="Missing image" width="100" height="100"/> )

For more background information, see these topics:

-   "**EXT files overview**"
-   "**Extract phase overview**"
-   "**Format phase overview**"
-   "**MR88 Format Data overview**"
-   "**MR95 Reference and Extract overview**"

Links to these overviews are under **Related concepts** below.

# 20 DDNAME for a view output file

View output files have a default DDNAME of **F<ViewNbr\>** where the view ID number has 7 digits. If necessary, the view number is padded with leading zeroes.

The default is replaced \(if a value exists\) with the **output DDNAME field for the physical file** associated with the view output file.

The view output file is specified either in the **Extract phase tab** or the **Format phase tab** of a view.

These two tabs are discussed in these topics:

-   "**Edit View \(View Properties, Extract phase tab\) screen help**"
-   "**New View \(View Properties, Extract phase tab\) screen help**"
-   "**Edit View \(View Properties, Format phase tab\) screen help**"
-   "**New View \(View Properties, Format phase tab\) screen help**"

Links to these overviews are under **Related reference** below.

The Extract phase tab and the Format phase tab specify only an output logical file and physical file. The output DDNAME for the physical file does not appear.

The output DDNAME for the physical file is shown in these topics:

-   "**Edit Physical File screen help**"
-   "**New Physical File screen help**"

Links to these overviews are under **Related reference** below.

# 30 Phases for view output files

[//]: # ( Comment on old image - PLEASE KEEP - <img src="../images/VOutF_Phases_01.gif" alt="Missing image" width="100" height="100"/> )

Processing of view output files is as follows:

1.  Program **MR95** may create one or more **view output files** in the **extract** phase.Â 

    For more, see these topics:

    -   "**Extract phase overview**"
    -   "**MR95 Reference and Extract overview**"
    Links to these overviews are under **Related concepts** below.

2.  Program **MR88** may run once or many times to create one or more **view output files** in the **format** phase.Â 

    For more, see these topics:

    -   "**Format phase overview**"
    -   "**MR88 Format Data overview**"
    Links to these overviews are under **Related concepts** below.


