# Build-Your-Personal-Agent-Team

**Build your own agent team. Understand the pieces. Choose your boundaries.**

A curated map of open-source projects, architectural patterns, and building blocks for assembling your own **Personal Agent Team**.

This is not another monolithic agent framework. Instead of trapping your agents inside a black-box abstraction, this guide helps you explore the ecosystem, understand how independent pieces fit together, and orchestrate a team of specialized agents that work the way you want.

---

## Philosophy: Lightweight Bridges Over Heavy Frameworks

Most "multi-agent frameworks" force you into their way of thinking—dictating how agents talk, how state is stored, and how tools are called. 

A resilient Personal Agent Team follows the Unix philosophy, exemplified by projects like **[Pi Telegram Server](https://github.com/ken196502/pi-telegram-server)**:
1. **Agents are just processes:** An agent is a focused runtime session (like a `Pi` instance in `tmux`) with a specific role, prompt, and toolset.
2. **Gateways are thin bridges, not brains:** Your messaging layer routes intent to the right agent session without hijacking the agent's internal logic.
3. **Persistence is transparent:** Using native system primitives (`tmux`, filesystems, Git) means you can inspect, attach to, or take over any team member's workspace locally at any time.
4. **Teamwork through composition:** A "Team" isn't a complex graph library—it's multiple specialized agent sessions coordinating via shared workspaces, message queues, or a lightweight router.

---

## How a Personal Agent Team is Built

Think in composable layers and roles, not all-in-one platforms.

| Layer | Team Responsibility | Examples |
|---|---|---|
| **Interface** | Where you direct the team (DMs, Topic Groups, Threads) | Telegram (Topics/Bots), Discord, Web |
| **Gateway & Router** | Routes messages to specific agent roles or sessions | [Pi Telegram Server](https://github.com/ken196502/pi-telegram-server), Custom Bot Bridges |
| **Agent Runtime** | Executes individual agent reasoning & coding loops | Pi, Claude Code, LangGraph, Agents SDK |
| **Team Coordination** | How agents hand off tasks and share state | Shared Git repos, Markdown task boards, `tmux` sessions, A2A protocols |
| **Memory & Context** | Shared team knowledge base and role-specific context | Local Markdown files, SQLite, Vector stores |
| **Tools & Capabilities** | External actions assigned per role | MCP servers, CLI tools, APIs |
| **Computer Use** | Visual and browser-level execution | Browser Use, Skyvern, Playwright |
| **Scheduling** | Proactive background routines & standups | Cron, n8n, Systemd timers |
| **Infrastructure** | Process isolation and session persistence | `tmux`, Docker, VPS, Local Mac/Linux server |

Choose what your team needs. Replace what you don't.

---

## Reference Architecture: The Pi + Telegram Team Pattern

Inspired by **[Pi Telegram Server](https://github.com/ken196502/pi-telegram-server)**, you don't need a heavy orchestrator to run a multi-agent team. You can bridge chat channels directly to persistent local CLI sessions:

```text
Telegram (User / Group Topics)
       │
       ▼
  Bot Gateway (Thin Router)
       │
       ├──► [Pi Extension] ──► tmux: "architect-pi"  (Designs & writes specs)
       ├──► [Pi Extension] ──► tmux: "coder-pi"      (Implements & runs tests)
       └──► [Pi Extension] ──► tmux: "researcher-pi" (Scrapes web & summarizes)
                                     │
                                     ▼
                         Shared Workspace (Git / Docs)
