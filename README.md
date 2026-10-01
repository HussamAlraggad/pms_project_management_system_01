# PMS - Passive Project Management System

> A "Developer's Sanctuary" that eliminates management friction by making the codebase the single source of truth.

## The Problem
Developers hate Jira/Trello because they must stop coding, switch windows, and manually move cards to "Done" — wasting cognitive flow.

## The Solution
**Zero manual task logging.** Developer pushes code with task IDs in commits (`feat: add auth #102`). Our system — via GitHub webhook + IDE plugin — parses the ID and auto-updates the Kanban board. The dev stays in flow; the manager gets real-time updates.

---

## Core Features

| Feature | Description |
|---------|-------------|
| **Passive Tracking** | Commits auto-update Kanban — no context switching |
| **Flow State UX** | Dark mode, neon priority accents, fluid Kanban, gesture nav |
| **Deep Work Mode** | Timer that silences OS notifications |
| **IDE Plugin** | VS Code + IntelliJ — listens to local git commits |
| **GitHub/GitLab OAuth** | Link repos to project boards securely |
| **Real-time Updates** | WebSocket-powered live board updates |

---

## Tech Stack

- **Frontend**: Next.js 14+ (App Router), TypeScript, Tailwind CSS, DaisyUI
- **Backend**: Microservices (Node.js/Go), PostgreSQL
- **Real-time**: WebSockets
- **Auth**: GitHub/GitLab OAuth
- **IDE Plugin**: VS Code Extension API, IntelliJ Platform SDK

---

## Project Structure

```
pms/
├── pms-web/          # Next.js dashboard & portal
├── pms-api/          # Core API microservice
├── pms-git/          # Git integration service
├── pms-budget/       # Budget tracking service
├── pms-plugin-vscode/    # VS Code extension
└── pms-plugin-intellij/  # IntelliJ plugin
```

---

## Documentation

- [Project Plan](PROJECT_PLAN.md) — Phased implementation roadmap
- [Original Discussion](pms_plan.txt) — Full conversation with product vision

---

## Getting Started

```bash
# Coming soon - Phase 1 setup
cd pms-web && npm install && npm run dev
```

---

## License

MIT — Built with ❤️ for developers who want to stay in flow.