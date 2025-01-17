 

# 10 What is the log file?

A log file is a trace of database activity in WE. This file is useful when debugging problems and when contacting IBM for help with a problem.

A simple example is below:

[//]: # ( Comment on old image - PLEASE KEEP - <img src="../images/WE_log_Ex_01_Genl_Rpt.gif" alt="Missing image" width="100" height="100"/> )

Note the following:

-   The first 21 lines down to "**INFO: Compiler version**" indicate a successful login to WE.
-   The last two lines are normal when creating a new view \(in this case called "General\_Report"\). The messages indicate that the name "General\_Report" is not used for any existing view, so this name is available for a new view.

# 20 Opening a log file inside WE

See topic "**Opening a log file**". A link to that topic is under **Related tasks** below.

# 30 Where is the WE log file?

Use topic "**Changing Log Path**" to display the current log file path. A link to that topic is under **Related tasks** below.

The first time the workbench executes, a default log file path is provided. Users can change to a different path by using the topic "**Changing Log Path**".

In a virtualization environment such as Citrix, a default log file path can be provided by the administrators.

For more on virtualization, see topic "**Workbench overview**". A link to that topic is under **Related concepts** below.

# 40 Naming system for log files

WE log files are named:

|Â |**WE.cycle.log.instance**|Example: **WE.1.log**Note the "instance" part of the name is blank in this example.

|

The parts of the naming system are explained below:

|Naming component|Notes|
|----------------|-----|
|WE|Always these letters|
|cycle|**Cycle** indicates which session of the workbench, as follows:

-   Cycle starts at 0 and then counts 1, 2 or 3 and so on.
-   **Cycle 0** means the **current** instance of a session in the workbench.
-   **Cycle 1** means the **previous** session in the workbench. Cycle 2 means the session before, and so on.
-   When your session ends, and you start a new session later, the **names of existing log files change**. For the current session, the log file is **WE.0.log** by WE. After you finish this session and start a new session later, the log file is renamed to **WE.1.log** by WE. As new sessions finish and start, the log files continue to change name.

|
|log|Always these letters|
|instance|**Instance** indicates multiple sessions running on your workstation at the same time, as follows:

-   Instance starts at **blank**, and then is a number: 1, 2 or 3 and so on.
-   **Instance blank** means the **first** of any multiple instances in the workbench. If you never run multiple sessions at the same time, then the instance is always blank.
-   **Instance 1** means the **second multiple** session running at the same time. Instance 2 means the third of multiple session, and so on.
-   For example, for the first current session, the log file is **WE.0.log** and the second instance running at the same time is named **WE.0.log.1** by WE. A third multiple instance is named **WE.0.log.2**by WE.

As explained for cycle, after all these sessions end and a new session starts later, those log files are renamed to **WE.1.log** and **WE.1.log.1** and **WE.1.log.2** by WE. Notice that the cycle number changes but the instance numbers do not change.


|

