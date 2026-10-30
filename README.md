# Build Your Own Personal Agent

**Build your own agent. Understand the pieces. Choose your boundaries.**

A curated map of open-source projects, architectural patterns, and building blocks for creating your own Personal Agent.

This is not another agent framework. It helps you explore the ecosystem, understand how the pieces fit together, and build an agent that works the way you want.

## How a Personal Agent is Built

Think in components, not frameworks.

| Layer | Responsibility | Examples |
|---|---|---|
| Interface | Where you interact | Telegram, Discord, Web |
| Gateway | Connects channels to agents | Bot servers, messaging bridges |
| Runtime | Executes agent logic | Pi, LangGraph, Agents SDK |
| Memory | Stores context and knowledge | Files, databases, vector stores |
| Tools | Connects external capabilities | MCP, APIs, integrations |
| Computer Use | Interacts with software | Browser Use, Skyvern |
| Scheduling | Runs tasks proactively | Cron, workflow engines |
| Infrastructure | Runs and secures the system | Docker, VPS, local machine |

These are composable building blocks, not mandatory layers. Choose what you need. Replace what you don't.

## Explore the Ecosystem

### Personal Agent Projects
- [OpenBot](https://github.com/CopilotKit/OpenBot)
- [Rakazo](https://github.com/elie222/rakazo)
- [OpenClaw](https://github.com/openclaw/openclaw)

### Agent Runtimes
- [Pi](https://github.com/badlogic/pi-mono)
- [OpenAI Agents SDK](https://github.com/openai/openai-agents-python)
- [LangGraph](https://github.com/langchain-ai/langgraph)
- [AutoGen](https://github.com/microsoft/autogen)

### Messaging & Interfaces
- [Pi Telegram Server](https://github.com/ken196502/pi-telegram-server)
- [grammY](https://github.com/grammyjs/grammY)
- [Telegraf](https://github.com/telegraf/telegraf)
- [Discord.js](https://github.com/discordjs/discord.js)

### Tools & Integrations
- [Model Context Protocol](https://modelcontextprotocol.io/)
- [Browser Use](https://github.com/browser-use/browser-use)
- [Skyvern](https://github.com/Skyvern-AI/skyvern)
- [n8n](https://github.com/n8n-io/n8n)

## Reference Architecture: Telegram + Pi

A lightweight way to use an existing Pi session remotely:

**Telegram → Bot Gateway → Pi Extension → tmux → Pi TUI**

The gateway bridges Telegram messages to a running Pi process. tmux keeps the session persistent and lets you attach locally.

[Pi Telegram Server](https://github.com/ken196502/pi-telegram-server) is an example of this approach. It provides the bridge; users decide how to customize the agent and its capabilities.

## Repository Structure

- [`projects/`](projects/) — Open-source project catalog
- [`architecture/`](docs/architecture/) — Architecture patterns and diagrams
- [`guides/`](docs/guides/) — Practical integration guides
- [`decisions/`](docs/decisions/) — Technical trade-offs and design choices
- [`resources/`](resources/) — Papers, articles, tutorials, and talks

## Contribute

Found a useful project, integration pattern, or architectural insight? Contributions are welcome.

See [CONTRIBUTING.md](CONTRIBUTING.md).

---

**Build your own agent. Don't inherit someone else's boundaries.**
