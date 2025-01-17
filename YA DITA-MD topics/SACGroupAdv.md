 

This topic assumes you are familiar with the topic "**Groups overview**". A link to that overview is under **Related concepts** below.

# 10 Group permissions to create types of components

Group members receive create permissions for types of components.

The group create permissions possible are as follows:

-   Create Logical Files,
-   Create Logical Records,
-   Create Physical Files,
-   Create User-Exit Routines,
-   Create View Folders.

The above permissions can be applied to a general user in one or more environments. Administrators in an environment always have these permissions.

Notice there is no "create" right for control records and global fields - these are only created by administrators. General users can make use of existing control records and global fields, but cannot create, modify or delete them.

Different groups have different authority, and this can give a choice to a general user. For example:

-   **Group G1** is for regular reporting, so this group cannot create any new components. This applies to general users who login to this environment using group G1.
-   **Group G2** is for update of data, so this group can create any new components required. This applies to general users who login to this environment using group G2.

[//]: # ( Comment on old image - PLEASE KEEP - <img src="../images/Group_Adv_Perm_Create_03.gif" alt="Missing image" width="100" height="100"/> )

In the above example, the general user can **change rights to create items** in the environment by the **choice of group** during login to that environment.

# 20 Group permissions to run a utility

Group members can receive a permission to run utilities.

The utilities available in the SAFR Workbench are:

-   **Batch Activate Lookup Paths.** This utility checks lookup paths are ready to use in an environment, and if possible sets the status to "active". For more, see topic "**Lookup Paths overview**". A link to that overview is under **Related concepts** below.
-   **Batch Activate Views.** This utility checks views are ready to run in the SAFR Performance Engine, and if possible sets the status to "active". For more, see topic "**Views overview**". A link to that overview is under **Related concepts** below.
-   **Migration Utility.** This utility copies selected metadata from a source environment to target environment in the same SAFR Database. For more, see topic "**Migrate metadata overview**". A link to that overview is under **Related concepts** below.

There is one group run permission:

-   **Migrate In**. This provides access to all three utilities:
    -   **Migration Utility** where the target environment is this environment ,
    -   **Batch Activate Lookup Paths** and **Batch Activate Views** in this environment.

The above run permission can be applied to a general user in one more environments. Administrators in an environment always have this run permission.

Different groups have different authority, and this can give a choice to a general user. For example:

-   **Group G1** is for users who run established views and cannot migrate any metadata. Users in this group cannot run any utilities.
-   **Group G2** is for users who can migrate metadata from other environments. Users in this group can run all three utilities.

[//]: # ( Comment on old image - PLEASE KEEP - <img src="../images/Group_Adv_Perm_Utils_02.gif" alt="Missing image" width="100" height="100"/> )

In the above example, the general user can **change rights to run utilities** in the environment by the **choice of group** during login to that environment.

# 30 Groups and edit rights to specific components

Group members receive edit rights to specific components of metadata.

The specific components must be of the following types:

-   Logical File,
-   Logical Record,
-   Physical File,
-   User-Exit Routine,
-   View Folder.

The edit rights possible are:

-   **No rights at all**.
-   **Read** right which allows both display and usage of an item. For example, a user needs the read right to a logical record in order to refer to that logical record in a view.
-   **Modify** right which implies Read as well.
-   **Delete** right which implies the Modify and Read rights as well. This right is also called "**Full**" rights.

The above edit rights for a specific component can be applied to a general userin one or more environments. Administrators always have full rights to all components.

Edit rights can be seen in column "**Rights**" in the **Metadata List**. For example, if you click on "**View Folders**" in the **Navigator**, the Metadata List may appear as follows:

[//]: # ( Comment on old image - PLEASE KEEP - <img src="../images/ER_WB_Mlist_03.GIF" alt="Missing image" width="100" height="100"/> )

A group can have different edit rights to each individual component.

Different groups have different authority, and this can give a choice to a general user. For example:

-   **Group G1** is for reporting, so this group has the read right to a specific logical file.
-   **Group G2** is for update of data, so this group has the delete right \(which is all rights\) to a specific logical file.

[//]: # ( Comment on old image - PLEASE KEEP - <img src="../images/Group_Adv_EditR_01.gif" alt="Missing image" width="100" height="100"/> )

In the above example, the general user can **change access to specific components** in the environment by the **choice of group** during login to that environment.

# 40 Groups can allow administration rights

A group can have **administration rights to an environment**. This means all users in that group become **environment administrators** in that environment.

[//]: # ( Comment on old image - PLEASE KEEP - <img src="../images/Group_Adv_Auth_Admin_05.gif" alt="Missing image" width="100" height="100"/> )

Environment and system administrators have all the create permissions, run permission and edit rights that are possible.

An environment administrator and has almost the same rights as a system administrator. The difference is that an **environment** administrator:

-   Cannot create, read, modify or delete users.
-   Can only modify group permissions and rights. Cannot give administrator access. Cannot change group membership. Cannot create or delete groups.
-   Can only modify the environment record itself for the relevant environment. Cannot create or delete environments.Â Cannot modify environment records where there is no environment administrator access.

# 50 Groups have unique settings for each associated environment

All the above permissions apply separately to each environment associated with the group. For example, if a group G1 is associated with two environments all the above permissions can be set uniquely for each environment.

[//]: # ( Comment on old image - PLEASE KEEP - <img src="../images/Group_Multi_Env_02.gif" alt="Missing image" width="100" height="100"/> )

# 60 How do I create or modify a group?

[//]: # ( Comment on old image - PLEASE KEEP - <img src="../images/Group_Create_Modify_02.gif" alt="Missing image" width="100" height="100"/> )

**System administrators** can do the following tasks:

-   "**Creating groups**",
-   "**Modifying groups**",
-   "**Modifying group membership**",
-   "**Modifying group permissions by group**",
-   "**Modifying group permissions by environment**".

Links to these topics are under **Related tasks** below.

**Environment administrators** can do the following task in the appropriate environment:

-   "**Modifying group permissions by environment**".

A link to that topic is under **Related tasks** below.

# 70 How do I delete a group?

See topic "**Deleting metadata**". A link is under **Related tasks** below.

# 80 Environment Security Report

All users can run this report. To see a report that lists the groups in one or more environments, use one of these topics:

-   FAQ topic "**How do I generate an Environment Security Report?**"
-   Task "**Generating reports**"

A link to the FAQ topic is under "**Related Reference**" below. A link to the task topic is under **Related tasks** below.

For a complete discussion of security, see topic "**WE Security overview**". A link is under **Related concepts** below.

# 90 The best way to use groups

Groups aim to achieve the following goals:

-   **Accuracy:** provide only the appropriate access for users to the relevant environments. Too much access risks unintended update of environments.Â Too little access stops general users from doing their work.
-   **Flexibility:** allow some extra groups for unusual work situations that require unusual access for a short period of time.
-   **Simplicity:** fewer groups means less groups to maintain.

These goals are often in competition: for example to achieve goal of accuracy perfectly may require a separate group for each user which contradicts the goal of simplicity. Your company must find the appropriate choice of groups that balances the above goals. The next heading describes a suggestion.

# 95 Suggestion on groups for a large company using SAFR

If your company has a large number of environments and a large number of users, the following suggestion describes the groups to create:

-   Create a group for the system administrators - for example **YourCo\_System\_Administrators**
-   There are many environments, such as Market\_Research and Data\_Warehouse. Call the environment name **"eee"**. Create two groups per environment:
    -   **eee\_Environment\_Administrators** group - for example **Market\_Research\_Environment\_Administrators**
    -   **eee\_Users** group - for example **Market\_Research\_Users**
-   Group **eee\_Environment\_Administrators** has **administration rights** to that environment only. It is recommended that this group has only one or two members. **This delegates administration of this environment** to the members of this group.
-   Group **eee\_Users** has less rights, such as only read rights to all components of that environment. This group has all other general users for this environment.
-   **Create extra groups as required** where some members of group eee\_Users need more than the minimum rights. These extra groups are created by the system administrators \(and not by members of the eee\_Environment\_Administrators group, who do not have the right to create or modify groups\).

