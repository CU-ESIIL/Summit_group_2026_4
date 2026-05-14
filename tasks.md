Data Set Harmonization Tasks. This document describes the steps needed to gather multiple data sets from literature and harmonize so they can be directly compared and harmonised together. It is tool-agnostic — the same pipeline applies whether you use command-line utilities, Python, R, or any other stack.
Step 1
Refer to STEP1.md for instructions on performing the following tasks. 

Prompt the user to provide the following inputs: 
1. Clarify that this is a mandatory input. Topic or discipline that the user defines. 
2. Clarify that this is a mandatory input. Open access journal.
3. Clarify that this is an optional input. Range of publications dates. 
4. Clarify that this is an optional input. Spatial scale or target region of interest (state, county, custom boundary, or bounding box).
5. Clarify that this is an optional input. User defined selection criteria (e.g., language, impact factor). 

Task 1: Determine whether you can access the open access journal chosen by user. If no journal can be accessed, stop and display a failure message.
Task 2: Find relevant articles based on the user’s inputs. Check whether articles have available datasets.

Step 2
Task 3: Search for linked datasets referenced in articles or associated available data. 
Task 4: For every paper found, download associated dataset. Include DOI, citations and URL for data.
Task 5: Build a data frame for each publication/dataset that was downloaded. 
Task 6: Output the first 5 rows of data for each dataframe for user to evaluate. State the total number of rows and metadata or citations. 
