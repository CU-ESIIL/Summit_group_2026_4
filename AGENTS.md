AGENTS.md

This repository is for an ESIIL Project Group called Data Buffs: Wrangling Data using Language Models. The project group is centered around building a generalized workflow for using AI agent to find, extract and harmonize data from diverse resource types to answer questions in environmental science, with an included example case study. The overall goal is to gather datasets contained in open-access publications and datasets, process and harmonize them, so they can be used for larger meta-analyses. The overall workflow will be modular for a variety of fields of study and potential topics, and should work for several different types of data sources, such as tables, data contained in text, etc.

Guidelines for agents:

* Treat this repository as the source of truth.
* Treat the website as a rendered view of repository state.
* Make small, focused edits. Avoid rewriting entire files. New files can be created but this should be well documented.
* Do not change navigation or structure unless explicitly instructed.
* Preserve existing project content and historical context.
* Prefer improving shared systems over one-off fixes.
* Keep documentation and site content in sync.
* Do not introduce complex HTML into markdown pages. Keep participant-facing content Markdown-first, and hide layout or reusable behavior in CSS, hooks, includes, or templates.
* Keep everything editable by non-experts in GitHub.
* Do not add blocking tests for template completeness. Use the site health report for user-facing warnings instead.
* When adding new features, ensure they do not increase user complexity.
* Preserve the homepage as a polished, public-facing, replaceable example, not a long editing manual.
* Keep instructions, file maps, and editing workflows in the instructions pages rather than cluttering the front page.
* Keep final results structured around claims, evidence, confidence, limitations, reusable outputs, and next steps.
* Preserve per-person profile files in `docs/people/` so contributors can edit independently, and keep `docs/_data/people.yml` as an index of profile paths only.
* Preserve BibTeX citation flow through `docs/references.bib` and `[@citationKey]` references.
* Preserve artifact-first editing patterns: image placeholders, raw file replacement links, and clear captions that explain what claim each artifact supports.
* Do not replace scaffold language with project-specific conclusions unless the user explicitly asks for a finished group report.
* After meaningful changes, append an entry to PROMPT_ACTION_LOG.md.

## Repository Purpose

See **tasks.md** for a plain-English description of the harmonization pipeline.
The **tasks.md** file does not contain any specific instructions, but instead should serve as a general reference for aligning the agent goals. Specific instructions (regarding code, etc.) are contained within files structured as `STEPX.md`. The **tasks.md** will instruct you to reference specific step files for detailed instructions on each task.