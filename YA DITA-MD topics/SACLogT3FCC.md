 

# 10 What is logic text for Format Column Calculations?

The logic text "Format Column Calculations" can also be called "**Format-Phase Calculations**".

All logic text is optional. The objective of this logic text is to create columns based on numeric calculations for processing in a view. This logic text is limited to **numeric columns** in a view.

Specifically, this logic text **defines calculations** for columns in the format phase of the SAFR Performance Engine. This phase is optional, because the extract phase may be sufficient to produce the results of that view.

For an introduction to SAFR phases, see topic "**SAFR phases overview**". A link to that overview is under **Related concepts** below.

# 20 Where do I find syntax and examples of this logic text?

The syntax of this logic text and examples are described in topic "**Logic text 3: Format Column Calculations**". A link to this topic is under **Related reference** below.

# 30 How do I create logic text for Format Column Calculations?

This logic text is part of a view and is associated with a column during the format phase. To create this logic text in an existing view, do the following:

1.  Ensure you are on the "**Edit View**" screen for the relevant view. For help with displaying this screen, see topic "**Modifying Views**" in the General User Guide.
2.  The view must have a format phase. If there is no format phase or you are not sure, see topic "**Edit View \(View Properties, General tab\) screen help**". A link to this topic is under **Related reference** below.
3.  Ensure you are on the "**View Editor**" tab. If the "**View Properties**" tab is displayed, click the **Show Grid / Properties** button. <img src="../images/Icon_Show_Grid_Props_01.gif" alt="Missing image" width="35" height="35"/> or press F9 or select **Edit -\> Show Grid/Properties**.
4.  Select a **numeric column** that is not part of the sort key. \(A numeric column is any Data Type that is not Alphanumeric.\) In that column **double click** on the cell for row "**Format-Phase Calculation**". That cell may be grey, which means this logic text cannot be applied. This may be because the column is part of the sort key, or is not numeric. This may also be because there is no format phase.
5.  Click <img src="../images/Icon_Three_Dots_01.gif" alt="Missing image" width="35" height="35"/>.
6.  Type your logic text in the window "**Create New Format-Phase Calculation**" or "**Edit Format-Phase Calculation**".
7.  Click <img src="../images/Icon_ValidLT_02.gif" alt="Missing image" width="35" height="35"/> to check if the logic text is valid.
8.  Fix any errors shown in the "**Logic Text Validation Errors**" window.
9.  When the new logic text is complete and valid,
    -   **EITHER** click <img src="../images/Icon_Save_03.GIF" alt="Missing image" width="35" height="35"/> \(the save icon\" alt="Missing image" width="35" height="35"/>,
    -   **OR** select **File, Save**,
    -   **OR** press **Ctrl+S**.
10. You may wish to close some of the open windows, such as "**Logic Text Helper**" and "**Create New Format-Phase Calculation**" or "**Edit Format-Phase Calculation**".

