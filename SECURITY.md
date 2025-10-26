# Security Policy

## Supported Versions

We release patches for security vulnerabilities.

| Version | Supported          |
| ------- | ------------------ |
| 1.0.x   | :white_check_mark: |

## Reporting a Vulnerability

We take the security of Claude Code Plugin Marketplace seriously. If you believe you have found a security vulnerability, please report it to us as described below.

### Please Do NOT:

- Open a public GitHub issue
- Disclose the vulnerability publicly before it has been addressed

### Please Do:

**Report privately via GitHub:**
1. Go to the [Security tab](https://github.com/NotMyself/claude-marketplace/security)
2. Click "Report a vulnerability"
3. Fill out the form with as much detail as possible

**Or email directly:**
- Email: bobby@notmyself.io
- Subject: "[SECURITY] Claude Marketplace"

### What to Include:

- **Description** of the vulnerability
- **Steps to reproduce** the issue
- **Potential impact** (what could an attacker do?)
- **Affected plugin** (if specific to one plugin)
- **Suggested fix** (if you have one)
- **Your contact information** for follow-up questions

### What to Expect:

- **Acknowledgment** within 48 hours
- **Initial assessment** within 7 days
- **Regular updates** on progress toward a fix
- **Credit** in the release notes (if desired)

### Vulnerability Disclosure Timeline:

1. **Day 0:** Report received
2. **Day 1-7:** Initial assessment and response
3. **Day 7-30:** Fix developed and tested (or plugin removed if critical)
4. **Day 30-45:** Patch released (earlier if critical)
5. **Day 45+:** Public disclosure coordinated with reporter

---

## Security Best Practices for Users

### Marketplace Installation

**Verify source:**
- Only add marketplaces from trusted sources
- Verify GitHub repository ownership
- Check marketplace maintainer reputation

**Installation command:**
```bash
# Verify you're adding the official marketplace
/plugin marketplace add NotMyself/claude-marketplace
```

### Plugin Installation

**Review before installing:**
- Check plugin repository source code
- Review plugin.json permissions
- Read plugin documentation
- Check for recent maintenance

**Trust model:**
- Marketplace links to plugin repos
- Each plugin runs with YOUR permissions
- Plugins can access files and run commands
- Review plugin code before trusting

**Installation safety:**
```bash
# 1. Review plugin repository first
# 2. Check what commands it provides
# 3. Install only if trusted
/plugin install plugin-name
```

### Plugin Permissions

**What plugins can do:**
- ✅ Read/write files in your project
- ✅ Execute bash commands
- ✅ Make network requests
- ✅ Access environment variables
- ✅ Modify GitHub issues (if you grant access)

**What plugins CANNOT do:**
- ❌ Access files outside project directory
- ❌ Elevate permissions beyond your user
- ❌ Access other Claude Code sessions
- ❌ Persist data outside plugin directory

---

## Security Considerations

### Marketplace Integrity

**How we protect marketplace integrity:**

1. **Public repository** - All changes visible via GitHub
2. **Commit history** - Audit trail of all marketplace updates
3. **Review process** - PRs reviewed before merging
4. **GitHub-based sources** - Plugins installed from verifiable repos

**Marketplace does NOT:**
- Host plugin code directly
- Cache plugin content
- Modify plugin behavior
- Store user data

### Plugin Vetting

**Before adding plugins to marketplace:**

- ✅ Repository is public and accessible
- ✅ Has valid `.claude-plugin/plugin.json`
- ✅ Documentation exists (README)
- ✅ License is specified
- ✅ Source code is reviewable

**We do NOT guarantee:**
- ❌ Plugin security (user responsibility to review)
- ❌ Plugin functionality
- ❌ Plugin maintenance
- ❌ Absence of vulnerabilities

**User responsibility:**
- Review plugin source code before installation
- Understand what commands do before running them
- Keep plugins updated
- Report suspicious behavior

### Supply Chain Security

**Risks:**

1. **Compromised plugin repository** - Malicious code added to plugin repo
2. **Dependency attacks** - Plugin dependencies compromised
3. **Typosquatting** - Similar plugin names for confusion

**Mitigations:**

1. **GitHub source verification** - Plugins installed from GitHub repos
2. **User review** - You can inspect source before installing
3. **Marketplace transparency** - All plugin sources visible
4. **Naming standards** - Kebab-case naming reduces confusion

**Best practices:**
- Bookmark official plugin repos
- Verify repository ownership
- Check commit history for suspicious activity
- Use dependency scanning tools

### Malicious Plugin Indicators

**Warning signs:**

- ⚠️ Requests unnecessary permissions
- ⚠️ Obfuscated or unclear code
- ⚠️ No documentation or examples
- ⚠️ Recently created repository
- ⚠️ No commit history or maintenance
- ⚠️ Suspicious network requests
- ⚠️ Attempts to access sensitive files

**If you suspect a malicious plugin:**
1. **Do NOT install it**
2. **Report to marketplace** (open issue)
3. **Report to Claude Code** (if already published)
4. **Warn community** (discussions)

---

## Known Security Considerations

### Marketplace Repository

**Public by design:**
- All marketplace updates are public
- Plugin additions/removals are visible
- No private or sensitive data stored

**Access control:**
- Only maintainers can merge PRs
- Community can submit PRs
- GitHub provides audit logs

### Plugin Installation Flow

**How it works:**
1. User adds marketplace: `/plugin marketplace add NotMyself/claude-marketplace`
2. Claude Code fetches `marketplace.json`
3. User browses available plugins
4. User installs plugin: `/plugin install plugin-name`
5. Claude Code clones from GitHub source
6. Plugin commands become available

**Security implications:**
- Marketplace is just a catalog (not a security boundary)
- Plugins execute with user's permissions
- User trusts marketplace → trusts plugin repos
- No sandboxing or isolation

### GitHub Dependency

**Marketplace depends on GitHub:**
- Plugin sources must be GitHub repos
- GitHub API availability required
- GitHub security = our security
- Git cloning uses your credentials

**If GitHub is compromised:**
- Plugins could be modified
- New malicious plugins could be added
- Users should verify commit signatures

---

## Out of Scope

The following are **not** considered marketplace security vulnerabilities:

- Issues in individual plugins (report to plugin maintainer)
- GitHub platform vulnerabilities
- Claude Code vulnerabilities
- User misconfiguration
- Social engineering attacks
- Plugins behaving as documented (even if dangerous)

**Note:** We may still remove plugins that are intentionally malicious, even if "working as designed."

---

## Plugin Removal Process

**Criteria for removal:**

1. **Confirmed malicious** - Intentionally harmful code
2. **Severely vulnerable** - Critical unpatched security issues
3. **Abandoned + broken** - Unmaintained and non-functional
4. **Legal issues** - Copyright violation, illegal content

**Process:**

1. **Issue opened** with evidence
2. **Maintainer investigates** (1-3 days)
3. **Plugin author notified** (if contactable)
4. **Decision made** (remove or keep with warning)
5. **If removed:**
   - Removed from `marketplace.json`
   - README updated with removal note
   - CHANGELOG documents reason
   - GitHub issue references removal

---

## Reporting Malicious Plugins

**If you discover a malicious plugin:**

**Immediate:**
1. Do NOT install or run the plugin
2. Uninstall if already installed: `/plugin uninstall plugin-name`

**Report:**
1. Open [GitHub Issue](https://github.com/NotMyself/claude-marketplace/issues)
2. Title: "[SECURITY] Malicious plugin: plugin-name"
3. Include:
   - Plugin name and source repo
   - Malicious behavior observed
   - Evidence (code snippets, logs)
   - Impact assessment

**For urgent threats:**
- Email: bobby@notmyself.io
- Subject: "[URGENT SECURITY] Malicious plugin"

---

## Questions?

For security questions that aren't vulnerabilities:
- [GitHub Discussions](https://github.com/NotMyself/claude-marketplace/discussions)
- [GitHub Issues](https://github.com/NotMyself/claude-marketplace/issues)

Thank you for helping keep the Claude Code plugin ecosystem secure!