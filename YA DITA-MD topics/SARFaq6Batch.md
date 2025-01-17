 

Each application of SAFR typically requires only one batch stream, but if multiple batch streams are required, they are normally run sequentially. If multiple SAFR batch streams for different reporting applications are scheduled to run simultaneously, there could be some excessive resource consumption. One SAFR customer got around this problem by clever scheduling of SAFR batch streams on separate mainframes in their sysplex and by not allowing any more than one SAFR batch stream to executed on one machine at a time. The customer told IBM that they are loosening this restriction as more of their SAFR batch streams are converted to use zIIP features, since they have plenty of extra CPU cycles on their zIIP processors.

Sometimes when building SAFR applications which require a lot of lookup data in memory, paging becomes a consideration. The options for the customer then are to: 1\) redesign the application to reduce the amount of in-memory data needed \(which may also increase elapsed time\), 2\) buy more memory, or 3\) tolerate the paging. One SAFR customer chose to tolerate the paging because the SAFR application was running at a time when the reports it was producing were top priority and the other applications could just wait. Another way to look at it is that the paging subsystem is really very efficient and any alternative technique for performing lookups would have required access of indexed files/tables on disk, increasing elapsed time and actually using more system resources in total.

**Parent topic:**[FAQ](../html/SARFaq0.md)

