# Claude Code Plugin Marketplace

A centralized marketplace for Bobby Johnson's Claude Code plugins.

## Installation

Add this marketplace to your Claude Code CLI:

```bash
/plugin marketplace add NotMyself/claude-marketplace
```

## Available Plugins

### dot-hooks

**Strongly-typed .NET plugin framework for Claude Code hooks**

A .NET 10 CLI tool that provides a robust plugin framework for intercepting and handling Claude Code lifecycle events. Features compile-time type safety, runtime plugin compilation via Roslyn, and full dependency injection support.

**Key Features:**
- 🔒 **Strongly-Typed Event Handlers** - `IHookEventHandler<TInput, TOutput>` with compile-time type constraints
- 🎯 **Event-Specific Execution** - Handlers only execute for events they care about
- 🔌 **Multiple Event Support** - Single plugin can handle multiple event types
- 💉 **Full Dependency Injection** - Any registered service can be injected
- 🚀 **Dynamic Compilation** - Roslyn-based runtime compilation of C# plugins
- 📝 **Comprehensive Logging** - Session-based logs with per-plugin tracking

**Supported Events:**
- `pre-tool-use`, `post-tool-use` (Tool events)
- `session-start`, `session-end` (Session events)
- `user-prompt-submit`, `notification`, `stop`, `subagent-stop`, `pre-compact` (Generic events)

**Installation:**
```bash
/plugin install dot-hooks
```

**Version:** 0.2.0 (Strongly-Typed Event System)

**Repository:** [dot-hooks](https://github.com/NotMyself/dot-hooks)

---

## License

MIT
