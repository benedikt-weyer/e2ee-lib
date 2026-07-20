# Offline Provider

`@e2ee-lib/offline-provider` supplies a small persistence abstraction for
encrypted note records. It stores note envelopes; encryption and decryption
remain the responsibility of the application.

## Browser

```ts
import { createWebOfflineNotesProvider } from '@e2ee-lib/offline-provider/web';

const provider = createWebOfflineNotesProvider({
  storageKey: 'my-app.offline-notes',
  wasmPath: '/vendor/sql-wasm.wasm',
});

await provider.initialize();
```

## React Native

```ts
import { createNativeOfflineNotesProvider } from '@e2ee-lib/offline-provider/native';
```

The native provider is backed by Expo SQLite. The browser provider uses `sql.js`
and local storage for persistence metadata.

Use the provider as a local cache and sync queue. Your application still owns
network transport, conflict policy, authentication, and ciphertext handling.
