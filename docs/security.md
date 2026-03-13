# Security Model

Aivyx is designed with defense-in-depth security.

## Encryption at Rest

All sensitive data encrypted with **ChaCha20Poly1305** authenticated encryption.

## Key Derivation

```
Passphrase → Argon2id → Master Key (32 bytes)
                          ├── derive_audit_key()   → HMAC key
                          ├── derive_memory_key()  → Memory encryption
                          ├── derive_task_key()    → Task store key
                          └── derive_session_key() → Session key
```

Each derived key uses unique context — compromising one doesn't compromise others.

## Passphrase Handling

- **Never stored** on disk
- Key material zeroed on exit via `secrecy` crate
- Only derived keys held in memory during session

## Tamper-Proof Audit Log

HMAC-chained audit entries with Ed25519 signatures:
```
Entry_N.hmac = HMAC(key, Entry_{N-1}.hmac || event_data)
```
Verify with: `aivyx audit verify`

## Capability Model

- Permissions granted explicitly per-agent
- Capabilities can be narrowed but never widened
- Two autonomy tiers: **Trust** and **Leash**

## Authentication

- Bearer token auth with multi-session support
- Per-IP rate limiting on failed attempts
- Token TTL with proactive refresh (at 80% of TTL)
