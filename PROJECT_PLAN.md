# PMS - Passive Project Management System

## Project Overview
A "Developer's Sanctuary" PMS that eliminates management friction by making the codebase the single source of truth for project tracking. Developers never manually log tasks - the system automatically tracks progress through git commits.

## Core Problem
Developers hate Jira/Trello because they must stop coding, switch windows, and manually move cards to "Done" - wasting cognitive flow.

## Solution
- Developer pushes to GitHub/GitLab with task IDs in commit messages (e.g., `#102`)
- System via GitHub webhook + IDE plugin parses the ID and automatically updates the Kanban board
- Developer stays in flow; manager gets real-time updates

---

## Architecture

### Frontend
- **Next.js 14+** (App Router)
- **Dashboard**: Dark mode with neon accents (priority-based colors)
- **Kanban Boards**: Fluid drag-and-drop, gesture-based navigation
- **Deep Work Mode**: Timer that silences OS notifications
- **Visual Celebrations**: Milestone completion rewards

### Backend (Microservices)
- **Core API**: Task/project management, OAuth, webhooks
- **Git Integration Service**: Commit parsing, webhook handling
- **Budget Tracking Service**: Independent module
- **Real-time**: WebSocket for live updates

### Database Schema
```
Users (OAuth: GitHub/GitLab)
Projects (1:many Tasks)
Tasks (status: ENUM - To Do/In Progress/Review/Done)
Commits (external event table: hash, message, timestamp, repo)
CommitMapping (many-to-one: commit_hash → Task IDs)
TaskHistory (optional: velocity tracking from To Do → Done)
```

### IDE Plugin
- VS Code + IntelliJ
- Auth handshake with PMS backend
- Listens for `git commit` events
- Extracts task IDs from commit messages
- Triggers API to update Kanban

---

## Implementation Phases

### Phase 1: Foundation (Weeks 1-2)
- [ ] Set up Next.js project with .gitignore (Node/Next template)
- [ ] Design database schema (PostgreSQL)
- [ ] Implement OAuth authentication (GitHub/GitLab)
- [ ] Set up project structure

### Phase 2: Core Functionality (Weeks 3-4)
- [ ] GitHub webhook endpoint
- [ ] Commit message parser (extracts `#102` style IDs)
- [ ] API endpoints for task status updates
- [ ] Kanban board component (draggable tasks)

### Phase 3: IDE Plugin (Weeks 5-6)
- [ ] Lightweight plugin (VS Code + IntelliJ)
- [ ] Authentication handshake
- [ ] Commit event listener
- [ ] Automatic status update trigger

### Phase 4: UX & Polish (Weeks 7-8)
- [ ] Flow State dark mode theme
- [ ] Neon accents based on task priority
- [ ] Deep Work timer (OS notification silencer)
- [ ] Visual celebrations on milestone completion

### Phase 5: Testing & Deployment (Weeks 9-10)
- [ ] End-to-end integration tests
- [ ] IDE plugin compatibility testing
- [ ] Production deployment

---

## Key Dependencies
- Next.js 14+ with App Router
- PostgreSQL
- GitHub/GitLab OAuth
- WebSocket for real-time updates
- Framer Motion (animations)

## Success Metrics
- Zero manual task logging required
- Commit → Kanban update in <2 seconds
- Developer stays in flow state
- 90%+ reduction in context-switching

---

## Source of Truth
Original conversation documented in `pms_plan.txt` - discussion between Hussam and wife (Maya) about the project philosophy, architecture, UX, and technical approach.