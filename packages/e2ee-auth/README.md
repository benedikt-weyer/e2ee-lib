# @e2ee-lib/e2ee-auth

End-to-end encryption primitives for password-derived credentials, encrypted payloads, API tokens, and ML-KEM key-encryption keys.

## Install

```sh
npm install @e2ee-lib/e2ee-auth
```

The package ships TypeScript source. Configure your application bundler to transpile this dependency.

## Entry Points

```ts
import { deriveCredentials, encryptString } from '@e2ee-lib/e2ee-auth/web';
import { deriveCredentials as deriveNativeCredentials } from '@e2ee-lib/e2ee-auth/native';
```

The root entry point resolves to the web implementation. Use the explicit `web` or `native` entry point for portable applications.

The web entry point uses Web Crypto and `libsodium-wrappers-sumo`. The native entry point requires `react-native-libsodium` and the native OQS KEK adapter from `@e2ee-lib/oqs-kek/native`.

## Example

```ts
import {
  createPasswordSalt,
  deriveCredentials,
  deriveKekKeyPair,
  encryptStringWithAsymmetricKek,
} from '@e2ee-lib/e2ee-auth/web';

const salt = await createPasswordSalt();
const credentials = await deriveCredentials('person@example.com', 'correct horse battery staple', salt);
const kek = await deriveKekKeyPair(credentials.cryptKey);
const encrypted = await encryptStringWithAsymmetricKek('private note', kek.kekPublicKey);
```

Run checks with `pnpm --filter @e2ee-lib/e2ee-auth test` and `pnpm --filter @e2ee-lib/e2ee-auth typecheck`.
