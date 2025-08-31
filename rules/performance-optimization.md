# Performance Optimization Best Practices
- Last Updated: 2025-08-31
- Description: Comprehensive performance optimization guidelines for frontend, backend, and database optimization
- Tags: performance, optimization, profiling, scalability, potential-rule
- Version: 1.0

## Core Performance Principles

### Measurement-First Approach
- **Measure First, Optimize Second**: Always profile and measure before optimizing. Use benchmarks, profilers, and monitoring tools to identify real bottlenecks. Guessing is the enemy of performance.
- **Pro Tip**: Use tools like Chrome DevTools, Lighthouse, New Relic, Datadog, Py-Spy, or your language's built-in profilers.

### Optimization Strategy
- **Optimize for the Common Case**: Focus on optimizing code paths that are most frequently executed. Don't waste time on rare edge cases unless they're critical.
- **Avoid Premature Optimization**: Write clear, maintainable code first; optimize only when necessary. Premature optimization can make code harder to read and maintain.
- **Minimize Resource Usage**: Use memory, CPU, network, and disk resources efficiently. Always ask: "Can this be done with less?"
- **Prefer Simplicity**: Simple algorithms and data structures are often faster and easier to optimize. Don't over-engineer.

### Documentation and Monitoring
- **Document Performance Assumptions**: Clearly comment on any code that is performance-critical or has non-obvious optimizations.
- **Understand the Platform**: Know the performance characteristics of your language, framework, and runtime.
- **Automate Performance Testing**: Integrate performance tests and benchmarks into your CI/CD pipeline. Catch regressions early.
- **Set Performance Budgets**: Define acceptable limits for load time, memory usage, API latency, etc. Enforce them with automated checks.

## Frontend Performance

### Rendering and DOM
- **Minimize DOM Manipulations**: Batch updates where possible. Frequent DOM changes are expensive.
- **Virtual DOM Frameworks**: Use React, Vue, or similar efficiently—avoid unnecessary re-renders.
- **Keys in Lists**: Always use stable keys in lists to help virtual DOM diffing. Avoid using array indices as keys unless the list is static.
- **Avoid Inline Styles**: Inline styles can trigger layout thrashing. Prefer CSS classes.
- **CSS Animations**: Use CSS transitions/animations over JavaScript for smoother, GPU-accelerated effects.

### Asset Optimization
- **Image Compression**: Use tools like ImageOptim, Squoosh, or TinyPNG. Prefer modern formats (WebP, AVIF) for web delivery.
- **SVGs for Icons**: SVGs scale well and are often smaller than PNGs for simple graphics.
- **Minification and Bundling**: Use Webpack, Rollup, or esbuild to bundle and minify JS/CSS. Enable tree-shaking to remove dead code.
- **Cache Headers**: Set long-lived cache headers for static assets. Use cache busting for updates.
- **Lazy Loading**: Use `loading="lazy"` for images, and dynamic imports for JS modules/components.

### JavaScript Performance
- **Avoid Blocking the Main Thread**: Offload heavy computation to Web Workers.
- **Debounce/Throttle Events**: For scroll, resize, and input events, use debounce/throttle to limit handler frequency.
- **Memory Leaks**: Clean up event listeners, intervals, and DOM references. Use browser dev tools to check for detached nodes.
- **Efficient Data Structures**: Use Maps/Sets for lookups, TypedArrays for numeric data.
- **Avoid Global Variables**: Globals can cause memory leaks and unpredictable performance.

### Framework-Specific Tips

#### React
- Use `React.memo`, `useMemo`, and `useCallback` to avoid unnecessary renders.
- Split large components and use code-splitting (`React.lazy`, `Suspense`).
- Avoid anonymous functions in render; they create new references on every render.
- Profile with React DevTools Profiler.

#### Vue
- Use computed properties over methods in templates for caching.
- Use `v-show` vs `v-if` appropriately (`v-show` is better for toggling visibility frequently).
- Lazy load components and routes with Vue Router.

## Backend Performance

### Algorithm and Data Structure Optimization
- **Choose the Right Data Structure**: Arrays for sequential access, hash maps for fast lookups, trees for hierarchical data.
- **Efficient Algorithms**: Use binary search, quicksort, or hash-based algorithms where appropriate.
- **Avoid O(n²) or Worse**: Profile nested loops and recursive calls. Refactor to reduce complexity.
- **Batch Processing**: Process data in batches to reduce overhead (e.g., bulk database inserts).
- **Streaming**: Use streaming APIs for large data sets to avoid loading everything into memory.

### Concurrency and Parallelism
- **Asynchronous I/O**: Use async/await, callbacks, or event loops to avoid blocking threads.
- **Thread/Worker Pools**: Use pools to manage concurrency and avoid resource exhaustion.
- **Avoid Race Conditions**: Use locks, semaphores, or atomic operations where needed.
- **Bulk Operations**: Batch network/database calls to reduce round trips.

### Caching Strategies
- **Cache Expensive Computations**: Use in-memory caches (Redis, Memcached) for hot data.
- **Cache Invalidation**: Use time-based (TTL), event-based, or manual invalidation. Stale cache is worse than no cache.
- **Distributed Caching**: For multi-server setups, use distributed caches and be aware of consistency issues.
- **Cache Stampede Protection**: Use locks or request coalescing to prevent thundering herd problems.

### Language-Specific Tips

#### Node.js
- Use asynchronous APIs; avoid blocking the event loop (e.g., never use `fs.readFileSync` in production).
- Use clustering or worker threads for CPU-bound tasks.
- Profile with `clinic.js`, `node --inspect`, or Chrome DevTools.

#### Python
- Use built-in data structures (`dict`, `set`, `deque`) for speed.
- Profile with `cProfile`, `line_profiler`, or `Py-Spy`.
- Use `multiprocessing` or `asyncio` for parallelism.
- Use `lru_cache` for memoization.

#### TypeScript/JavaScript
- Use efficient data structures and avoid deep object cloning.
- Implement proper memory management and cleanup.
- Use Web Workers for CPU-intensive tasks.

## Database Performance

### Query Optimization
- **Indexes**: Use indexes on columns that are frequently queried, filtered, or joined. Monitor index usage and drop unused indexes.
- **Avoid SELECT ***: Select only the columns you need. Reduces I/O and memory usage.
- **Parameterized Queries**: Prevent SQL injection and improve plan caching.
- **Query Plans**: Analyze and optimize query execution plans. Use `EXPLAIN` in SQL databases.
- **Avoid N+1 Queries**: Use joins or batch queries to avoid repeated queries in loops.

### Schema Design
- **Normalization**: Normalize to reduce redundancy, but denormalize for read-heavy workloads if needed.
- **Data Types**: Use the most efficient data types and set appropriate constraints.
- **Partitioning**: Partition large tables for scalability and manageability.
- **Archiving**: Regularly archive or purge old data to keep tables small and fast.

### Transactions
- **Short Transactions**: Keep transactions as short as possible to reduce lock contention.
- **Isolation Levels**: Use the lowest isolation level that meets your consistency needs.
- **Avoid Long-Running Transactions**: They can block other operations and increase deadlocks.

## Code Review Checklist for Performance

- [ ] Are there any obvious algorithmic inefficiencies (O(n²) or worse)?
- [ ] Are data structures appropriate for their use?
- [ ] Are there unnecessary computations or repeated work?
- [ ] Is caching used where appropriate, and is invalidation handled correctly?
- [ ] Are database queries optimized, indexed, and free of N+1 issues?
- [ ] Are large payloads paginated, streamed, or chunked?
- [ ] Are there any memory leaks or unbounded resource usage?
- [ ] Are network requests minimized, batched, and retried on failure?
- [ ] Are assets optimized, compressed, and served efficiently?
- [ ] Are there any blocking operations in hot paths?
- [ ] Is logging in hot paths minimized and structured?
- [ ] Are performance-critical code paths documented and tested?

## Integration with Core Principles

This performance protocol enhances existing rules:
- **Code Review Process**: Include performance review in internal expert consultation
- **Problem-Solving**: Apply performance-first approach to debugging and optimization
- **Testing**: Include performance test cases and benchmarks
- **Transparency**: Explicitly state performance assumptions and trade-offs

## When to Apply This Rule

**HIGH PRIORITY:**
- Applications with strict performance requirements
- High-traffic web applications and APIs
- Real-time systems and data processing pipelines
- Mobile applications with resource constraints
- Systems handling large datasets

**MODERATE PRIORITY:**
- Standard web applications
- Backend services and microservices
- Database-heavy applications
- User-facing interfaces

## Success Criteria

✅ Performance bottlenecks are identified through profiling before optimization
✅ Code follows performance best practices for the target platform
✅ Performance tests are included in CI/CD pipeline
✅ Performance assumptions and critical paths are documented
✅ Resource usage is optimized without sacrificing code maintainability

**Confirmation Emoji**: 🐐 (when performance optimization rule is active)
