# Releases

Every push to `main` runs the release workflow.

The workflow derives a SemVer tag from commit subjects:

| Subject | Result |
| --- | --- |
| `feat: ...` | minor version bump |
| `feat(scope)!: ...` | major version bump |
| any other subject | patch version bump |

It creates and pushes a `vX.Y.Z` tag, tests and typechecks the workspace, then
publishes all packages at that version. `@e2ee-lib/oqs-kek` is published before
`@e2ee-lib/e2ee-auth` so the latter's packed workspace dependency resolves to
the same registry version.

The workflow skips publication when the pushed commit already has its SemVer
release tag.
