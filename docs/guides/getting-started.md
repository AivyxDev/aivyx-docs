# Getting Started with Aivyx

From zero to chatting with your own AI agent in under 5 minutes.

---

## Installation

### Desktop App (Recommended)

Download the latest release:

→ [**Download Desktop App**](https://github.com/AivyxDev/aivyx-app/releases/latest)

| Platform | Format |
|----------|--------|
| Linux | `.AppImage` (recommended), `.deb` |
| Windows | `.msi`, `.exe` installer |
| macOS | Coming soon |

### CLI (One-Line Install)

```bash
curl -fsSL https://aivyx-studio.com/install.sh | bash
```

---

## First-Time Setup

### Desktop App

1. Launch the app — the Genesis Wizard appears automatically
2. Choose your LLM provider (Ollama for local, or enter an API key for cloud)
3. Set a passphrase to encrypt your data
4. Start chatting!

### CLI

```bash
aivyx genesis
```

---

## Configure Your LLM Provider

### Ollama (Local — 100% Offline)

```bash
ollama pull llama3.2
aivyx config set provider.type Ollama
aivyx config set provider.model llama3.2
```

### OpenAI

```bash
aivyx config set provider.type OpenAI
aivyx config set provider.model gpt-4o
aivyx secret set openai_api_key
```

### Anthropic (Claude)

```bash
aivyx config set provider.type Anthropic
aivyx config set provider.model claude-sonnet-4-20250514
aivyx secret set anthropic_api_key
```

### Google Gemini

```bash
aivyx config set provider.type Gemini
aivyx config set provider.model gemini-2.0-flash
aivyx secret set gemini_api_key
```

---

## Your First Conversation

```bash
# Quick one-shot
aivyx run assistant "Explain closures in Rust"

# Interactive chat
aivyx chat assistant

# Full Terminal UI
aivyx tui
```

---

## Next Steps

- [User Manual](user-manual.md) — Full command reference
- [Skills Guide](skills-guide.md) — 22 built-in skills
- [MCP Guide](mcp-guide.md) — Connect external tools
- [Desktop App Guide](desktop-app.md) — Desktop-specific features
- [Troubleshooting](../../TROUBLESHOOTING.md) — Common issues
