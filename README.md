# Claude Code Plugin Marketplace

A centralized marketplace for Bobby Johnson's Claude Code plugins.

## Installation

Add this marketplace to your Claude Code CLI:

```bash
/plugin marketplace add NotMyself/claude-dotnet-marketplace
```

## Available Plugins

### claude-hall-monitor

**All 12 hook handlers with JSONL logging, realtime viewer UI, rules, and slash commands**

A comprehensive Claude Code hooks implementation using Bun. Monitor and debug Claude Code sessions with structured logging and a realtime web-based log viewer.

**Key Features:**
- **12 Hook Handlers** - Complete coverage of all Claude Code lifecycle events
- **JSONL Logging** - Structured, queryable log format for all events
- **Realtime Viewer** - Web UI with SSE streaming for live log monitoring
- **Rules Files** - 6 actionable convention files for Claude Code guidance
- **Slash Commands** - 3 custom commands for enhanced workflow
- **Cross-Platform** - Works on Windows, macOS, and Linux

**Supported Hooks:**
- `SessionStart`, `SessionEnd` - Session lifecycle with auto-start viewer
- `PreToolUse`, `PostToolUse`, `PostToolUseFailure` - Tool execution monitoring
- `UserPromptSubmit` - Prompt logging and context injection
- `Notification`, `Stop` - System event handling
- `SubagentStart`, `SubagentStop` - Subagent lifecycle tracking
- `PreCompact` - Context compaction logging
- `PermissionRequest` - Auto-approve/deny permissions

**Installation:**
```bash
/plugin install claude-hall-monitor
```

**Version:** 1.0.2

**Repository:** [claude-hall-monitor](https://github.com/NotMyself/claude-hall-monitor)

---

### plan

**Plan and execute complex features with verified sub-agents**

Break large features into smaller pieces, then let Claude execute them one by one - with built-in verification that ensures each piece is actually complete before moving on.

**Key Features:**
- **Collaborative Planning** - `plan:new` helps you think through features with Claude
- **Automatic Decomposition** - `plan:optimize` breaks plans into executable chunks
- **Verified Execution** - `plan:orchestrate` runs sub-agents with mechanical verification
- **Parallel Execution** - `plan:parallel` runs multiple plans via git worktrees
- **Crash Recovery** - Idempotent execution, just re-run if interrupted

**Commands:**
- `plan:new` - Start planning a new feature
- `plan:optimize <plan.md>` - Break plan into sub-agent prompts
- `plan:orchestrate <plan-dir>` - Execute with verification
- `plan:parallel <dir1> <dir2>` - Run multiple plans simultaneously

**Prerequisites:** [Bun](https://bun.sh), [Beads](https://github.com/steveyegge/beads), Git, GitHub CLI

**Optional:**
- [Perles](https://github.com/zjrosen/perles) - Visual tracking UI for Beads
- [Azure CLI](https://docs.microsoft.com/cli/azure/) with [DevOps extension](https://learn.microsoft.com/en-us/azure/devops/cli/) (`az extension add --name azure-devops`) - For Azure DevOps integration (PRs, work item sync)

**Installation:**
```bash
/plugin install plan
```

**Version:** 0.2.0

**Repository:** [planning-system](https://github.com/NotMyself/planning-system)

---

## License

MIT

