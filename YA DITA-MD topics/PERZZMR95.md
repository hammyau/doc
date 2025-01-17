 

# 10 MR95 error messages

Error message codes are in the form:

**GVB999X**

where **999** is a message number and **X** is one of the following:

-   **C = Critical**
-   **E = Error**
-   **I = Information**
-   **N = Notice**
-   **S = Severe**
-   **U = Unrecoverable**
-   **W = Warning**

|MR95RPT error message|Other details|Solution or Possible Problem\(s\)|
|---------------------|-------------|---------------------------------|
|**\*\* GVB000E GVBMR95 Message not known**|Â |See your IBM representative - this error needs investigation by IBM.|
|**\*\* GVB001S GVBMR95 Identify macro failed**|Â |See your IBM representative - this error needs investigation by IBM.|
|**\*\* GVB002I GVBMR95 TTT threads started**|TTT is the number of threads.|This is an informational message only.|
|**\*\* GVB003S GVBMR95 Attach macro failed XXX**|XXX is the macro name.|See your IBM representative - this error needs investigation by IBM.|
|**\*\* GVB004U GVBMR95 Event file thread abended TTT**|The abend applies to thread number TTT.|Investigate and fix the abend.|
|**\*\* GVB099X GVBMR95 x**|Â |Â |
|**\*\* GVB099X GVBMR95 x**|Â |Â |
|**\*\* GVB099X GVBMR95 x**|Â |Â |
|**\*\* GVB099X GVBMR95 x**|Â |Â |
|**\*\* GVB099X GVBMR95 x**|Â |Â |
|Â |Â |Â |
|Â |Â |Â |
|Â |Â |Â |
|Â |Â |Â |
|Â |Â |Â |
|Â |Â |Â |
|Â |Â |Â |
|Â |Â |Â |
|**\*\* GVB041U GVBMR95 Incorrect trace execution parameter**|MR95 has **RC = 0008**|Solution: Fix TRACE parameter in MR95 config file.Find the details in section [80 Solutions](PERZZMR95.md#80)

|

# 20 Other symptoms

|Symptom\(s\)|Other details|Solution or Possible Problem\(s\)|
|------------|-------------|---------------------------------|
|SOC1 in MR95 step.|**IEC130I MR95BILL DD STATEMENT MISSING**|Solution: Insert MR95BILL DD.Find the details in section [80 Solutions](PERZZMR95.md#80)

|

# 40 Possible problems

This section describes problems that may underly various errors and symptoms. Available solutions are identified.

|Problem|Details|Solutions|
|-------|-------|---------|
|To be completed|To be completed|To be completed|

# 80 Solutions

|Solution|Details|
|--------|-------|
|Fix TRACE parameter in MR95 config file|Ensure coding it either **TRACE=Y** or **TRACE=N** in the config file. For more details, see the section on MR95 Parameters in topic "**Program Runbook: MR95 Reference Data**" or topic "**Program Runbook: MR95 Extract Data**". Links to those topics are under **Related reference** below.

|
|Insert MR95BILL DD|Insert the following in the MR95 step:```
//MR95BILL DD DUMMY        

```

|

