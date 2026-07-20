# OQS KEK

`@e2ee-lib/oqs-kek` provides the ML-KEM adapter layer used by the E2EE auth
package. It exposes separate web and native entry points.

```ts
import { createWebOqsKekAdapter } from '@e2ee-lib/oqs-kek/web';
```

```ts
import { createNativeOqsKekAdapter } from '@e2ee-lib/oqs-kek/native';
```

The adapter is responsible for key encapsulation and decapsulation primitives.
Applications should normally use it through `@e2ee-lib/e2ee-auth`; consume it
directly only when implementing a compatible KEK workflow.

The package does not persist private key material or select recipients. Those
are consumer responsibilities.
