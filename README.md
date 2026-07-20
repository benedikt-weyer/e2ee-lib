# E2EE Libraries

Publishable E2EE support packages shared by applications:

- `@e2ee-lib/e2ee-auth`
- `@e2ee-lib/oqs-kek`
- `@e2ee-lib/offline-provider`
- `@e2ee-lib/realtime`
- `@e2ee-lib/import-export-suite`

Use `pnpm test` and `pnpm typecheck` to validate the workspace. Every commit pushed to `main` receives a commit-subject-derived SemVer tag and publishes all packages at that version, with `oqs-kek` published before `e2ee-auth`.
