# API Documentation Workflow
- Last Updated: 2025-08-30
- Description: populating the `memory-bank/reference/api_docs/` with technical summaries and roadmaps for libraries
- Tags: meta documentation
- Version: 1.0


This rule defines the workflow for populating the `memory-bank/reference/api_docs/` with technical summaries and roadmaps for libraries.

## Workflow

When requested to document a library or a specific section of its documentation, you MUST follow this process:

### 1. Verify Library & Version

- Scan `memory-bank/reference/api_docs/` to see if the library (e.g., `aws-amplify`, `react`) already exists.
- If a similar entry exists, confirm with the user whether to update it or create a new one.
- Establish a canonical name and version for the library.

### 2. Create/Update the Roadmap (`llms.md`)

The `llms.md` file is the main index for a library's documentation.

- **Action**: Crawl the user-provided documentation page to extract all major navigation links, sections, and sub-sections.
- **Content**: Create a hierarchical list that matches the documentation's structure, with direct links. This is a navigation index, not a prose summary.
- **Save Location**: `memory-bank/reference/api_docs/[LIBRARY_NAME]/[MAJOR_VERSION]/llms.md`.
- **Notify**: Inform the user that the roadmap has been created/updated.

### 3. Create/Update a Section Summary (`llms-[section].md`)

Section summaries are detailed technical overviews of a specific page.

- **Action**: When asked to summarize a specific URL, crawl ONLY that page for its complete technical details.
- **Content**: Write a detailed, prose-style technical summary with code examples, optimized for your own consumption.
- **Save Location**: `memory-bank/reference/api_docs/[LIBRARY_NAME]/[MAJOR_VERSION]/llms-[section].md`.
- **Update Roadmap**: After saving the summary, you MUST add or update the link to it in the main `llms.md` roadmap file.
- **Notify**: Inform the user that the section summary has been created, but DO NOT display the content in the chat.

## Critical Rules

- Do not summarize or paraphrase when creating a roadmap (`llms.md`); it is a navigation index.
- Do not display the content of a section summary in the chat.
- Always check for existing libraries and sections before creating new ones to avoid duplication.
- If you cannot crawl a page or encounter ambiguity, STOP and NOTIFY the user immediately.
