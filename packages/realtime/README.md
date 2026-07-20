# @e2ee-lib/realtime

Reconnectable WebSocket client for encrypted note change events.

## Install

```sh
npm install @e2ee-lib/realtime
```

The package ships TypeScript source. Configure your application bundler to transpile this dependency.

## Usage

```ts
import { subscribeToNoteEvents } from '@e2ee-lib/realtime';

const subscription = subscribeToNoteEvents({
  accessToken,
  baseUrl: 'https://api.example.com',
  onError: console.error,
  onEvent: (event) => {
    console.log(event.kind, event.noteId);
  },
});

subscription.close();
```

`baseUrl` may use `http`, `https`, `ws`, or `wss`; the client converts HTTP URLs to WebSocket URLs and defaults to `/api/notes/events`. Supply `WebSocketCtor` when the runtime does not provide a global `WebSocket` implementation.

Run `pnpm --filter @e2ee-lib/realtime typecheck` to check the package.
