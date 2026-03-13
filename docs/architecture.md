# Architecture

Aivyx is built as a multi-repository ecosystem with a layered crate architecture.

## Repository Layout

| Repo | Visibility | Description |
|------|-----------|-------------|
| `aivyx-app` | Public | Desktop App releases and downloads |
| `aivyx-docs` | Public | Documentation and guides |
| `aivyx-core` | Public | 10 shared foundation crates (MIT) |
| `aivyx` | Private | Source: Desktop, TUI, server, deployment |
| `aivyx-engine` | Private | Engine: orchestration, enterprise features |

## Crate Graph

```
aivyx-core (Foundation)
├── aivyx-crypto        ← Encryption (HKDF + ChaCha20Poly1305)
├── aivyx-config        ← TOML configuration
├── aivyx-audit         ← Tamper-proof audit log (HMAC chain)
├── aivyx-capability    ← Permission model (RBAC)
├── aivyx-llm           ← LLM providers (OpenAI, Claude, Gemini, Ollama)
├── aivyx-mcp           ← Model Context Protocol tools
├── aivyx-memory        ← Semantic memory + knowledge graph
├── aivyx-agent         ← Agent sessions and tool dispatch
├── aivyx-federation    ← Multi-instance protocol (Ed25519)
└── aivyx-nexus         ← Agent social network

aivyx (Application Layer)
├── aivyx-server        ← HTTP API (Axum), WebSocket, SSE
├── aivyx-task          ← Mission orchestration, DAG execution
├── aivyx-team          ← Nonagon multi-agent collaboration
└── apps/ (Desktop, TUI, Website)
```

## Design Principles

1. **Privacy first** — All data encrypted at rest
2. **Capability attenuation** — Permissions narrow but never widen
3. **Tamper-proof audit** — Every action in an HMAC chain
4. **Provider agnostic** — OpenAI, Anthropic, Gemini, Ollama
5. **Protocol native** — MCP + A2A standards

## Data Flow

```
User (Desktop/TUI/CLI)
      │
      ▼
Engine HTTP API (localhost:1707)
      ├─► Agent Session → LLM + Tools + Memory
      ├─► Mission Orchestrator → DAG + Team Runtime
      └─► Audit Log (tamper-proof)
```

See [Security Model](security.md) for the complete security design.
