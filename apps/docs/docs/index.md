# E2EE Libraries

This repository publishes platform-neutral TypeScript packages for applications
that need local key derivation, encrypted payload handling, offline data, and
realtime invalidation.

## Packages

| Package | Purpose |
| --- | --- |
| `@e2ee-lib/e2ee-auth` | Password and token credential derivation, payload encryption, and KEK/DEK helpers |
| `@e2ee-lib/oqs-kek` | Web and native ML-KEM KEK adapters |
| `@e2ee-lib/offline-provider` | Browser and Expo offline-note persistence |
| `@e2ee-lib/realtime` | Validated reconnecting websocket subscriptions |
| `@e2ee-lib/import-export-suite` | Encrypted note backup and import helpers |

The packages do not provide a backend, user interface, authentication session
store, or application data model. Consumers own those boundaries.
