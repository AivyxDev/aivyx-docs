# User Manual

Complete CLI command reference for Aivyx.

---

## Core Commands

| Command | Description |
|---------|-------------|
| `aivyx genesis` | First-time setup wizard |
| `aivyx run <agent> "<prompt>"` | Single-turn task execution |
| `aivyx chat <agent>` | Interactive multi-turn conversation |
| `aivyx tui [agent]` | Full-screen terminal UI |
| `aivyx voice <agent>` | Real-time voice interaction |

## Agent Management

| Command | Description |
|---------|-------------|
| `aivyx agent list` | List available agent profiles |
| `aivyx agent show <name>` | Display agent profile details |
| `aivyx agent create <name>` | Create a new agent profile |

## Secret Management

| Command | Description |
|---------|-------------|
| `aivyx secret set <key>` | Store an encrypted secret |
| `aivyx secret list` | List stored secret keys |
| `aivyx secret delete <key>` | Remove a stored secret |

## Configuration

| Command | Description |
|---------|-------------|
| `aivyx config show` | Display current configuration |
| `aivyx config set <key> <value>` | Set a configuration value |

## Memory

| Command | Description |
|---------|-------------|
| `aivyx memory search "<query>"` | Semantic search over agent memory |
| `aivyx memory stats` | Memory store statistics |

## MCP Tools

| Command | Description |
|---------|-------------|
| `aivyx mcp add <name> --command "<cmd>"` | Register an MCP server |
| `aivyx mcp list` | List registered MCP servers |
| `aivyx mcp remove <name>` | Remove an MCP server |

## Server & Utilities

| Command | Description |
|---------|-------------|
| `aivyx server start` | Start the HTTP API server |
| `aivyx audit verify` | Verify audit log integrity |
| `aivyx backup` | Create encrypted backup |
| `aivyx self-update` | Update to latest release |

---

## Configuration File

Stored at `~/.aivyx/config.toml`:

```toml
[provider]
type = "Ollama"
base_url = "http://localhost:11434"
model = "llama3.2"

[autonomy]
default_tier = "Trust"
max_tool_calls_per_minute = 60
max_cost_per_session_usd = 5.0

[providers.reasoning]
type = "Ollama"
model = "qwen2.5:72b"
```
