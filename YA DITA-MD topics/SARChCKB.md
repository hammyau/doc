 

# 10 What are Common Key Buffers?

See help topic "**Common Key Buffers overview**". A link to that overviews is under **Related concepts** below.

# 20 Metadata required

The following metadata items must exist in your SAFR database.

|Metadata|Notes|
|--------|-----|
|GVBXRCK|This read user-exit routine is installed as part of the SAFR install. This user-exit routine must be defined in SAFR Workbench WE. If your company requires a different name to GVBXRCK then apply the appropriate name where GVBXRCK appears in this help topic.|
|GVBXLCK|This lookup user-exit routine is installed as part of the SAFR install. This user-exit routine must be defined in SAFR Workbench WE. If your company requires a different name to GVBXLCK then apply the appropriate name where GVBXLCK appears in this help topic.|
|Physical files|Each physical file for the Common Key Buffer view needs to have **GVBXRCK** defined as the read exit.|
|Logical records|There are two requirements:1.  All logical records in a Common Key Buffer view need a prefix area of 11 bytes added to the front. The prefix consists of:

    -   Entity ID of 8 bytes
    -   Partition ID of 2 bytes
    -   Category ID or 1 byte
2.  For a lookup in a Common Key Buffer view, the target logical record must have **GVBXLCK** defined as the lookup exit.

|

# 30 Executable items required

The following items must be installed on your mainframe system running SAFR.

|Executable item|Notes|
|---------------|-----|
|GVBXRCK|This read user-exit routine is installed as part of the SAFR install.|
|GVBXLCK|This lookup user-exit routine is installed as part of the SAFR install.|

# 40 File and PE Job stream requirements

|Job|Notes|
|---|-----|
|To be completed|To be completed|

# 50 Other requirements

|Issue|Notes|
|-----|-----|
|To be completed|To be completed|

# 90 Troubleshooting

See help topic "**Troubleshooting: Common Key Buffers**". A link to that topic is under **Related reference** below.

