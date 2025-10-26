# Support

Need help with Claude Code Plugin Marketplace? This guide will help you find the right resource.

---

## Quick Links

- **Getting Started:** [README.md](README.md)
- **Adding Plugins:** [CONTRIBUTING.md](CONTRIBUTING.md)
- **Security:** [SECURITY.md](SECURITY.md)
- **Issues:** [GitHub Issues](https://github.com/NotMyself/claude-marketplace/issues)
- **Discussions:** [GitHub Discussions](https://github.com/NotMyself/claude-marketplace/discussions)

---

## Finding Answers

### Documentation

**Before opening an issue**, check these resources:

1. **[README.md](README.md)** - Installation and available plugins
2. **[CONTRIBUTING.md](CONTRIBUTING.md)** - How to add plugins to marketplace
3. **[SECURITY.md](SECURITY.md)** - Security considerations
4. **[CHANGELOG.md](CHANGELOG.md)** - Version history and changes

### Common Issues

#### "Marketplace not found"

**Problem:** `/plugin marketplace add` fails

**Solutions:**
1. Verify exact command: `/plugin marketplace add NotMyself/claude-marketplace`
2. Check GitHub repository is accessible
3. Ensure you have network connectivity
4. Try removing and re-adding marketplace

---

#### "Plugin not found in marketplace"

**Problem:** Plugin doesn't appear after adding marketplace

**Solutions:**
1. Verify plugin is listed in `marketplace.json`
2. Check plugin name spelling (use `/plugin` to browse)
3. Restart Claude Code to refresh plugin list
4. Remove and re-add marketplace to force refresh

---

#### "Plugin installation failed"

**Problem:** `/plugin install` fails

**Solutions:**
1. **Check plugin repository exists** and is public
2. **Verify plugin.json** is valid in plugin repo
3. **Check permissions** - you need read access to plugin repo
4. **Review error message** - often indicates specific issue
5. **Try installing directly** from plugin repo if marketplace fails

**Common causes:**
- Plugin repository moved or deleted
- Plugin repository is private
- Invalid plugin.json in plugin repo
- Network connectivity issues

---

#### "Marketplace has old plugin version"

**Problem:** Marketplace lists outdated plugin version

**Solutions:**
1. **For users:** Remove and re-add marketplace
   ```bash
   /plugin marketplace remove notmyself-marketplace
   /plugin marketplace add NotMyself/claude-marketplace
   ```

2. **For maintainers:** Update `marketplace.json` version number
   - Edit plugin entry in `marketplace.json`
   - Update `version` field
   - Commit and push changes
   - Users need to refresh marketplace

---

## Getting Help

### For Marketplace Issues

Use [GitHub Issues](https://github.com/NotMyself/claude-marketplace/issues) for:
- ✅ Marketplace configuration problems
- ✅ Plugin listing errors (wrong info, broken links)
- ✅ Installation failures
- ✅ Documentation issues
- ✅ Request to add your plugin

**Issue Template:**
```markdown
**Type:** Bug / Plugin Request / Documentation

**Description:**
{Clear description of issue}

**Steps to Reproduce:** (for bugs)
1. Run command: /plugin marketplace add ...
2. Error message: {paste error}

**Expected Behavior:**
{What should happen}

**Actual Behavior:**
{What actually happened}

**Environment:**
- OS: {Windows/Mac/Linux}
- Claude Code Version: {version}

**Additional Context:**
{Screenshots, logs, etc.}
```

---

### For Plugin-Specific Issues

**Plugin not working correctly?**

Report to the **plugin's repository**, not the marketplace:

1. Find plugin repository URL in [README.md](README.md)
2. Open issue in that repository
3. Include specific error messages and steps to reproduce

**Marketplace vs Plugin Issues:**

| Issue | Report To |
|-------|-----------|
| Plugin not in marketplace list | Marketplace Issues |
| Plugin installation fails | Check plugin repo, then marketplace |
| Plugin command doesn't work | Plugin repository |
| Plugin command gives wrong output | Plugin repository |
| Plugin documentation unclear | Plugin repository |
| Want to add new plugin | Marketplace Issues or PR |

---

### GitHub Discussions

Use [GitHub Discussions](https://github.com/NotMyself/claude-marketplace/discussions) for:
- ✅ Questions about adding plugins
- ✅ Plugin discovery ("what plugin does X?")
- ✅ Marketplace best practices
- ✅ Feature suggestions
- ✅ General questions

**Categories:**
- **Q&A:** Ask questions about the marketplace
- **Show and Tell:** Share your plugin additions
- **Ideas:** Suggest marketplace improvements
- **General:** Everything else

---

### Plugin Discovery

**Looking for a specific type of plugin?**

1. Browse [README.md](README.md#available-plugins) - all plugins listed
2. Search by keyword - plugins have keyword tags
3. Ask in [Discussions](https://github.com/NotMyself/claude-marketplace/discussions)

**Want to create a plugin?**

1. See [Claude Code Plugin Documentation](https://docs.claude.com/en/docs/claude-code/plugins)
2. Review existing plugins for examples
3. Read [CONTRIBUTING.md](CONTRIBUTING.md) for marketplace addition process

---

## Direct Contact

**For marketplace administration:**
- Email: bobby@notmyself.io
- Response time: 1-3 business days

**For security issues:**
- See [SECURITY.md](SECURITY.md)
- Email: bobby@notmyself.io (subject: "[SECURITY] ...")

---

## Response Times

### Issues and Pull Requests

- **Bug reports:** Acknowledged within 3 days
- **Plugin requests:** Reviewed within 5 days
- **Pull requests:** Reviewed within 1 week
- **Security issues:** See [SECURITY.md](SECURITY.md) for timeline

**Note:** This is an open-source project maintained by volunteers. Response times are best-effort.

---

## Adding Your Plugin

### Process Overview

1. **Prepare your plugin repository**
   - Must have `.claude-plugin/plugin.json`
   - Must be public on GitHub
   - Must have documentation

2. **Submit to marketplace**
   - Fork this repository
   - Add entry to `marketplace.json`
   - Update README and CHANGELOG
   - Submit pull request

3. **Review and merge**
   - Maintainer reviews PR
   - Tests plugin installation
   - Merges if acceptable

**Detailed instructions:** See [CONTRIBUTING.md](CONTRIBUTING.md#adding-a-new-plugin)

---

## Removing a Plugin

**Need to remove your plugin?**

1. Open [GitHub Issue](https://github.com/NotMyself/claude-marketplace/issues)
2. Title: "Remove plugin: plugin-name"
3. Explain reason (discontinued, deprecated, etc.)
4. We'll remove within 1 week

**Deprecation preferred:**
- We can mark plugins as deprecated
- Gives users time to migrate
- Add warning to README

---

## Marketplace Maintenance

### How the Marketplace Works

**What marketplace does:**
- Lists available plugins with metadata
- Points to plugin GitHub repositories
- Provides centralized discovery

**What marketplace does NOT do:**
- Host plugin code (that's in plugin repos)
- Guarantee plugin quality
- Provide plugin support
- Control plugin versioning

**Responsibility:**
- **Marketplace:** Accurate plugin listings
- **Plugin maintainers:** Plugin functionality
- **Users:** Review and trust plugins

---

## Plugin Quality

**Marketplace inclusion doesn't mean:**
- ❌ Plugin is secure
- ❌ Plugin is bug-free
- ❌ Plugin is maintained
- ❌ Plugin is recommended

**Users should:**
- ✅ Review plugin source code
- ✅ Check maintenance activity
- ✅ Read plugin documentation
- ✅ Test in safe environment
- ✅ Report issues to plugin maintainer

---

## Resources

### For Plugin Users

- **Plugin installation:** See [README](README.md#installation)
- **Available plugins:** See [README](README.md#available-plugins)
- **Plugin issues:** Report to plugin repository

### For Plugin Developers

- **Creating plugins:** [Claude Code Plugin Docs](https://docs.claude.com/en/docs/claude-code/plugins)
- **Plugin reference:** [Plugin Reference](https://docs.claude.com/en/docs/claude-code/plugins-reference)
- **Adding to marketplace:** [CONTRIBUTING.md](CONTRIBUTING.md)

### Official Documentation

- **Claude Code Documentation:** https://docs.claude.com/en/docs/claude-code/
- **Plugin System:** https://docs.claude.com/en/docs/claude-code/plugins
- **Marketplace Schema:** https://docs.claude.com/en/docs/claude-code/plugin-marketplaces

---

## Community Support

### Helping Others

**You can help!**
- Answer questions in Discussions
- Test plugin installations
- Report broken links
- Suggest improvements
- Share your plugins

### Code of Conduct

**Be helpful:**
- Welcome newcomers
- Give constructive feedback
- Share knowledge

**Be respectful:**
- Respect maintainers' time
- Be patient with reviews
- Accept feedback gracefully

**Be honest:**
- Don't misrepresent plugins
- Disclose limitations
- Report issues you find

---

## Stay Updated

**Watch repository** for notifications:
- New plugins added
- Marketplace updates
- Security announcements

**Subscribe to:**
- [Releases](https://github.com/NotMyself/claude-marketplace/releases)
- [Discussions](https://github.com/NotMyself/claude-marketplace/discussions)

---

## Feedback

**How are we doing?**

We value your feedback on:
- Ease of adding plugins
- Plugin discovery
- Documentation clarity
- Support responsiveness

**Share feedback:**
- [Discussions > General](https://github.com/NotMyself/claude-marketplace/discussions)
- GitHub Issues for specific problems

---

## Thank You!

Thank you for using Claude Code Plugin Marketplace! Your questions and feedback help us improve.

**Remember:** The marketplace is a catalog, not a gatekeeper. You're always free to install plugins directly from their repositories without using the marketplace.

Need help? Don't hesitate to ask! 🙏