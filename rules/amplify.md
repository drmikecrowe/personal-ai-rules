---
title: AWS Amplify Gen 2 Backend
last_updated: 2025-09-03
description: Rules and patterns for using AWS Amplify Gen 2.
tags: amplify, aws, backend
version: 1.0
---

## CLI Usage

- **Gen 2 Only**: This project uses Amplify Gen 2. Your knowledge of Gen 1 is likely outdated.
- **Verify Commands**: Verify all CLI commands against the current Amplify Gen 2 documentation before use.

## Backend Implementation

- All new backend functions, APIs, or Lambdas **MUST** be implemented using Amplify's Function or API patterns.
- Default to the Function/API workflow and file structure used by Amplify Gen 2 in this repository.

## Integration Patterns

- **Authentication**: Use JWT-based authentication with Cognito groups for admin permissions.
- **Storage**: Store user-specific files in S3 using the path format `[bucket]/receipts/[user-email]/[yyyy-mm-dd]/[guid].[ext]`.
- **Data Model**: Use an embedded data model, with parent documents containing all their associated child data.
- **Caching**: Use the project's existing Effect-based caching layer in `src/services/AmplifyService/cache.ts`.
- **Subscriptions**: Implement real-time updates using Amplify subscriptions, synchronized with the caching layer.
