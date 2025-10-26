# Changelog

All notable changes to the Claude Code Plugin Marketplace will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

## [1.0.0] - 2025-10-26

### Added

- **Marketplace Infrastructure** - Centralized plugin catalog
  - `marketplace.json` with plugin metadata
  - GitHub-based plugin source references
  - Version tracking for marketplace and plugins

- **Initial Plugin** - workflow plugin
  - Evidence-based feature development workflow
  - 4 commands: risk-assess, spike, design, reject
  - Source: `github:NotMyself/evidence-based-workflow-plugin`

- **Documentation**
  - README with installation instructions
  - Plugin listing with descriptions and commands
  - Guidelines for adding new plugins
  - LICENSE (MIT)

### Installation

```bash
/plugin marketplace add NotMyself/claude-marketplace
/plugin install workflow
```

### Plugin Catalog

| Plugin | Version | Description |
|--------|---------|-------------|
| workflow | 1.0.0 | Evidence-based feature development workflow |

---

## Version History

**1.0.0** - Initial marketplace release
- Centralized plugin catalog
- workflow plugin available
- Complete documentation

---

## Links

- [Repository](https://github.com/NotMyself/claude-marketplace)
- [Issues](https://github.com/NotMyself/claude-marketplace/issues)
- [Discussions](https://github.com/NotMyself/claude-marketplace/discussions)