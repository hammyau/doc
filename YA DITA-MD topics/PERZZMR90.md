 

# 10 Symptoms

|Symptom|Details of symptom|Possible problems|
|-------|------------------|-----------------|
|No views in output VDP|MR90 output VDP has no views.|MR90 excluded all views|
|Output XLT file is empty or very short|MR90 output XLT file may be empty, have only two instructions or something similar.|MR90 excluded all views|
|**USER ABEND U1099** from step after MR90or **return code 02** from MR90 step

|SYSOUT contains these messages:

```
**GVBMR90: too many arguments given.** 
```

|Missing or incorrect PARM options for MR90|
|Wrong views in output VDP|The output VDP file contains more views than required.|MR90 did not correctly exclude views|

# 40 Possible problems

|Problem|Details of problem|Solutions|
|-------|------------------|---------|
|Missing or incorrect PARM options for MR90|Even if the SYSOUT error message says 'too many arguments given", it may be that a required PARM option is missing.Â Alternatively, an incorrect PARM option may be encoded.|Review PARM options|
|MR90 did not correctly exclude views|The input config file for MR90 does not contain the appropriate VIEWID and/or FOLDERID parameters. These parameters must be under the section \[VIEWS TO RUN\], be spelled correctly, and refer to relevant id numbers that are already in the input VDP file.|Review input parameters|
|MR90 excluded all views|MR90 coded some VIEWID and/or FOLDERID parameters in the input config file, and this resulted in no views being selected by MR90. This can occur if the values for these two parameters do not refer to values that are already in the input VDP file.|Review input parameters|

# 80 Solutions

|Solution|Details of solution|
|--------|-------------------|
|Review input parameters|See section on the input configuration file in topic "**Program Runbook: MR90 Logic Table Generator**". A link to that topic is under **Related reference** below.

|
|Review PARM options|See section on the PARM options in topic "**Program Runbook: MR90 Logic Table Generator**". A link to that topic is under **Related reference** below.

|

