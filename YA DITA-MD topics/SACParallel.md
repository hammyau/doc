 

# 10 What is parallelism?

One of the biggest advantages of SAFR is the speed of producing results. Parallelism means allowing SAFR to run multiple processes in parallel, so that the overall work is done faster.

There are four methods to create parallelism in SAFR:

1.  **Physical File Partitions.** Partition a logical file into many physical files. With careful implementation, each physical file can be processed in parallel with the others.
2.  **DB2 Key Range Partitions.** This method accesses DB2 Tables which have been partitioned by Key Ranges using SQL. With careful implementation, this speeds access to DB2.
3.  **DB2 via VSAM Access.** This method accesses the VSAM partitions that underly DB2. This allows the fastest sequential access to data in DB2.
4.  **Pipes** allow multiple views to run in parallel.

Each of these methods is discussed below.

# 20 Physical File Partitions \(1\): choose a field

A logical file may consist of a single physical file. To make SAFR run faster, partition the physical file into many physical files, based on a field that you choose.

A good example is to split the **USA\_Sales** physical file into a physical sales file for each state in the USA. Here the field for the partitions is the state of each sales transaction. There is still one logical USA\_Sales file and this now consists of 50 physical files. SAFR can run a separate process for each physical file, so the USA\_Sales logical file can be processed by 50 processes in parallel, instead of by one process working on the entire logical file.

Notice that all the partitions are still needed to process all the sales. For field partitions, normally all partitions are included in processing.

[//]: # ( Comment on old image - PLEASE KEEP - <img src="../images/LF_Example_02.gif" alt="Missing image" width="100" height="100"/> )

Partitions needs to be planned early in the design for implementing SAFR.

# 30 Physical File Partitions \(2\): time periods

Another way to partition a logical file is to create physical files for time periods.

An example is to split the USA\_Sales physical file into three physical files, as shown below:

[//]: # ( Comment on old image - PLEASE KEEP - <img src="../images/Time_Partitions_USA_Sales_01.gif" alt="Missing image" width="100" height="100"/> )

The advantages of this partition are that SAFR only needs to read the relevant time partitions for a report, and can ignore the rest.

Partitions needs to be planned early in the design for implementing SAFR. The time partitions can be combined with fields partitions - for example, each state can have separate time partitions.

# 40 DB2 Key Range Partitions

A DB2 table can have different key ranges stored in different partitions. The Physical File \(in the SAFR Workbench\) for the DB2 table must have **DB2 via SQL** and the SQL text must have **WHERE** clauses for the different key ranges. Each of the different key ranges can be processed in parallel by SAFR, which is faster than processing the entire table as a single file.

[//]: # ( Comment on old image - PLEASE KEEP - <img src="../images/DB2KeyRange_01.gif" alt="Missing image" width="100" height="100"/> )

This method requires careful work to ensure that the file contain strictly only the key ranges specified, and all the possible keys are covered by the ranges.

# 50 DB2 via VSAM access

Any DB2 table has underlying VSAM partitions. SAFR can process the underlying VSAM partitions directly in parallel. The DB2 Physical File \(in the SAFR Workbench\) must be marked **DB2 via VSAM** and some changes made to the JCL that runs the Performance Engine to identify all the VSAM partitions.

[//]: # ( Comment on old image - PLEASE KEEP - <img src="../images/DB2VSAM_01.gif" alt="Missing image" width="100" height="100"/> )

This is the fastest method for SAFR to access DB2 in a sequential way.

# 60 Pipes

The pipe itself is a virtual file that stays in memory and is passed between views without Input/Output. Pipes are defined as a Physical File of type **Pipe** in the SAFR Workbench.

See the topic "**Pipes overview**". A link to that overview is under **Related concepts** below.

