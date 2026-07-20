# Import/export Suite

`@e2ee-lib/import-export-suite` creates and reads encrypted note backups.

```ts
import {
  exportImportExportSuite,
  importImportExportSuite,
} from '@e2ee-lib/import-export-suite/web';
```

Use `/web` in browser applications and `/native` in Expo or React Native.
The package serializes encrypted note documents; it does not authenticate a
user, upload backups, or decide where exported files are stored.

Before importing, validate that the backup belongs to the expected application
and retain the user-facing confirmation flow in the consumer application.
