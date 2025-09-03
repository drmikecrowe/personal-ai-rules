---
title: Performance Optimization Best Practices
last_updated: 2025-09-03
description: Comprehensive performance optimization guidelines for frontend, backend, and database optimization
tags: performance, optimization, profiling, scalability, potential-rule
version: 1.1
---

## Core Principles

- **Measure First**: Profile and measure before optimizing.
- **Strategy**: Optimize the common case, avoid premature optimization, and minimize resource usage.
- **Automate**: Integrate performance tests into CI/CD.

## Frontend

- **DOM**: Minimize DOM manipulations, use stable keys in lists.
- **Assets**: Compress images, minify/bundle code, use cache headers, and lazy load.
- **JS**: Avoid blocking the main thread, debounce/throttle events, and prevent memory leaks.

## Backend

- **Algorithms**: Choose efficient data structures and algorithms. Avoid O(n^2).
- **Concurrency**: Use async I/O and thread pools.
- **Caching**: Use in-memory caches (Redis, Memcached) for hot data.

## Database

- **Queries**: Use indexes, `EXPLAIN`, and avoid `SELECT *` and N+1 queries.
- **Schema**: Normalize for writes, denormalize for reads. Use efficient data types.
- **Transactions**: Keep them short.
