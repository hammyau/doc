 

# 02 Screen function and rights

[//]: # ( Comment on old image - PLEASE KEEP - <img src="../images/New_Environment_01.gif" alt="Missing image" width="100" height="100"/> )

Use this screen to create a new environment record.

This screen is for system administrators only.

# 05 Errors

For errors or messages on this screen, see topic "**New Environment errors**". For a link, see under **Related reference** below.

# 10 Action on this screen

Enter or modify values and save as follows:

-   **EITHER** click <img src="../images/Icon_Save_03.GIF" alt="Missing image" width="35" height="35"/> \(the save icon\" alt="Missing image" width="35" height="35"/>,
-   **OR** select **File, Save**,
-   **OR** press **Ctrl+S**.

# 50 Fields - General Information section

|Field|Definition|
|-----|----------|
|ID|The position in the list of all environments. \(Display only.\)|
|Name|Up to 48 characters, starting with a letter, and composed of letters, numbers, the Number sign \(\#\) and the underscore \(\_\). Pressing the spacebar automatically creates an underscore in this field. Must be unique \(among environment names\).Examples of permitted names:

-   CA\_SF\_Accounts\_Receivable\_2009
-   Sales\_DivisionC76

These names are not permitted:

-   2009\_Expenses \(doesn't start with a letter\)
-   New York Sales \(must not include spaces\)
-   USA/Canada Summary 1.1 \(must not include "/" or fullstop\)

|
|Enable Archiving?|Tick if this environment might be a target of the Migration Utility. Once ticked, the Migration Utility archives data to an XML file before overwriting this environment. \(Optional.\)|
|Comments|Useful notes, up to 254 characters. \(Optional.\)|
|Created|The person who created this record, and the date and time of creation. \(Display only.|
|Last Modified|The last person who modified this record, and the date and time of the change. \(Display only.\)|

# 60 Fields - Default Initialization Parameters section

|Field|Definition|
|-----|----------|
|Control Record Name|This field names the first control record for the new environment. A default name is given which you can change. Up to 48 characters, starting with a letter, and composed of letters, numbers, the Number sign \(\#\) and the underscore \(\_\). Pressing spacebar automatically creates an underscore in this field.|
|Group Name|General users in this group can access the new environment. If you give an existing group, SAFR uses that group. If you give a new group, SAFR creates that new group. Up to 48 characters, starting with a letter, and composed of letters, numbers, the Number sign \(\#\) and the underscore \(\_\). Pressing spacebar automatically creates an underscore in this field.|
|View Folder Name|This field names the first view folder name for the new environment. A default name is given which you can change. A string of up to 32 characters, starting with a letter, and composed of letters, numbers, the Number sign \(\#\) and the underscore \(\_\). Pressing spacebar automatically creates an underscore in this field.|

# 99 Keyboard Shortcuts

See section "**10 Shortcuts: All workbench screens**" in topic "**What are the keyboard shortcuts?**" .

A link to this topic is under **Related reference** below.

**Parent topic:**[Workbench Screen help](../html/AAR586WEScreens.md)

