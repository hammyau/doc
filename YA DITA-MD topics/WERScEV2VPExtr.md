 

# 02 Screen function and rights

[//]: # ( Comment on old image - PLEASE KEEP - <img src="../images/Edit_View_1_ViewProps_2ExtractPh_01.gif" alt="Missing image" width="100" height="100"/> )

The above screen image has been compressed horizontally for ease of printing and display. Some fields are wider than shown.

Use this screen to define the given fields in a view.

This screen is available to all users of the workbench. General users can save a view if the group selected during login has at least the modify right to the relevant view folder that contains the view. See your system administrator if you require more rights.

# 03 Summary of how to prepare a view

The main focus of preparing a view is preparing the **columns**. Each column is a field in the logical record for the output file of the view.

A view is displayed in two large tabs:

-   The first large tab is the "**View Properties**" tab, which has sub-tabs:



    -   **General sub-tab**

        This sub-tab names the view, the view folder and the control record. This sub-tab also defines the type of output of the view as a whole and whether a format phase is required.

    -   **Extract Phase sub-tab**

        This sub-tab defines some parameters of the extract phase processing in the Performance Engine. An output logical file and physical file for the extract phase are only defined if this view has no format phase. Other parameters are available regardless of the existence or not of a format phase.

    -   **Format Phase sub-tab**

        This sub-tab only exists if the **General sub-tab** has a tick for format phase. This sub-tab defines some parameters of the format phase processing in the Performance Engine.

    -   **Header/ Footer sub-tab**

        This tab only exists if the **General sub-tab** has **Hardcopy Report** selected, which ensures a format phase. This sub-tab defines a Header and Footer for the report.

    The "**View Properties**" tab can also be called the "**Properties**" tab.

-   The second large tab is the "**View Editor**" tab.

    This tab describes the columns in the output logical file. Most of the action on this screen is about the columns each headed with "Column X".

    Normally the first action on the 'View Editor" tab is to define at least one **view source file**, which is an input logical record and logical file for the view.

    You can save the view without a view source. To activate a view there must be at least one view source.

    The "**View Editor**" tab can also be called the "**Grid**" tab because of the display of the columns.


Only one large tab is displayed at a time. To switch between the large tabs click the **Show Grid / Properties** button <img src="../images/Icon_Show_Grid_Props_01.gif" alt="Missing image" width="35" height="35"/> or press F9 or select **Edit -\> Show Grid / Properties**.

The objective of all the tabs is an **active** view, because only active views can produce results in the SAFR Performance Engine.

A high level overview of reaching the objective is as follows:

-   Enter or modify values you require in the tabs.
-   **Save the values** in the view. When you save, the workbench performs validation checks and any validation error prevents the save. For example, there must be a unique view name. Fix any validation errors and repeat the save until successful.
-   **Activate the view** to change the status to "Active".

    When the view is first created the screen heading says "**New View - \[Inactive\]**". After successful activation, the screen heading becomes "**New View - \[Active\]**" or "**Edit View - \[Active\]**".

    If you modify any value in an existing "Active" view, when you click or tab away from the modified field the screen heading changes to "**Edit View - \[Inactive\]**". This means it is necessary to activate the view again.

    When you attempt to activate a view, the workbench performs activation checks. Any activation errors keep the status as "Inactive". For example, a view must have at least one sort key and at least one view source, even though a view can be saved without these items. Fix any activation errors and repeat the attempt to activate until successful.


General users need to be aware of help topic "**What metadata do I want to see?**" A link to that topic is under **Related reference** below.

When creating or editing a view, if you open a list and cannot see the required items such as logical records or logical files, see your system or environment administrator.

# 05 Errors

For error messages on the 'View Activation Errors" screen, see topic "**View Activation Errors message help**". For a link, see under **Related reference** below.

For all other messages on this screen, see topic "**Edit View errors**". For a link, see under **Related reference** below.

# 10 Action on the "View Properties, Extract Phase" tab

Remember to switch between the large tabs "**View Editor**" \(which has a grid for the columns\" alt="Missing image" width="35" height="35"/> and "**View Properties**" by clicking<img src="../images/Icon_Show_Grid_Props_01.gif" alt="Missing image" width="35" height="35"/> \(the **Show Grid / Properties** button\" alt="Missing image" width="35" height="35"/> or press F9 or select **Edit -\> Show Grid / Properties**.

Enter or modify values on the "**View Properties, Extract Phase**" tab. See the sections below for help on the fields on this screen.

Optionally, **right** click any value already in the field "**Logical File**" and select "**Open Editor**". This opens the "**Edit Logical File**" screen.

Optionally, **right** click any value already in the field "**Physical File**" and select "**Open Editor**". This opens the "**Edit Physical File**" screen.

Optionally, **right** click any value already in the field "**Name**" for "**Output User-Exit Routine**" and select "**Open Editor**". This opens the "**Edit User-Exit Routine**" screen.

When required,

-   **EITHER** click <img src="../images/Icon_Save_03.GIF" alt="Missing image" width="35" height="35"/> \(the save icon\" alt="Missing image" width="35" height="35"/>,
-   **OR** select **File, Save**,
-   **OR** press **Ctrl+S**.

When you save, there are **validations** of the values, and any validation error prevents the save. For example, there must be a unique view name. Once these validation errors are fixed, clicking save is successful.

Activation is explained in topics "**New View \(View Editor tab\) screen help**" and "**Edit View \(View Editor tab\) screen help**" because activation is normally performed on the "View Editor" tab.

# 50 Fields - Output File section

|Field|Definition|
|-----|----------|
|Logical File|Select an output logical file for this view. Click the drop down arrow to see a list of logical files where you have access rights. \(Optional.\) Sort the list by clicking on "id" or "name" in the header of the list. Reverse the sort order by clicking again on "id" or "name" in the header.|
|Physical File|Select a physical file that matches the given logical file in the field above. This drop down field lists the relevant physical files where you have access rights. \(Optional.\) Sort the list by clicking on "id" or "name" in the header of the list. Reverse the sort order by clicking again on "id" or "name" in the header.|

# 60 Fields - Output User-Exit Routine section

|Field|Definition|
|-----|----------|
|Name|Select a User-Exit Routine from the drop down list. All the routines are of type Write. \(Optional.\) Sort the list by clicking on "id" or "name" in the header of the list. Reverse the sort order by clicking again on "id" or "name" in the header. In rare cases, the User-Exit Routine named in this field may no longer be type Write due to some external update. If this occurs, the existing name is not shown in the drop down list, and you must select a new name from the drop down list.|
|Parameters|Input data for the user-exit routine, up to 32 characters. \(Optional.\)|

# 70 Fields - Extract-Phase Record Aggregation section

|Field|Definition|
|-----|----------|
|Do not aggregate records|Select this button to stop aggregation of output records. \(Optional.\)|
|Aggregate records with identical sort keys using a buffer of ? records|Select this button to aggregate records with identical sort keys using a buffer with a limit of the ? field. The ? value is a positive integer up to 9 digits. The default for the ? value is 4000. \(Optional.\)|

# 80 Fields - Extract-Phase Output Limit section

|Field|Definition|
|-----|----------|
|Write all eligible records|Select this button to ensure that all eligible records are output. This button is selected by default. \(Optional.\)|
|Stop Extract-Phase processing for this view after ? records are written|Select this field to stop the processing of this view after ? records are written. The ? value is a positive integer up to 9 digits. The default for the ? value is 100. \(Optional.\)|
|Extract Work File Number|The sequence number of the Work File passing data from the Extract Phase to the Format Phase. This field can only be used if a Format Phase is enabled for this view. The value is a positive integer up to 9 digits. The default value of this field is 1. \(Optional.\)|

# 99 Keyboard Shortcuts

Go to topic "**What are the keyboard shortcuts?**" and read these sections:

-   "**10 Shortcuts: All workbench screens**" and
-   "**32 Shortcuts: New/Edit View screen \(View Properties tab\)**".

A link to this topic is under **Related reference** below.

**Parent topic:**[Workbench Screen help](../html/AAR586WEScreens.md)

