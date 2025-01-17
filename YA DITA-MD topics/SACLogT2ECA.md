 

# 10 What is logic text for Extract Column Assignment?

All logic text is optional. The objective of this logic text is to create columns for processing in a view, and possibly to write certain records to files.

Specifically, this logic text **defines column values** in files processed in the extract phase of the SAFR Performance Engine. Writing of input records to files is also controlled in this logic text.

For an introduction to SAFR phases, see topic "**SAFR phases overview**". A link to that overview is under **Related concepts** below.

# 20 Where do I find syntax and examples of this logic text?

The syntax of this logic text and examples are described in topic "**Logic text 2: Extract Column Assignment**". A link to this topic is under **Related reference** below.

# 30 How do I create logic text for Extract Column Assignment?

This logic text is part of a view and is associated with a column and a view source file. To create this logic text in an existing view, do the following:

1.  Ensure you are on the "**Edit View**" screen for the relevant view. For help with displaying this screen, see topic "**Modifying Views**" in the General User Guide.
2.  The view must already have at least one view source defined. If there is no view source defined, see topic "**Edit View \(View Editor tab\) screen help**". A link to this topic is under **Related reference** below.
3.  Ensure you are on the "**View Editor**" tab. If the "**View Properties**" tab is displayed, click the **Show Grid / Properties** button. <img src="../images/Icon_Show_Grid_Props_01.gif" alt="Missing image" width="35" height="35"/> or press F9 or select **Edit -\> Show Grid/Properties**.
4.  In the column immediately below "View Editor", if there is a plus + sign to the left of '**View Source**", double click the plus sign to expand the list of view sources.
5.  Click on a cell in the relevant column that is also in the row for the relevant view source file.
6.  The "**Column Source Properties**" window appears. Double click "**Column Source Type**" and select "**Formula**" from the drop down box.
7.  Double click "**Column Source Value**" and click <img src="../images/Icon_Three_Dots_01.gif" alt="Missing image" width="35" height="35"/>.
8.  Type your logic text in the window "**Create New Extract Column Assignment**" or "**Edit Extract Column Assignment**".
9.  Click <img src="../images/Icon_ValidLT_02.gif" alt="Missing image" width="35" height="35"/> to check if the logic text is valid.
10. Fix any errors shown in the "**Logic Text Validation Errors**" window.
11. When the new logic text is complete and valid,
    -   **EITHER** click <img src="../images/Icon_Save_03.GIF" alt="Missing image" width="35" height="35"/> \(the save icon\" alt="Missing image" width="35" height="35"/>,
    -   **OR** select **File, Save**,
    -   **OR** press **Ctrl+S**.
12. You may wish to close some of the open windows, such as "**Logic Text Helper**" and "**Create New Extract Column Assignment**" or "**Edit Extract Column Assignment**".

