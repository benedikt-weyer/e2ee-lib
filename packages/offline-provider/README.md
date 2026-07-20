# @e2ee-lib/offline-provider

Offline-first note storage and change tracking for browser and Expo/React Native applications.

## Install

```sh
npm install @e2ee-lib/offline-provider
```

The package ships TypeScript source. Configure your application bundler to transpile this dependency.

## Entry Points

```ts
import { createWebOfflineNotesProvider } from '@e2ee-lib/offline-provider/web';

const provider = createWebOfflineNotesProvider({
  storageKey: 'my-notes',
  wasmPath: '/vendor/sql-wasm.wasm',
});

await provider.init();
```

Use `@e2ee-lib/offline-provider/web` for browser storage backed by `sql.js` and `localStorage`. Serve the `sql.js` WASM file at the configured `wasmPath`.

Use `@e2ee-lib/offline-provider/native` for Expo/React Native storage backed by `expo-sqlite`:

```ts
import { createNativeOfflineNotesProvider } from '@e2ee-lib/offline-provider/native';

const provider = createNativeOfflineNotesProvider({ databaseName: 'my-notes.db' });
await provider.init();
```

The root entry point exports the provider class and shared note, database, and synchronization types. Run `pnpm --filter @e2ee-lib/offline-provider typecheck` to check the package.
