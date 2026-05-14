# Step 1

This files contains specific instructions for how the agent should handle processes handled during step 1.

## Code

All code generaterd by the agent during this step should be saved in /workflows/STEP1/code

## Outputs

All outputs should be saved in the /workflows/STEP1/output

## Log

Log all user prompts and actions taken by the agent into /workflows/STEP1/PROMPT_ACTION_LOG.md

## USER INPUTS

- For each of the following inputs, succinctly prompt the user for their preferences
- If a prompt is marked as Mandatory, the user must provide a response
- If a prompt is marked as optional, the user may choose skip it or leavew it blank
- If the user provides input or response that does not answer the given prompt, please kindly re ask the prompt

Mandatory Input: Topic or discipline defined by the user.
Mandatory Input: Open access journal.
Optional Input: Range of publication dates.
Optional Input: Spatial scale or target region of interest (state, county, custom boundary, or bounding box).
Optional Input: User-defined selection criteria (e.g., language, impact factor).

Here are some example inputs priovided by a user:

Agent: "For what topic or discipline would you like to find data?"
User: "I would like to perform a metaanalsis of morphology of California's native wildflowers"

Agent: "Which open access journal(s) would you like to search for available data?"
User: "PLOS One, bioXriv, BioMed Central"

Agent: "Would you like to specify the range of publication dates?"
User: "No"

Agent: "Would you like to specify the spatial scope or extent?"
User: "Yes, please limit studies that include data from the state of California"

Agent: "Would you like to provide any additional criteria?"
User: "Yes, please include all papers that are in English or Spanish"

Once all mandatory inputs are provided, ad optional inputs are passed or skipped, please proceed with the following tasks.

## Task 1 - Determine Access To Journal(s)

For the journals specified by the user, determine agent's access and ability to access and download associated data.

If at least one journal is inaccessible and at least one other is accessible, pause the workflow and display a failure error message describing which journal(s) were inaccessible.

For example: "Nature is not accessible to the agent. PLOS ONE is accessible to the agent. Would you like to proceed with journals specified earlier, or refine your input?"

If no journals provided by the user are accessible, do not proceed without additional journals input by the user.

## Task 2 - Find relevant articles


