---
title: Documentation Workflow
last_updated: 2025-09-03
description: Proactive knowledge capture practices for troubleshooting, lessons learned, and complex debugging
tags: documentation, knowledge-capture, troubleshooting, lessons-learned
version: 1.1
---

## Proactive Documentation

- **Memory Bank**: `memory-bank/` is the single source of truth. Consult it first.
- **Post-Resolution**: Proactively offer to document errors in `troubleshooting_log.md` and complex tasks in `lessons_learned.md`.

## Complex Debugging

- **Log Files**: For issues surpassing the three-strike rule, create a detailed log in `./ai-debugging-log/{Problem}_{TROUBLESHOOTING/RESEARCH}_LOG.md`.
- **Log Structure**: Include date, issue, context, attempts, solution, and prevention.

## Knowledge Capture

- **Real-Time**: Document decisions and reasoning as they're made.
- **Quality**: Be specific, concise, searchable, and timely.
