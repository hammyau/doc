 

# 10 What is metadata?

Metadata is a group of data items that describe the work that SAFR will do for your company. Metadata is how you "tell SAFR what to do", and describes part of the mainframe data in your company. A Metadata item can also be called a metadata component.

To describe the users of the SAFR Workbench, you need these types of metadata items:

-   **General users** who login and configure SAFR to produce results for your company.
-   **Groups** with members that are general users. A group can make general users become environment administrators.
-   **Environment administrators** who prepare environments for general users.
-   **System administrators** who create environments and nominate environment administrators and also prepare environments for general users.

To configure SAFR to produce results for your company, users create and modify these types of metadata items:

-   **Views** to describe the results that SAFR must produce.
-   **Logical files** to describe collections of input and output data.
-   **Logical records** to describe record layouts for logical files.
-   **Physical files** to describe actual datasets on the mainframe systems in your company.
-   **Global fields** to describe common fields of data in the mainframe systems in your company. For example, a customer identification number might be a global field.
-   **Lookup paths** to describe how one or more source files can lookup a target file by using fields of data.
-   **Control records** to control how a view processes data.
-   **View folders** to contain collections of views.
-   **User-exit routines** to performs some unique and necessary computing task specifically for your company.
-   **Environments** to contain all the items above in logical collections, such as **Sales** or **Accounts\_Receivable**.

For example, your SAFR Workbench needs general users, groups and environments. System and environment administrators setup the environments with and other items so that general users can do work. General users create views and lookup paths that you need for SAFR to produce results.

# 20 Items of metadata

An item of metadata is a particular example, such as a particular view.

Every metadata item has the following:

-   A **name**.

    For example, a logical file might be named "**Sales\_USA**".

-   An **ID** number.

    For example, logical file "Sales\_USA" might have an ID number of **123**. ID numbers in SAFR are often written inside square brackets: **\[123\]**.

    Often, both the name and ID are given in the format "name\[ID\]", for example "**Sales\_USA\[123\]**".

-   A **type**.

    For the example of "**Sales\_USA\[123\]**" the type is **logical file**.


Items of metadata can be created in the SAFR Workbench, where most of the screens allow creating or editing metadata items.

# 30 How metadata item types are related

[//]: # ( Comment on old image - PLEASE KEEP - <img src="../images/Metadata_05.gif" alt="Missing image" width="100" height="100"/> )

The diagram above shows the metadata types in SAFR. The lines show where metadata types are related. The relationship may be one to many or many to many, and may be only in one direction. If there is no line then there is no direct relationship.

System and environment administrators can create and modify all the items types shown above.

General users can create and modify the shaded items, which produce the most obvious results for SAFR. General users can have extra authorities granted by membership of a group. The extra authorities can allow a general user to create and modify other items. Granting of extra authorities is a way of implementing specialized job roles for general users in your company.

All the items in the diagram above have overview topics. Authorities are discussed in topic "**Groups overview**".

Links to overview topics under **Related concepts** below.

# 50 General users can choose the metadata to see

General users get access to environments and metadata by the group selected during login, and can potentially become an environment administrator. This contrasts with system administrators who have unlimited access to every environment and every item of metadata.

This means that general users can choose the metadata to see on screens in the workbench:

-   EITHER see ALL metadata items, and items are grey if the user has no rights to that item
-   OR see ONLY the metadata items where the user has rights.

For more about this, see topic "**What metadata do I want to see?**" A link to this topic is under **Related reference** below.

# 60 Permissions to access metadata

Different users of the SAFR Workbench have different permissions to login to environments and access metadata.

For details of how these permissions work, see topics "**Groups overview**" and "**Groups - advanced overview**". Links to those overviews are under **Related concepts** below.

# 70 Reports on metadata

All users can access these reports. Use one of these topics:

-   FAQ topic "**How do I generate an Environment Security Report?**
-   FAQ topic "**How do I generate a Logical Record Report?**
-   FAQ topic "**How do I generate a Lookup Path Report?**
-   FAQ topic "**How do I generate a View Properties Report?**
-   FAQ topic "**How do I generate a View Column Report?**
-   FAQ topic "**How do I generate a View Column PIC Report?** \(this gives the COBOL PIC clause appropriate for each column in the view\)
-   Task "**Generating reports on metadata**"

Links to the FAQ topics are under "**Related Reference**" below. A link to the task topic is under **Related tasks** below.

# 80 Searching lists of metadata

In some places in the SAFR Workbench, there are lists of metadata. In some cases, these lists can be searched to assist working with a long list of items.

For instructions on how to search these lists, see topic "**Searching lists of metadata**".

A link to this topic is under **Related tasks** below.

# 90 How do I delete metadata?

See topic "**Deleting metadata**". A link is under **Related tasks** below.

# 95 More information on metadata

See topic "**Metadata - advanced overview**" . A link to this overview is under **Related concepts** below.

