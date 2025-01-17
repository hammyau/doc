 

# 02 Screen function and rights

[//]: # ( Comment on old image - PLEASE KEEP - <img src="../images/Group_Perm_4_ByGroup_Group_AssocEnvs_01.gif" alt="Missing image" width="100" height="100"/> )

This screen specifies the rights of a group to modify components of an environment.

This screen is for system administrators only.

The Group Permissions screen has three sections:

|Section|Notes|
|-------|-----|
|**Groups**|Select the group to work on. If the list is long, sort the drop down list by clicking on "id" or "name" in the header of the list. Reverse the sort order by clicking again on "id" or "name" in the header.|
|**Associated Environments**|Displays the environments this group can access, and allows modification to this list.|
|**Component Security**|Security details of the **highlighted environment** under **Associated Environments**. This section has two tabs:-   "**Permissions**" tab. Allows the group to **create new components of certain types** and **run certain SAFR processes** in this environment.
-   "**Edit Rights**" tab. Allows the group **Read, Modify or Delete** access for **any existing component** in this environment.

|

# 05 Errors

For errors or messages on this screen, see topic "**Group Permissions messages**". For a link, see under **Related reference** below.

# 10 Action - Groups section

Select any group. If the list is long, sort the drop down list by clicking on "id" or "name" in the header of the list. Reverse the sort order by clicking again on "id" or "name" in the header.

Optionally, **right** click any group already in the field "**Group**" and select "**Open Editor**". This opens the "**Edit Group**" screen.

# 20 Action - Associated Environments section

|If you want to ...|then ...|
|------------------|--------|
|**Add one or more environments** for that group to access|Click **Add**. On the screen "**Select components to be associated**", tick the relevant environments and click OK. Sort the list by clicking on "id" or "name" in the header of the list. Reverse the sort order by clicking again on "id" or "name" in the header. If the list of environments in "Select components to be associated" is long, this list can be searched - see the section below. If the button **Add** is grey, ensure a group is selected above.|
|**Allow \(or disallow\)** the group to have **administration rights** to an environment.|**A tick in the Admin column** gives administration rights for the group in that environment.

Remove the tick to disallow administration rights. The group can still have rights given in the Component Security section below.

|
|**Remove one or more environments** from access by that group|Highlight the relevant environment\(s\) and click **Remove**. You can sort the list by clicking on "id" or "name" in the header of the list. Reverse the sort order by clicking again on "id" or "name" in the header. If the list of environments in "Associated Environments" is long, this list can be searched - see the section below. If the button **Remove** is grey, ensure an environment is highlighted. If you need to highlight more than one environment, hold the Ctrl key down and click on an extra environment. Hold the Ctrl key down and click on a highlighted environment to remove the highlight. Hold the Shift key down to highlight all environments back to and including the last highlighted environment.|
|See details of a listed **environment**.|**Right** click in any existing **row** of values in the "Associated Environments" table and select "**Open Editor**". This opens the "**Edit Environment**" screen.|

When all changes are complete,

-   **EITHER** click <img src="../images/Icon_Save_03.GIF" alt="Missing image" width="35" height="35"/> \(the save icon\" alt="Missing image" width="35" height="35"/>,
-   **OR** select **File, Save**,
-   **OR** press **Ctrl+S**.

# 30 Searching in Associated Environments

If there is a long list of associated environments, then the list can be searched as follows:

1.  Click inside the list under "**Associated Environments**".
2.  Press the **F3 key**. Alternatively, click on the **search icon** <img src="../images/Icon_SearchMetadata_01.gif" alt="Missing image" width="35" height="35"/> in the Workbench toolbar. If the icon is grey, repeat the previous step and the icon should now be available.
3.  The screen "**Search Metadata Component**" appears. Choose the type of search you require: either "**By ID**" or "**By Name**".
4.  In the field "**Search text**" type either the ID or the first characters in the environment name.
5.  Click OK to start the search.

If the environment is found, then you are returned to the list with that environment highlighted.

For more about this searching, read task "**Searching lists of metadata**". A link to that topic is under **Related tasks** below.

# 40 Searching in "Select components to be associated"

Only system administrators can reach this screen.

After clicking **Add**, the screen "**Select components to be associated**" lists the environments available. If there is a long list of environments, then this list can be searched as follows:

1.  Click inside the list under "**Select components to be associated**".
2.  Press the **F3 key**. Alternatively, click on the **search icon** <img src="../images/Icon_SearchMetadata_01.gif" alt="Missing image" width="35" height="35"/> in the Workbench toolbar. If the icon is grey, repeat the previous step and the icon should now be available.
3.  The screen "**Search Metadata Component**" appears. Choose the type of search you require: either "**By ID**" or "**By Name**".
4.  In the field "**Search text**" type either the ID or the first characters in the environment name.
5.  Click OK to start the search.
6.  If the component is found, then you are returned to the screen "Select components to be associated" with that component highlighted. Tick the file to include \(later\) in the list of associated environments.
7.  You may search again if required. You may tick as many environments as required.
8.  When all ticks are in place, click OK to complete the add of ticked files.

For more about this searching, read task "**Searching lists of metadata**". A link to that topic is under **Related tasks** below.

# 50 Fields - Groups section

|Field|Definition|
|-----|----------|
|Groups|Select an existing group. If the list is long, sort the list by clicking on "id" or "name" in the header of the list. Reverse the sort order by clicking again on "id" or "name" in the header. When a group is selected, the fields in the Associated Environments section are populated.

|

# 60 Fields - Associated Environments section

|Field|Definition|
|-----|----------|
|Admin|A tick gives the group administration rights to that environment, which means all members of that group are environment administrators. Remove the tick to remove these rights. \(Optional.\)|
|ID|The ID of the environment. Click on the column heading **ID** to sort the list by ID. Click repeatedly to switch between ascending and descending sort order. \(Display only.\)|
|Name|The name of the environment. Click on the column heading **Name** to sort the list by Name. Click repeatedly to switch between ascending and descending sort order. \(Display only.\)|

# 99 Keyboard Shortcuts

See section "**10 Shortcuts: All workbench screens**" in topic "**What are the keyboard shortcuts?**" .

A link to this topic is under **Related reference** below.

**Parent topic:**[Workbench Screen help](../html/AAR586WEScreens.md)

