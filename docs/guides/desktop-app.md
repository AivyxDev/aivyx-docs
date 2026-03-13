# Desktop App Guide

The Aivyx Desktop App provides a visual interface for everything Aivyx can do.

---

## Installation

→ [**Download**](https://github.com/AivyxDev/aivyx-app/releases/latest)

- **Linux**: `.AppImage` (recommended) or `.deb`
- **Windows**: `.msi` or `.exe` installer

---

## First Launch

1. **Genesis Wizard** — Choose LLM provider, enter API key, set passphrase
2. **Lock Screen** — On subsequent launches, enter passphrase to unlock

## Architecture

Built with **Tauri v2** (Rust) + **SvelteKit** (Svelte 5). The engine runs as a sidecar process on `localhost:1707`.

## Features

- **Chat** — Interactive conversations with markdown rendering
- **Missions** — Create and monitor multi-step task execution
- **Settings** — Provider config, API key management, agent profiles

## Auto-Updates

Checks for updates automatically on launch via GitHub Releases.

## Multi-Client Support

As of v0.3.3, Desktop and TUI can run simultaneously with independent sessions.

## Troubleshooting

See [TROUBLESHOOTING.md](../../TROUBLESHOOTING.md) for Desktop App issues.
