 

# 02 Screen function and rights

[//]: # ( Comment on old image - PLEASE KEEP - <img src="../images/Edit_Ctrl_Rec_01.gif" alt="Missing image" width="100" height="100"/> )

Use this screen to edit an existing control record.

This screen is for system and environment administrators only.

# 05 Errors

For errors or messages on this screen, see topic "**Edit Control Record errors**". For a link, see under **Related reference** below.

# 10 Action on this screen

Enter or modify values and save as follows:

-   **EITHER** click <img src="../images/Icon_Save_03.GIF" alt="Missing image" width="35" height="35"/> \(the save icon\" alt="Missing image" width="35" height="35"/>,
-   **OR** select **File, Save**,
-   **OR** press **Ctrl+S**.

# 50 Fields

|Field|Definition|
|-----|----------|
|ID|The position in the list of all control records. \(Display only.\)|
|Name|Up to 48 characters, starting with a letter, and composed of letters, numbers, the Number sign \(\#\) and the underscore \(\_\). Pressing the spacebar automatically creates an underscore in this field. Must be unique among control record names in this environment.Examples of permitted names:

-   CA\_SF\_Accounts\_Receivable\_2009
-   Sales\_DivisionC76

These names are not permitted:

-   2009\_Expenses \(doesn't start with a letter\)
-   New York Sales \(must not include spaces\)
-   USA/Canada Summary 1.1 \(must not include "/" or fullstop\)

|
|Maximum Extract File Number|The maximum number of extract files that can be created in the Extract Phase. Must be greater than zero and up to nine digits.|
|Comments|Useful notes, up to 254 characters. \(Optional.\)|
|Created|The person who created this record, and the date and time of creation. \(Display only.|
|Last Modified|The last person who modified this record, and the date and time of the change. \(Display only.\)|
|First Fiscal Month|Mandatory: the calendar month in which the fiscal year starts. A number in the range one to 12, representing the months January to December.|
|Beginning Period|A month numbered from zero to 11. This is an alternative to First Fiscal Month which is from one to 12. \(Optional.\)|
|Ending Period|A month numbered from zero to 11. Must be larger than Beginning Period, if set. \(Optional.\)|

# 99 Keyboard Shortcuts

See section "**10 Shortcuts: All workbench screens**" in topic "**What are the keyboard shortcuts?**" .

A link to this topic is under **Related reference** below.

**Parent topic:**[Workbench Screen help](../html/AAR586WEScreens.md)

