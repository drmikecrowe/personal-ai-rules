---
title: API Documentation Workflow
last_updated: 2025-09-03
description: populating the `memory-bank/reference/api_docs/` with technical summaries and roadmaps for libraries
tags: meta documentation
version: 1.1
---

## Workflow

1. **Verify Library**: Check `memory-bank/reference/api_docs/` for existing library docs. Confirm with user if update or new.
2. **Create/Update Roadmap (`llms.md`)**:
    - Crawl docs page to extract navigation links.
    - Create a hierarchical index with direct links.
    - Save to `memory-bank/reference/api_docs/[LIBRARY_NAME]/[MAJOR_VERSION]/llms.md`.
3. **Create/Update Section Summary (`llms-[section].md`)**:
    - Crawl specific URL for technical details.
    - Write a detailed prose summary with code examples.
    - Save to `memory-bank/reference/api_docs/[LIBRARY_NAME]/[MAJOR_VERSION]/llms-[section].md`.
    - Update the main `llms.md` with a link to the new summary.

## Critical Rules

- Roadmaps are navigation indexes, not summaries.
- Do not display section summary content in chat.
- Check for existing docs to avoid duplication.
- If crawling fails, STOP and NOTIFY.
