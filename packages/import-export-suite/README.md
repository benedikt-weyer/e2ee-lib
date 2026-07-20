# @e2ee-lib/import-export-suite

Encrypted note backup export, inspection, and import helpers for web and Expo/React Native applications.

## Install

```sh
npm install @e2ee-lib/import-export-suite
```

The package ships TypeScript source. Configure your application bundler to transpile this dependency.

## Entry Points

```ts
import {
  exportImportExportSuite,
  importImportExportSuite,
  inspectImportExportSuite,
} from '@e2ee-lib/import-export-suite/web';
```

Use `@e2ee-lib/import-export-suite/web` in browsers and `@e2ee-lib/import-export-suite/native` in Expo/React Native. The native entry point requires `expo-crypto` and `react-native-libsodium`; the web entry point requires Web Crypto.

## API

- `exportImportExportSuite` creates an encrypted backup document from notes and a password.
- `inspectImportExportSuite` reads backup metadata without importing it.
- `importImportExportSuite` decrypts and validates a backup document.

The root entry point resolves to the web implementation. Run checks with `pnpm --filter @e2ee-lib/import-export-suite test` and `pnpm --filter @e2ee-lib/import-export-suite typecheck`.
