# Getting Started

## Documentation development

Install the docs dependencies once, then run the app from the workspace root:

```sh
python3 -m pip install -r apps/docs/requirements.txt
pnpm docs:dev
```

Install only the packages your application uses:

```sh
pnpm add @e2ee-lib/e2ee-auth @e2ee-lib/oqs-kek
```

Use explicit platform entry points so the runtime requirement is clear:

```ts
import { deriveCredentials, encryptString } from '@e2ee-lib/e2ee-auth/web';
// React Native: import from '@e2ee-lib/e2ee-auth/native'
```

For an offline browser note store, add `@e2ee-lib/offline-provider` and serve
the `sql.js` WASM file at the `wasmPath` supplied to the web provider.

For React Native, use the `/native` entry points and ensure the native
dependencies required by the selected package are installed in the app.

## Integration sequence

1. Generate or retrieve a per-account password salt in your application.
2. Derive local credentials with `deriveCredentials()`.
3. Send only the derived authentication material to your backend.
4. Keep the `cryptKey` local and use it to encrypt, decrypt, and rewrap data.
5. Store the returned encrypted payload objects without changing their fields.

See [E2EE Auth](e2ee-auth.md) for the complete API boundary.
