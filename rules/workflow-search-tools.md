---
title: Modern Search Tools Usage
last_updated: 2025-09-03
description: Instructions for using fd and ripgrep (rg) instead of find and grep for faster, more efficient searches
tags: search-tools, fd, ripgrep, rg, performance, workflow
version: 1.1
---

## Overview

- Always prefer `fd` (for file search) and `ripgrep` (`rg`) (for content search) over `find` and `grep`.

## Usage

- **`fd`**: Find files by name, extension, or pattern.
  - `fd "*.ts"`
- **`rg`**: Search text content in files.
  - `rg "function"`

## Benefits

- **Speed**: 3-10x faster.
- **Smart Defaults**: Respects `.gitignore`.
- **Better Syntax**: More intuitive.

## Fallback

- If `fd` or `rg` are not available, use `find` and `grep -r`.
