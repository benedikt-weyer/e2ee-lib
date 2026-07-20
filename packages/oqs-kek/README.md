# @e2ee-lib/oqs-kek

ML-KEM-768 key-encryption-key adapter for web and React Native applications.

## Install

```sh
npm install @e2ee-lib/oqs-kek
```

The package ships TypeScript source. Configure your application bundler to transpile this dependency.

## Entry Points

```ts
import { createWebOqsKekAdapter } from '@e2ee-lib/oqs-kek/web';

const oqsKek = createWebOqsKekAdapter();
await oqsKek.ready;

const recipient = await oqsKek.deriveDeterministicKeyPair(seed);
const encapsulated = await oqsKek.encapsulate(recipient.publicKey);
const sharedSecret = await oqsKek.decapsulate(encapsulated.cipherText, recipient.privateKey);
```

Use `@e2ee-lib/oqs-kek/web` in browsers. Use `@e2ee-lib/oqs-kek/native` in React Native; it can use a registered native OQS bridge and otherwise falls back to the JavaScript ML-KEM implementation.

The root entry point exports adapter and ML-KEM types plus `bytesToHex` and `hexToBytes`. Run `pnpm --filter @e2ee-lib/oqs-kek typecheck` to check the package.
