 

# 10 What is a view?

A view configures the SAFR Performance Engine to produce results for your company. A view is a description of an input file\(s\), processing specifications and an output file. Views are prepared in the SAFR Workbench.

At a simplified level, the main components of a view are:

-   The **input file\(s\)** called a view source file\(s\).
-   The **output file** which can be a flat file or hardcopy report. A flat file can be a delimited file \(for example, a CSV file\).
-   The **columns** which are the fields in the output file. Each column is one of the following:

    -   **EITHER** a source file field,
    -   **OR** a constant,
    -   **OR** a formula which is implemented in **logic text**,
    -   **OR** a lookup field which uses a **lookup path**.
    If the view has a format phase, then at least one column must be part of the **sort key.**


For an introduction to logic text and lookup paths, see topics "**Logic text overview**" and "**Lookup path overview**". For an introduction to phases, see topic "**SAFR phases overview**". Links to all these topics are under **Related concepts** below.

A view is the most complex component in the SAFR metadata. This overview \(and the advanced overview\) provide an introduction only. You must create or modify a view to become familiar with all the data involved in a view.

# 20 What are the possible inputs and outputs of a view?

[//]: # ( Comment on old image - PLEASE KEEP - <img src="../images/View_inputs_outputs_02.gif" alt="Missing image" width="100" height="100"/> )

All of the **inputs** shown above are **metadata** components in SAFR - see "**Metadata Overview**". A link to that topic is under **Related concepts** below.

# 30 How is a view used?

Views are run in the SAFR Performance Engine.

A view must be "**Active**" before the view can be run in the Performance Engine. A view is created, modified and activated by work in the SAFR Workbench.

# 40 How do I know which view to use?

In the SAFR Workbench, look at views for the environments you have access to. If the appropriate view does not exist, either copy and/or modify an existing view, or create a new view.

# 45 How do I copy a view?

See topic "**Copying metadata**". A link is under **Related tasks** below.

# 50 How do I create or modify a view?

[//]: # ( Comment on old image - PLEASE KEEP - <img src="../images/View_Create_Modify_02.gif" alt="Missing image" width="100" height="100"/> )

General users with at leastmodify rights to the relevant view folder\(s\) can create, modify and delete views in the view folder\(s\). Administrators can always do these tasks in any view folder in the environment. For instructions on creating or modifying views, see these topics:

-   "**Creating views**",
-   "**Modifying views**".

Links to these topics are under **Related tasks** below.

# 60 Metadata reports on views

To see a **report on selected views**, use one of these FAQ topics:

-   "**How do I generate a View Properties Report?**"
-   "**How do I generate a View Column Report?**"
-   "**How do I generate a View Column PIC Report?**"

A link to each FAQ topic is under "**Related Reference**" below.

# 90 How do I delete a view?

See topic "**Deleting metadata**". A link is under **Related tasks** below.

# 95 More information

See topic "**Views - advanced overview**". A link to this overview is under **Related concepts** below.

