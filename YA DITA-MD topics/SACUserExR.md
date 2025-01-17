 

# 10 Short name is "exit"

The term "**exit**" is simply the short name for "**user exit routine**".Â Both terms are used interchangeably in this documentation.

The term "**user-exit routine**" is commonly used in WE. The term "**exit**" is more commonly used in PE.

# 20 What is a user-exit routine?

A user-exit routine is a program specifically written for your company, which performs some unique and necessary computing task. There are four types of user-exit routine:

-   **Read** - use for special processing during a read of your mainframe data. For example, SAFR can only **read encrypted data** with the help of a read user-exit routine.Â 

    Read user-exit routines run in the extract phase.

-   **Lookup** - use for special processing in a step for a Lookup Path. For example, SAFR can only handle **exceptions for some ranges of key values** with the help of a lookup user-exit routine.

    Lookup user-exit routines run in the extract phase.

-   **Write** - use for special processing during a write of your mainframe data. For example, SAFR can only **write encrypted data**with the help of a write user-exit routine. Also called "**output**" user-exit routines.

    Write user-exit routines run in the extract phase.

-   **Format** - use for special processing during output of reports. For example, a format user-exit routine might customize jumping to new pages in certain places in a report.

    Format user-exit routines run in the format phase.


[//]: # ( Comment on old image - PLEASE KEEP - <img src="../images/UER_Concept_02.gif" alt="Missing image" width="100" height="100"/> )

# 30 How do I use a user-exit routine?

[//]: # ( Comment on old image - PLEASE KEEP - <img src="../images/UER_Usage_and_Rights_02.gif" alt="Missing image" width="100" height="100"/> )

User-Exit Routines are used in views and physical files- see these topics:

-   "**Physical Files overview**",
-   "**Views overview**",
-   "**Views - advanced overview**",
-   "**Creating physical files**",
-   "**Creating views**",
-   "**Modifying physical files**",
-   "**Modifying views**".

Links to the overviews are under **Related concepts** below. Links to the other topics are under **Related tasks** below.

# 40 How do I know which user-exit routine to use?

**See your system or environment administrator** for advice on user-exit routines in your environment.

# 50 How do I create or modify a user-exit routine?

[//]: # ( Comment on old image - PLEASE KEEP - <img src="../images/UER_Create_Modify_02.gif" alt="Missing image" width="100" height="100"/> )

System administrators and environment administrators can always **create or modify user-exit routines**.

General users can **create or modify user-exit routines** if the group for login has the following authorities:

-   **Create User-Exit Routine** permission in the relevant environment.
-   **Modify or Delete rights to the relevant user-exit routines** in that environment.

For more on these authorities, see topics "**Groups overview**" , "**Groups - advanced overview**" and "**WE Security overview**". Links to these overviews are under **Related concepts** below.

Once the group has the above authorities, users in that group can **create or modify user-exit routines** by using the tasks below, which are **administrator tasks:**

-   **Creating user-exist routines**,
-   **Modifying user-exit routines**.

Links to these topics are under **Related tasks** below.

# 90 How do I delete a user-exit routine?

See topic "**Deleting metadata**". A link is under **Related tasks** below.

