# Claude Code Plugin Marketplace

A centralized marketplace for Bobby Johnson's Claude Code plugins.

## Installation

Add this marketplace to your Claude Code CLI:

```bash
/plugin marketplace add NotMyself/claude-marketplace
```

## Available Plugins

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