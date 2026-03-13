# Troubleshooting

Common issues and solutions for the Aivyx ecosystem.

---

## LLM Provider Connection

### "No provider configured" or empty responses

1. **Check your provider is set:**
   ```bash
   aivyx config show
   ```
   Look for the `[provider]` section. If missing, run:
   ```bash
   aivyx init
   ```

2. **Verify your API key is stored:**
   ```bash
   aivyx secret list
   ```

3. **Set a missing API key:**
   ```bash
   # OpenAI
   aivyx secret set openai_api_key
   # Anthropic (Claude)
   aivyx secret set anthropic_api_key
   # Google Gemini
   aivyx secret set gemini_api_key
   ```

### Ollama (Local) not connecting

- Ensure Ollama is running: `ollama serve`
- Default URL: `http://localhost:11434`
- Pull your model: `ollama pull llama3.2`

### API key is set but still getting errors

- **OpenAI**: Verify at [platform.openai.com/api-keys](https://platform.openai.com/api-keys)
- **Anthropic**: Verify at [console.anthropic.com/settings/keys](https://console.anthropic.com/settings/keys)
- **Gemini**: Verify at [aistudio.google.com/apikey](https://aistudio.google.com/apikey)
- Ensure the key has sufficient credits/quota

---

## Desktop App

### Desktop App won't start or shows blank screen

1. Check the engine sidecar started correctly
2. Try restarting the app
3. If the database is locked, close all Aivyx instances and retry

### "Unauthorized" or 401 errors

- Click the lock icon and re-enter your passphrase
- The Desktop and TUI can run simultaneously (multi-session support as of v0.3.3)

### Can't connect to LLM provider from Desktop

The Desktop App uses the same engine as the CLI:
```bash
aivyx run assistant "Hello, are you there?"
```
If the CLI works but Desktop doesn't, check for firewall rules blocking localhost:1707.

---

## TUI (Terminal UI)

### TUI shows "connection refused"

Ensure the engine is running:
```bash
aivyx server start
```
Default port is 1707.

---

## Database & Data

### "Database is locked" error

1. Close all Aivyx instances (Desktop, TUI, CLI)
2. Check for orphaned processes: `ps aux | grep aivyx`
3. Kill any remaining: `kill <PID>`
4. Retry

### Resetting your data

```bash
aivyx backup          # Backup first
rm -rf ~/.aivyx       # Reset
aivyx init            # Re-initialize
```

---

## Building from Source

### Prerequisites

- **Rust** 1.80+ (`rustup update stable`)
- **Node.js** 18+ and npm (for Desktop app)
- **System libs** (Linux): `libssl-dev pkg-config libgtk-3-dev libwebkit2gtk-4.1-dev libappindicator3-dev`

---

## Feedback & Support

- 🐛 **Bug Reports** — [Open an Issue](https://github.com/AivyxDev/aivyx-app/issues/new)
- 💡 **Feature Requests** — [Request a Feature](https://github.com/AivyxDev/aivyx-app/issues/new)
- 💬 **Community** — [GitHub Discussions](https://github.com/AivyxDev/aivyx-app/discussions)
- 📧 **Email** — [support@aivyx-studio.com](mailto:support@aivyx-studio.com)
