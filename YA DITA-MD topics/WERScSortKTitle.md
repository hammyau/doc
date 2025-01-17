 

# 02 Screen function and rights

[//]: # ( Comment on old image - PLEASE KEEP - <img src="../images/Edit_View_6_SortKeyTitles_01.gif" alt="Missing image" width="100" height="100"/> )

The above screen image has been compressed horizontally for ease of printing and display. Some fields are wider than shown.

Use this screen to create or update the sort key title for a view.

This screen does not appear if the output format for a view is **Flat File**. This screen also does not appear if the output format is either **Hardcopy** and the display mode of the sort key is **As Data**.

This screen is available for all users of the workbench.

# 05 Errors

For errors or messages on this screen, see topic "**Sort Key Titles errors**". For a link, see under **Related reference** below.

# 10 Action on this screen

Enter or modify values in cells where the background is white \(not grey\). When complete,

-   **EITHER** click <img src="../images/Icon_Save_03.GIF" alt="Missing image" width="35" height="35"/> \(the save icon\" alt="Missing image" width="35" height="35"/>,
-   **OR** select **File, Save**,
-   **OR** press **Ctrl+S**.

[//]: # ( Comment on old image - PLEASE KEEP - Alternatively, click <img src="../images/LR_Delete_field_03.GIF" alt="Missing image" width="100" height="100"/> to effectively clear the sort key title fields. This button does not work for a new sort key field. )

# 50 Fields

|Field|Definition|
|-----|----------|
|View Source|Click in this field to display a drop down list of logical record and logical file pairs available. Ensure one choice is selected.|
|Title Field|Click in this field to display a drop down list of available combinations of logical record, lookup path and logical record field name. Ensure one choice is selected.|
|Effective Date Type|Select a value to determine the type of effective date for the lookup path.|
|Effective Date Value|If the value in the previous field is Run Date, then no value is required for this field. If the previous field is CCYYMMDD then type a date in that format. If the previous field is Source File Field, then select a logical record field from the list given.|
|Title Length|The length of the title field. A positive integer greater than zero and up to a maximum of four digits. Must not be greater than the actual length of the logical record field selected in Title Field.|

# 99 Keyboard Shortcuts

See section "**10 Shortcuts: All workbench screens**" in topic "**What are the keyboard shortcuts?**" .

A link to this topic is under **Related reference** below.

**Parent topic:**[Workbench Screen help](../html/AAR586WEScreens.md)

