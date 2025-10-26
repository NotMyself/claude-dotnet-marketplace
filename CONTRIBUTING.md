# Contributing to Claude Code Plugin Marketplace

Thank you for your interest in contributing! This guide explains how to add plugins to the marketplace or improve the marketplace itself.

---

## Table of Contents

- [Quick Start](#quick-start)
- [Adding a New Plugin](#adding-a-new-plugin)
- [Updating Plugin Metadata](#updating-plugin-metadata)
- [Testing Changes](#testing-changes)
- [Pull Request Process](#pull-request-process)
- [Guidelines](#guidelines)

---

## Quick Start

### 1. Fork and Clone

```bash
git clone https://github.com/YOUR_USERNAME/claude-marketplace.git
cd claude-marketplace
```

### 2. Make Changes

Edit `.claude-plugin/marketplace.json` to add or update plugins.

### 3. Test Locally

```bash
# Add your fork as a marketplace
/plugin marketplace add YOUR_USERNAME/claude-marketplace

# Try installing a plugin
/plugin install workflow
```

---

## Adding a New Plugin

### Prerequisites

Your plugin repository must have:
1. `.claude-plugin/plugin.json` with proper schema
2. Component directories (`commands/`, `agents/`, etc.)
3. Proper documentation (README, etc.)

See [Claude Code Plugin Documentation](https://docs.claude.com/en/docs/claude-code/plugins) for plugin development.

### Steps to Add

**1. Ensure your plugin repository is ready:**

```
your-plugin/
├── .claude-plugin/
│   └── plugin.json          # Plugin metadata
├── commands/                 # Slash commands
│   └── your-command.md
└── README.md
```

**2. Add plugin entry to `.claude-plugin/marketplace.json`:**

```json
{
  "plugins": [
    {
      "name": "your-plugin-name",
      "source": "github:NotMyself/your-plugin-repo",
      "description": "Brief description of what your plugin does",
      "version": "1.0.0",
      "author": {
        "name": "Your Name"
      },
      "homepage": "https://github.com/NotMyself/your-plugin-repo",
      "repository": "https://github.com/NotMyself/your-plugin-repo",
      "license": "MIT",
      "keywords": [
        "keyword1",
        "keyword2"
      ]
    }
  ]
}
```

**3. Update README.md:**

Add your plugin to the "Available Plugins" section:

```markdown
### your-plugin-name

**Brief description**

Commands:
- `/your-plugin:command1` - Description
- `/your-plugin:command2` - Description

**Installation:**
\`\`\`bash
/plugin install your-plugin-name
\`\`\`

**Repository:** [your-plugin-repo](https://github.com/NotMyself/your-plugin-repo)
```

**4. Update CHANGELOG.md:**

Add entry under `[Unreleased]`:

```markdown
### Added

- **your-plugin-name** - Brief description
  - Command1: description
  - Command2: description
  - Source: `github:NotMyself/your-plugin-repo`
```

---

## Updating Plugin Metadata

To update an existing plugin's metadata (description, version, etc.):

1. Edit the plugin entry in `.claude-plugin/marketplace.json`
2. Update version number if applicable
3. Update CHANGELOG.md with the change
4. Submit pull request

**Note:** Plugin source code changes happen in the plugin's own repository, not here.

---

## Testing Changes

### Test Locally

```bash
# Remove old marketplace (if installed)
/plugin marketplace remove notmyself-marketplace

# Add your fork
/plugin marketplace add YOUR_USERNAME/claude-marketplace

# Test installing plugins
/plugin install workflow
/plugin install your-new-plugin

# Restart Claude Code
# Verify commands appear when typing /
```

### Validation Checklist

- [ ] `marketplace.json` is valid JSON
- [ ] All plugin entries have required fields (`name`, `source`)
- [ ] Plugin names use kebab-case (no spaces)
- [ ] Source URLs use `github:owner/repo` format
- [ ] Keywords are lowercase and hyphenated
- [ ] README lists all plugins
- [ ] CHANGELOG documents changes

---

## Pull Request Process

### Before Submitting

1. **Test your changes locally** (see above)
2. **Update documentation** (README, CHANGELOG)
3. **Validate JSON syntax** (`marketplace.json`)
4. **Ensure plugin repo is public** and accessible

### Submission

1. **Create feature branch:**
   ```bash
   git checkout -b add-plugin-name
   ```

2. **Commit with descriptive message:**
   ```bash
   git commit -m "feat: add plugin-name plugin

   - Added plugin-name to marketplace catalog
   - Updated README with plugin description
   - Added CHANGELOG entry

   Plugin provides:
   - Command1: description
   - Command2: description"
   ```

3. **Push and create PR:**
   ```bash
   git push origin add-plugin-name
   ```

4. **PR Template:**
   ```markdown
   ## Description

   Adding [plugin-name] to the marketplace.

   ## Plugin Details

   - **Name:** plugin-name
   - **Repository:** https://github.com/NotMyself/plugin-name
   - **Commands:** /plugin-name:command1, /plugin-name:command2
   - **Author:** Your Name

   ## Checklist

   - [ ] Plugin repository has `.claude-plugin/plugin.json`
   - [ ] Plugin repository is public
   - [ ] Tested plugin installation locally
   - [ ] Updated `marketplace.json`
   - [ ] Updated README.md
   - [ ] Updated CHANGELOG.md
   - [ ] JSON is valid

   ## Testing

   Tested by:
   ```
   /plugin marketplace add YOUR_USERNAME/claude-marketplace
   /plugin install plugin-name
   ```

   Commands appear correctly: (screenshot or confirmation)
   ```

### Review Process

1. **Automated checks** run (JSON validation, etc.)
2. **Maintainer reviews** within 3-5 days
3. **Address feedback** if needed
4. **Merge** when approved
5. **Plugin available** to all users

---

## Guidelines

### Plugin Quality Standards

Plugins added to this marketplace should:

- ✅ **Work correctly** - Tested and functional
- ✅ **Be documented** - Clear README in plugin repo
- ✅ **Follow schemas** - Valid plugin.json structure
- ✅ **Have clear commands** - Intuitive command names
- ✅ **Provide value** - Solve real problems

### Naming Conventions

- **Plugin names:** kebab-case (e.g., `workflow`, `code-reviewer`)
- **Command names:** kebab-case (e.g., `risk-assess`, `review-pr`)
- **Keywords:** lowercase, hyphenated (e.g., `feature-development`)

### Documentation Requirements

Your plugin repository should have:

- **README.md** - Installation, usage, examples
- **LICENSE** - Open source license (MIT recommended)
- **CHANGELOG.md** - Version history
- **.claude-plugin/plugin.json** - Valid plugin manifest

### Version Management

- Use [Semantic Versioning](https://semver.org/)
- Update version in both:
  - Plugin's `plugin.json`
  - Marketplace's `marketplace.json` entry
- Document breaking changes

---

## Removing a Plugin

To remove a plugin from the marketplace:

1. **Create issue** explaining why
2. **Deprecation period** (2 weeks notice)
3. **Remove from marketplace.json**
4. **Update README** (remove from list)
5. **Update CHANGELOG** (document removal)
6. **Tag with reason** (archived, deprecated, etc.)

---

## Code of Conduct

### Be Helpful

- Welcome new plugin developers
- Provide constructive feedback
- Share knowledge and examples
- Help troubleshoot issues

### Be Respectful

- Respect maintainers' time
- Be patient with reviews
- Accept feedback gracefully
- Follow guidelines

### Be Honest

- Don't add broken plugins
- Disclose limitations
- Report issues you find
- Give credit where due

---

## Questions?

- **Plugin development:** See [Claude Code docs](https://docs.claude.com/en/docs/claude-code/plugins)
- **Marketplace questions:** Open [GitHub Discussion](https://github.com/NotMyself/claude-marketplace/discussions)
- **Bug reports:** Open [GitHub Issue](https://github.com/NotMyself/claude-marketplace/issues)
- **Security:** See [SECURITY.md](SECURITY.md)

---

## Thank You!

Thank you for contributing to the Claude Code plugin ecosystem! Your plugins help developers work more effectively.