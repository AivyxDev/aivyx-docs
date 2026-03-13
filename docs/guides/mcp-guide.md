# MCP Guide — Model Context Protocol

Connect external tools to your Aivyx agent via [MCP](https://modelcontextprotocol.io/).

## Adding MCP Servers

```bash
# GitHub
aivyx mcp add github --command "npx -y @modelcontextprotocol/server-github"

# Filesystem
aivyx mcp add filesystem --command "npx -y @modelcontextprotocol/server-filesystem ~/Documents"

# SQLite
aivyx mcp add sqlite --command "npx -y @modelcontextprotocol/server-sqlite ~/data/mydb.sqlite"
```

## Managing Servers

```bash
aivyx mcp list          # List registered servers
aivyx mcp tools github  # View discovered tools
aivyx mcp remove github # Remove a server
```

## Transport Modes

| Mode | Description | Use Case |
|------|-------------|----------|
| **stdio** | Subprocess communication | Local tools (most common) |
| **SSE** | Server-Sent Events over HTTP | Remote tool servers |
| **Streamable HTTP** | HTTP with streaming | Modern MCP servers |

```bash
# SSE example
aivyx mcp add remote-tool --sse-url https://my-server.com/mcp
```

Aivyx's MCP client supports OAuth 2.1 with PKCE for secure server authentication.
