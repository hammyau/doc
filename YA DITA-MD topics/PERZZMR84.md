 

# 10 Symptoms

|Symptom|Details of symptom|Possible problems|
|-------|------------------|-----------------|
|**USER ABEND U1099** from step after MR84or **return code 08** from MR84 step

|MR84 Report contains these messages:

```
**Fatal Error at file DD:XMLIN,
     line 1, char 22
Message: An exception occurred! 
     Type:RuntimeException,
Message:EBCDIC files must provide
     an encoding= string  ** 
```

|Incorrect encoding in XML file|

# 40 Possible problems

|Problem|Details of problem|Solutions|
|-------|------------------|---------|
|Incorrect encoding in XML file|MR86 did not specify parameter **ENCODING=IBM-1047** in the \[XML\] section of the MR86 input configuration file. The XML file created by MR86 does not use a character set expected by MR84.See section on the input configuration file in topic "**Program Runbook: MR86 VDP Builder**". A link to that topic is under **Related reference** below.

|Recreate XML file|

# 80 Solutions

|Solution|Details of solution|
|--------|-------------------|
|Recreate XML file|Rerun from the select phase \(MR86\). Ensure the input configuration file for MR86 has parameter **ENCODING=IBM-1047** in the \[XML\] section See topic "**Program Runbook: MR86 VDP Builder**". A link to that topic is under **Related reference** below.

|

