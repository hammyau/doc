 

# 10 What is a group?

A group is a collection of users in the SAFR Workbench.

The function of the group is to **provide access to one or more environments** associated with the group. The group can have **different access to each environment** associated with the group. All the users in that group get the access authorities of that group.

[//]: # ( Comment on old image - PLEASE KEEP - <img src="../images/Group_Concept_04.gif" alt="Missing image" width="100" height="100"/> )

**System administrators define groups** to be used by general users and environment administrators.

**General users login using a group.** The group gives users access to the environment for that session \(and may make the general user an environment administrator\). If a user needs to change group for that environment, then that user clicks **File -\> Return to login...** to specify a new group for the same environment. All work for general users is done using one group and one environment per session.

Groups allow your company to achieve these benefits:

-   **Apply access authorities once to a group** instead of configuring each member of the group individually for each environment. This saves time in applying access authorities and solving problems with access.
-   When setup, a general user can have a **choice of group**, which allows the user to **change their access to an environment** depending on their work situation. For example, a user may normally work with only read access to the physical files in an environment, and occasionally the user changes group to obtain the authority to modify those physical files \(for example to remove a duplicate transaction\). Most users are likely to have no choice of group during login.

# 20 How do I use a group?

General users select an environment when they **login** to the SAFR Workbench, and the user **may have a choice of group** for that environment. General users become environment administrators only when a group provides the necessary access authority. Only a system administrator can change group authorities so that members of a group are environment administrators.

[//]: # ( Comment on old image - PLEASE KEEP - <img src="../images/Env_Usage_and_rights_02.gif" alt="Missing image" width="100" height="100"/> )

System administrators are not affected by groups and so the group field on the login screen is always grey.

For more about login, see topic "**Logging into the SAFR Workbench**". A link to this topic is under **Related tasks** below.

# 30 How do I know which group to use?

|If you are a ...|then ...|
|----------------|--------|
|General User|If you have a **choice of group during login**, see your system administrator. Otherwise use the only group given to you.|
|Environment Administrator|You must use the group given to you, because that is the group that provides the environment administrator access to you.|
|System Administrator|Groups do not affect system administrators during login.|

# 50 Group authorities and environments

Every environment must be associated with at least one **group**. A general user or environment administrator gain **access to an environment** by becoming a **member of a group**.

**Groups have authorities** to access one or more environments. Group authorities for each environment can be any of the following:

-   **Administrator** access authorities. This allows members of that group to be environment administrators.
-   **General user** access authorities, as follows:
    -   Edit rights to specific components. Example: rights to read/modify/delete a specific logical file.
    -   Create permissions for types of components Example: create logical files permission.
    -   Run permission for utilities.

[//]: # ( Comment on old image - PLEASE KEEP - <img src="../images/Group_Auth_01.gif" alt="Missing image" width="100" height="100"/> )

One group may have only **read access** to all components in an environment and no create rights. Another group may have **more rights** to individual components. User rights in an environment are controlled by the group selected during login to that environment.

For more, see topics "**Groups - advanced overview**" and "**Environments - advanced overview**". Links to these overviews are under **Related concepts** below.

For a complete discussion of security, see topic "**WE Security overview**". A link is under **Related concepts** below.

