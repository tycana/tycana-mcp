<p align="center">
  <img src="tycana-logo.svg" alt="Tycana" width="300">
</p>

<p align="center">
  <strong>AI-native productivity backend — your AI thinks, Tycana remembers.</strong>
</p>

<p align="center">
  <a href="https://www.tycana.com/getting-started/">Get Started</a> &middot;
  <a href="https://www.tycana.com">Website</a> &middot;
  <a href="https://www.tycana.com/mcp/">MCP Docs</a>
</p>

---

## What is Tycana?

Your AI assistant is brilliant but amnesiac. Every conversation starts from zero — no memory of what you captured yesterday, no awareness of what's overdue, no sense of your work patterns. You re-explain your priorities every morning. Tycana fixes this.

Tycana is a productivity backend built for AI reasoning, not human browsing. Connect your AI once via MCP (Model Context Protocol), and every conversation automatically includes your full work picture: active projects, upcoming deadlines, blocked items, and computed intelligence about your patterns.

This isn't another task app with an AI bolted on. There's no UI to check, no lists to reorganize, no weekly reviews to dread. Tycana is infrastructure that sits behind your AI conversation, making every interaction smarter.

<a href="https://glama.ai/mcp/servers/@tycana/tycana">
  <img width="380" height="200" src="https://glama.ai/mcp/servers/@tycana/tycana/badge" alt="Tycana MCP server" />
</a>

## Quick Start

### 1. Sign up

Start a [14-day free trial](https://www.tycana.com/getting-started/) — no credit card required.

### 2. Connect your AI

Add Tycana to your MCP client configuration:

```json
{
  "mcpServers": {
    "tycana": {
      "type": "streamable-http",
      "url": "https://app.tycana.com/mcp",
      "headers": {
        "authorization": "Bearer YOUR_TOKEN"
      }
    }
  }
}
```

Most MCP clients (Claude Desktop, Claude Code, Cursor) support OAuth — just connect and authorize when prompted. The bearer token config above is for clients that don't support OAuth flows.

### 3. Start talking

Just use your AI normally. Say things like:
- "Remind me to update the deployment docs before Friday"
- "Plan my day"
- "How's Project X going?"
- "What should I work on next?"

## Tools

Tycana provides 14 MCP tools:

### Task Management

| Tool | Description |
|------|-------------|
| `capture` | Create a new task, note, or idea with optional project, priority, due date, and effort estimate |
| `complete` | Mark an item as done with an outcome (resolved, wont_do, delegated, deferred) |
| `update_item` | Update any field on an existing item — title, body, priority, due date, project, effort |
| `delete_item` | Permanently delete an item |
| `list_items` | List items filtered by status (active, completed, all), project, or priority |
| `get_item` | Retrieve full details for a specific item by ID |
| `search` | Full-text search across all items |

### Intelligence & Planning

| Tool | Description |
|------|-------------|
| `plan_day` | Generate a prioritized daily plan based on available hours, deadlines, and your work patterns |
| `what_next` | Get a smart recommendation for what to work on based on available time (quick/hour/deep) |
| `review` | Weekly review — surfaces overdue items, stalled work, slip patterns, and velocity trends |
| `get_context` | Pull full context for a scope (today, project, everything) to ground AI responses |

### Organization & Memory

| Tool | Description |
|------|-------------|
| `relate_items` | Create relationships between items (blocks, parent, related) |
| `remember` | Store personal context — preferences, work style, facts your AI should always know |
| `cleanup_project` | Archive or bulk-complete items in a finished project |

## Key Features

- **Persistent memory** — Your AI remembers everything across conversations
- **Computed intelligence** — Velocity tracking, slip rate detection, stale work alerts, effort calibration
- **Confidence-gated signals** — Intelligence only surfaces when backed by enough data
- **Personal context** — Learns your preferences, work style, and priorities over time
- **Calendar feed** — Tasks appear alongside your meetings with effort-based lead times
- **Daily email digest** — Smart-scored briefing of what needs attention
- **Project relationships** — Items connect, block each other, have dependencies
- **Works everywhere** — Claude Code, Claude.ai, ChatGPT, Cursor, any MCP-compatible client

## How It Works

```
You <-> Your AI Assistant <-> MCP <-> Tycana Backend
                                         |
                                    PostgreSQL
                                    (your data)
```

Tycana is a hosted service. Your AI connects to `https://app.tycana.com/mcp` via streamable HTTP with OAuth 2.1 authentication. All data is stored securely and belongs to you — full export and deletion available at any time.

## Pricing

One plan. Everything included.

- **$15/month** or **$150/year** (2 months free)
- 14-day free trial, no credit card required
- No feature tiers, no per-seat pricing, no upsells

## Compatibility

Tycana works with any MCP-compatible client:

- Claude Desktop
- Claude Code (CLI)
- Claude.ai
- ChatGPT (via MCP)
- Cursor
- Windsurf
- Any client supporting streamable HTTP transport

## Links

- [Website](https://www.tycana.com)
- [Getting Started](https://www.tycana.com/getting-started/)
- [Privacy Policy](https://app.tycana.com/privacy)
- [Terms of Service](https://app.tycana.com/terms)
- [Data Processing Agreement](https://app.tycana.com/dpa)

## License

This repository contains documentation and configuration for the Tycana MCP server.
The Tycana service itself is proprietary software. See [Terms of Service](https://app.tycana.com/terms).

This documentation is released under [MIT](LICENSE).