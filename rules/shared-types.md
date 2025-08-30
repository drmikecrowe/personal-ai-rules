# Shared Types and Schemas
- Last Updated: 2025-08-30
- Tags: shared typescript
- Version: 1.0


The `shared/` directory contains generated code and MUST NOT be edited manually.

## Source of Truth

- The single source of truth for all data models is the set of JSON Schemas in `schema/*.json`.
- These schemas define all objects used in the application.

## Generation

- To regenerate all shared types and schemas, run: `pnpm run types`
- This script uses `quicktype` to generate:
  - TypeScript types into `shared/types/<name>.ts`
  - `effect/Schema` definitions into `shared/schemas/<name>.ts`
- Any changes to data models MUST be made in the `schema/*.json` files, followed by running the generation script.

## Usage

- **MUST** rely on the generated Effect Schemas in `shared/schemas/` to parse and validate data at application boundaries (e.g., API responses).
- Avoid writing manual mapping functions; use the schemas for object conversion.

## Workflow

1.  Update or add a `schema/*.json` file.
2.  Run `pnpm run types`.
3.  Run `pnpm lint:wip` and `pnpm test:unit` to fix any breakages.
4.  Commit the changes to both `schema/` and the regenerated `shared/` files together.
