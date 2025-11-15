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

### workflow

**Lean, evidence-based feature development workflow**

Commands:
- `/workflow:risk-assess` - Assess feature risk level (Low/Medium/High)
- `/workflow:spike` - Set up spike branch and validation documentation
- `/workflow:design` - Create lean design document with quality gates
- `/workflow:reject` - Document rejected features with evidence and learnings

**Installation:**
```bash
/plugin install workflow
```

**Repository:** [evidence-based-workflow-plugin](https://github.com/NotMyself/evidence-based-workflow-plugin)

---

## Adding New Plugins

To add a new plugin to this marketplace:

1. Create your plugin repository with proper structure:
   ```
   your-plugin/
   ├── .claude-plugin/
   │   └── plugin.json
   └── commands/
       └── your-command.md
   ```

2. Add the plugin to `.claude-plugin/marketplace.json`:
   ```json
   {
     "name": "your-plugin-name",
     "source": "github:NotMyself/your-plugin-repo",
     "description": "Plugin description",
     "version": "1.0.0",
     "author": {
       "name": "Bobby Johnson"
     },
     "repository": "https://github.com/NotMyself/your-plugin-repo"
   }
   ```

3. Commit and push to this repository

4. Users can then install with: `/plugin install your-plugin-name`

## Marketplace Structure

```
claude-marketplace/
├── .claude-plugin/
│   └── marketplace.json    # Marketplace catalog
└── README.md               # This file
```

The marketplace references plugins by their GitHub repositories, allowing each plugin to be independently developed and versioned.

## Automated Version Synchronization

This marketplace uses automated workflows to keep plugin versions up-to-date:

### How It Works

1. **Scheduled Polling**: Every 6 hours, a GitHub Actions workflow checks for new releases
2. **Version Detection**: Compares the latest release version with the current marketplace version
3. **Automatic PR Creation**: When a new version is detected, a PR is automatically created
4. **Review & Merge**: The PR includes release notes and can be reviewed before merging

### Workflow Details

- **Workflow File**: `.github/workflows/sync-plugins.yml`
- **Schedule**: Runs every 6 hours via cron job
- **Manual Trigger**: Can be manually triggered via GitHub Actions UI
- **Supported Plugins**: Currently monitors `dot-hooks`

### Benefits

- ✅ No manual version updates needed
- ✅ Automatic detection of new releases
- ✅ PR-based review process before going live
- ✅ Release notes included in PRs
- ✅ Zero secrets required (uses public GitHub API)

## Plugin Development

For plugin development guidelines, see:
- [Official Plugin Documentation](https://docs.claude.com/en/docs/claude-code/plugins)
- [Plugin Reference](https://docs.claude.com/en/docs/claude-code/plugins-reference)
- [Marketplace Reference](https://docs.claude.com/en/docs/claude-code/plugin-marketplaces)

## Support

- **Issues:** Report marketplace-specific issues in this repository
- **Plugin Issues:** Report in the specific plugin's repository

## License

MIT