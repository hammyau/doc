 

# 10 What is a "column formula"?

The above phrase means that a column in your view is based on a formula to calculate the value for that column.

Column formulas use a feature called **Extract Column Assignment logic text.** This is described in the next section.

# 20 Extract Column Assignment logic text

For an introduction, see topic "**Logic text 2: Extract Column Assignment overview**". A link to that overview is under "**Related concepts**" below.

For details of the syntax and how to create this logic text, see topic "**Logic text 2: Extract Column Assignment**". A link to this topic is under **Related reference** below.

# 30 Metadata required

The following metadata items must exist in your SAFR database.

|Metadata|Notes|
|--------|-----|
|Extract Column Assignment logic text inside a view|The logic text must be written for the specific column and specific view and the specific source file.|

# 40 File and PE Job stream requirements

|Job|Notes|
|---|-----|
|Run the view|PE executes the Extract Column Assignment logic text as part of the processing of the view.|

# 90 Troubleshooting

See help topic "**Troubleshooting: Column formula**". A link to that topic is under **Related reference** below.

