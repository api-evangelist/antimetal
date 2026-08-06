---
name: Antimetal
description: Use when investigating production incidents, diagnosing root causes, generating fixes, searching infrastructure data, or managing issues across monitoring and observability platforms. Agents should reach for this skill when users report outages, ask about system health, need remediation steps, or want to query logs, metrics, and traces across connected tools.
metadata:
    mintlify-proj: antimetal
    version: "1.0"
---

# Antimetal Skill

## Product Summary

Antimetal is an AI-powered incident investigation and remediation platform that connects to your monitoring, observability, and infrastructure tools to diagnose root causes and generate production-ready fixes. Agents use Antimetal to investigate alerts, search infrastructure data, manage issues, and propose code changes tied to evidence.

**Key entry points:**
- Dashboard: https://overlook.antimetal.com
- MCP server: https://mcp.antimetal.com (for Claude Code, Cursor, VS Code, and other AI tools)
- API: REST endpoints for issues, search, and artifacts
- Skills plugin: Available in Claude Code and Cursor marketplaces for direct integration

**Core files and config:**
- API keys: Generated at https://overlook.antimetal.com/settings/api-keys
- MCP config: `.cursor/mcp.json` (Cursor), `claude_desktop_config.json` (Claude Desktop), `settings.json` (VS Code)
- Integration setup: https://overlook.antimetal.com/integrations

## When to Use

Reach for this skill when:

- **An alert fires or incident is reported** — Create an issue and trigger an automated investigation to pull logs, metrics, traces, and code context
- **A user asks about system health or infrastructure state** — Use Search to query logs, metrics, and events across all connected platforms
- **You need to diagnose why something failed** — Run an investigation to get root cause analysis with supporting evidence and a causal graph
- **You're ready to fix an issue** — Review Antimetal's proposed immediate and comprehensive fixes, then ship as a PR or execute manually
- **You need to understand how issues relate to each other** — View the causal tree to see how symptoms propagate through your system
- **You're working in an IDE or terminal** — Use the MCP server or Skills plugin to investigate, search, and manage issues without leaving your editor

Do not use Antimetal for: authentication setup, account creation, pricing questions, or dashboard-only operations.

## Quick Reference

### Issue Statuses

| Status | Meaning | Next Action |
|--------|---------|------------|
| **Investigating** | Antimetal is gathering evidence and building root cause analysis | Wait for completion or chat to add context |
| **Ready to fix** | Investigation complete; root cause and fixes available | Review fixes, execute or create PR |
| **Resolved** | Marked as fixed by your team | Archive or reference for future incidents |
| **Muted** | Acknowledged but deprioritized; reopens if new alert fires | Unmute if issue resurfaces |

### Investigation Workflow

1. **Evidence collection** — Queries logs, metrics, traces, events, and code from connected platforms
2. **Causal analysis** — Builds hypotheses and tests them against data
3. **Root cause report** — Produces summary with supporting findings
4. **Remediation** — Generates immediate (symptom) and comprehensive (root cause) fixes
5. **Causal tree** — Visual graph showing how issues propagate

### Fix Types

| Type | Solves | Format |
|------|--------|--------|
| **Immediate** | Active symptom; stops the bleeding | CLI commands, config changes, manual steps |
| **Comprehensive** | Root cause; prevents recurrence | Code changes with diffs, ready for PR |

### MCP Configuration Templates

**Cursor** (`.cursor/mcp.json`):
```json
{
  "mcpServers": {
    "antimetal": {
      "type": "http",
      "url": "https://mcp.antimetal.com",
      "headers": {
        "Authorization": "Bearer ${ANTIMETAL_API_KEY}"
      }
    }
  }
}
```

**Claude Desktop** (`~/Library/Application Support/Claude/claude_desktop_config.json` on macOS):
```json
{
  "mcpServers": {
    "antimetal": {
      "type": "http",
      "url": "https://mcp.antimetal.com",
      "headers": {
        "Authorization": "Bearer YOUR_ANTIMETAL_API_KEY"
      }
    }
  }
}
```

**VS Code** (`settings.json`):
```json
{
  "mcp": {
    "servers": {
      "antimetal": {
        "type": "http",
        "url": "https://mcp.antimetal.com",
        "headers": {
          "Authorization": "Bearer ${input:antimetal-api-key}"
        }
      }
    }
  }
}
```

### API Key Setup

1. Navigate to https://overlook.antimetal.com/settings/api-keys
2. Click "Add New" and name it (e.g., "Antimetal")
3. Select permissions: "View data", "View all incident data", "View catalog types"
4. Click "Create" and copy the key immediately (shown only once)
5. Store securely and share with Antimetal UI or use in MCP config

### Integration Categories

**Monitoring & Observability:** Datadog, Grafana, Sentry, New Relic, Honeycomb, Splunk, Prometheus, Victoria Metrics, Victoria Logs, Tempo, Loki

**Cloud & Infrastructure:** AWS CloudWatch, GCP, Azure, Vercel, Cloudflare, Argo CD

**Incident Management:** PagerDuty, Incident.io, Rootly, iLert

**Source Control:** GitHub (for PR creation)

**CI/CD:** Azure DevOps, Buildkite, CircleCI

**Chat:** Slack (for alert-triggered investigations)

## Decision Guidance

### When to Use Search vs. Create an Issue

| Scenario | Use Search | Use Issue |
|----------|-----------|----------|
| Exploring infrastructure state, asking questions | ✓ | |
| Alert fired or incident reported | | ✓ |
| Need root cause analysis and fixes | | ✓ |
| Quick data lookup (latency, errors, CPU) | ✓ | |
| Want to track and manage the problem | | ✓ |

### When to Use Immediate vs. Comprehensive Fix

| Scenario | Immediate | Comprehensive |
|----------|-----------|---------------|
| Service is actively failing, need to stop bleeding | ✓ | |
| Want to prevent the issue from recurring | | ✓ |
| Need a quick workaround while investigating | ✓ | |
| Ready to ship a permanent code change | | ✓ |

### When to Ship PR from Antimetal vs. Take to Editor

| Scenario | Ship from Antimetal | Take to Editor |
|----------|-------------------|----------------|
| Fix is ready to merge as-is | ✓ | |
| Need to iterate or add context | | ✓ |
| Want to hand off to a coding agent | | ✓ |
| Want to create a draft PR for review | ✓ | |

## Workflow

### Investigate an Alert or Incident

1. **Create the issue** — Go to https://overlook.antimetal.com/issues or trigger from Slack via the Antimetal Slackbot
2. **Provide context** — Add alert details, error messages, or affected services
3. **Wait for investigation** — Watch the Steps tab for live chain of thought; Antimetal queries your connected platforms
4. **Review the Answers** — Once complete, read the root cause summary, findings, and causal graph
5. **Chat if needed** — Ask follow-up questions or provide additional context to refine the analysis
6. **Review fixes** — Check Immediate and Comprehensive tabs for proposed remediation
7. **Execute or ship** — Copy CLI commands to run manually, or create a PR directly from Antimetal

### Search Your Infrastructure

1. Go to https://overlook.antimetal.com/chats/new
2. Type a natural-language question: "What's the p99 latency for the payments service?" or "Are there errors in auth logs from the last hour?"
3. Antimetal queries all connected platforms and returns results with supporting evidence
4. If search surfaces something worth investigating, click "Create Issue" to kick off a full investigation

### Connect MCP to Your IDE

1. **Generate API key** — Go to https://overlook.antimetal.com/settings/api-keys and create a new key
2. **Add MCP config** — Paste the appropriate config template (Cursor, Claude Desktop, VS Code, etc.) into your editor's config file
3. **Replace placeholder** — Substitute `YOUR_ANTIMETAL_API_KEY` or set `ANTIMETAL_API_KEY` environment variable
4. **Restart editor** — Reload to pick up the new config
5. **Use skills** — Type `/investigate`, `/fix`, or `/antimetal-mcp-setup` in your AI tool

### Create and Ship a PR

1. **Review the fix** — Open the Comprehensive fix tab on an issue
2. **Check the diff** — Review the side-by-side code changes
3. **Choose your path:**
   - **Ship from Antimetal:** Click "Create PR" (requires GitHub integration) or "Create draft PR"
   - **Take to editor:** Click "Open in Cursor/Codex/Devin" or "Copy fix as prompt"
4. **Validate locally** — Antimetal does not run tests; verify the change works before merging
5. **Respond to PR** — Approve, request changes, or close if no longer relevant

## Common Gotchas

- **Investigation is asynchronous** — Issues move from Investigating to Ready to fix automatically. Poll the issue or watch the dashboard; don't assume it's done immediately.
- **API key is shown only once** — Copy and store it securely when created. You cannot retrieve it later; generate a new one if lost.
- **Fixes are proposals, not automatic** — Antimetal never applies fixes on your behalf. Every fix must be reviewed and shipped by an engineer.
- **PR creation requires GitHub integration** — You cannot create PRs without connecting GitHub to Antimetal first.
- **Tests are not run** — Antimetal does not validate fixes against your test suite. Always verify locally or in CI before merging.
- **MCP config requires restart** — Changes to MCP config files (`.cursor/mcp.json`, `claude_desktop_config.json`, etc.) require restarting your editor to take effect.
- **Integrations must be set up first** — Antimetal can only query platforms you've connected. If a tool is missing, add it at https://overlook.antimetal.com/integrations.
- **Multiple alerts map to one issue** — Antimetal groups related signals together. Don't create duplicate issues for the same underlying problem.
- **Chat adds context but doesn't re-run investigation** — Asking a question in chat refines the analysis; to regenerate with new evidence, explicitly request it.
- **Causal graph is visual only** — The causal tree shows relationships but is not executable. Use the fixes tab for remediation steps.

## Verification Checklist

Before submitting work with Antimetal:

- [ ] **Integrations are connected** — Verify all required platforms (monitoring, cloud, incident management) are set up at https://overlook.antimetal.com/integrations
- [ ] **Investigation is complete** — Check that the issue status is "Ready to fix", not "Investigating"
- [ ] **Root cause is clear** — Review the Answers tab and confirm the root cause explanation makes sense
- [ ] **Findings are auditable** — Click into findings to verify they link to real data in your connected platforms
- [ ] **Fix is reviewed** — Read the Immediate and Comprehensive fixes; understand what each step does
- [ ] **Code changes are validated** — If shipping a PR, run tests locally or in CI before merging
- [ ] **PR is assigned correctly** — Antimetal auto-assigns based on code history; verify the assignee is appropriate
- [ ] **Chat context is added** — If you provided additional context in chat, confirm it was incorporated into the analysis
- [ ] **No duplicate issues** — Check the issues board to ensure you're not creating a duplicate for an existing problem

## Resources

**Comprehensive navigation:** https://docs.antimetal.com/llms.txt

**Critical documentation:**
- [Issue Lifecycle](https://docs.antimetal.com/product/issue-lifecycle) — How issues move from alert to resolution
- [Fixes](https://docs.antimetal.com/product/fixes) — How to review, execute, and ship remediation
- [Integrations Overview](https://docs.antimetal.com/integrations/overview) — Full list of connected platforms and setup guides

---

> For additional documentation and navigation, see: https://docs.antimetal.com/llms.txt