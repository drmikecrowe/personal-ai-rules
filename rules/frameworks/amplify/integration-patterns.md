---
title: AWS Amplify Gen 2 Backend - Integration Patterns
last_updated: 2025-08-30
description: Patterns for integrating Amplify with other services (Auth, Storage, Data, Cache, Subscriptions).
tags: amplify
version: 1.0
---

- **Authentication**: Use JWT-based authentication with Cognito groups for admin permissions.
- **Storage**: Store user-specific files in S3 using the path format `[bucket]/receipts/[user-email]/[yyyy-mm-dd]/[guid].[ext]`.
- **Data Model**: Use an embedded data model, with parent documents (e.g., reports) containing all their associated child data (e.g., expense items).
- **Caching**: Use the project's existing Effect-based caching layer in `src/services/AmplifyService/cache.ts` for backend data.
- **Subscriptions**: Implement real-time updates using Amplify subscriptions, ensuring they are synchronized with the caching layer.
