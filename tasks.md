# Data Set Harmonization Tasks

This document describes the steps needed to gather multiple data sets from literature and harmonize them so they can be directly compared and integrated together. It is tool-agnostic — the same pipeline applies whether you use command-line utilities, Python, R, or any other stack.

---

# Step 1

Refer to `STEP1.md` for instructions on performing the following tasks.

## User Inputs

Prompt the user to provide the following inputs:

1. **Mandatory Input:** Topic or discipline defined by the user.
2. **Mandatory Input:** Open access journal.
3. **Optional Input:** Range of publication dates.
4. **Optional Input:** Spatial scale or target region of interest (state, county, custom boundary, or bounding box).
5. **Optional Input:** User-defined selection criteria (e.g., language, impact factor).

## Tasks

### Task 1
Determine whether the selected open access journal can be accessed.

- If the journal cannot be accessed:
  - Pause the workflow.
  - Display a failure message.

### Task 2
Find relevant articles based on the user’s inputs.

- Check whether articles include available datasets.

### Task 3
Search for linked datasets referenced in articles or associated available data.


---

# Step 2

Refer to `STEP2.md` for instructions on performing the following tasks.

## Tasks

### Task 4
For every paper found:

- Download the associated dataset.
- Include:
  - DOI
  - Citation
  - Dataset URL

### Task 5
Build a dataframe for each publication or dataset that was downloaded.

### Task 6
For each dataframe:

- Output the first 5 rows for user evaluation.
- State:
  - Total number of rows
  - Metadata
  - Citations
  
### Task 7
Confirm Dataset Relevance
Identify the columns, headers, or types of data for future outputs
Determine whether to retain the raw dataframes    

---

# Step 3

Refer to `STEP3.md` for instructions on performing the following tasks.

### Task 8
Across dataframes, conduct semantic matching, translate terms, normalize, convert, and standardize data.
Produce a metadata table for user confirmation.

### Task 9
Merge data into a single data frame.
Present data to the user and save the final output.
