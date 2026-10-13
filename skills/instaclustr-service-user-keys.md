---
name: instaclustr-service-user-keys
description: Create an Instaclustr service user and manage its API keys (generate, revoke) for automation.
api: instaclustr:instaclustr-api
operations:
- createServiceUser
- generateApiKey
- revokeApiKey
generated: '2026-10-13'
method: generated
source: openapi/instaclustr-openapi.yml
---
# Service user API keys

1. `createServiceUser` to create a non-human user for automation.
2. `generateApiKey` to issue that service user an API key of the type you need.
3. `revokeApiKey` to revoke a key when it is no longer needed.

Rules: these are write operations with no documented idempotency key, so do not retry `createServiceUser` or `generateApiKey` blindly. Revoking a key cannot be undone; issue a new key instead.
