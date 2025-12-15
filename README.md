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

**Version:** 1.0.1

**Repository:** [claude-hall-monitor](https://github.com/NotMyself/claude-hall-monitor)

---

## License

MIT
