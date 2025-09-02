---
title: React Component Architecture - Zero Mapping Logic
last_updated: 2025-08-30
description: Keeping business logic for data transformation out of React components.
tags: react effect
version: 1.0
---

- Components MUST NOT contain business logic for mapping or transforming data.
- Data transformation and mapping should be handled in the `Effect` service layer before being passed to the UI or sent to a state machine.
