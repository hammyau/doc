 

# 10 Symptoms

|Symptom|Details of symptom|Possible problems|
|-------|------------------|-----------------|
|MR88 **return code = 0008** and the MR88 Report has: **GVBMR88 \(67\) "VDP" TABLE OVERFLOW**

|This is the entire contents of the MR88 report.|VDP size too small|

# 40 Possible problems

|Problem|Details of problem|Solutions|
|-------|------------------|---------|
|VDP size too small|MR88 needs more memory to store the VDP file.|Increase VDP size|

# 80 Solutions

|Solution|Details of solution|
|--------|-------------------|
|Increase VDP size|Increase the value for MR88 PARM option **VDPTBLMX**. See topic "**Program Runbook: MR88 Format Data**" in the section on PARM options. A link to that topic is under **Related reference** below.|

