# Security Boundary

These libraries are local cryptographic and storage building blocks. They are
designed so raw passwords and decrypted content do not need to leave the
application runtime.

## Library responsibilities

- derive authentication and encryption material locally
- encrypt and decrypt typed payloads
- wrap random data-encryption keys for password-derived or recipient KEKs
- provide offline record persistence and realtime transport primitives

## Consumer responsibilities

- obtain and persist salts, sessions, and backend identifiers
- protect local `cryptKey` material for the lifecycle of the application
- define recipient, sharing, rotation, and migration policy
- authenticate and authorize backend requests
- validate application-specific data before encrypting or after decrypting

The packages do not make a backend end-to-end encrypted by themselves. The
backend must be designed to store and transport ciphertext without requiring
plaintext or raw password access.
