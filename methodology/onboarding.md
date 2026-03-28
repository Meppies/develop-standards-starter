# Developer Onboarding

> Fill this in with your actual onboarding steps. Be specific — vague checklists don't help.

---

## Day 1 — Access & setup

### Accounts to request

Ask [e.g. your manager / IT / platform team] for access to:

- [ ] [e.g. GitHub organization — team: your-team]
- [ ] [e.g. Azure DevOps]
- [ ] [e.g. Cloud console — AWS / Azure / GCP]
- [ ] [e.g. Secret manager — Vault / Key Vault / Secrets Manager]
- [ ] [e.g. Kubernetes namespaces — dev and staging for your team]
- [ ] [e.g. Monitoring — Grafana / Datadog]
- [ ] [e.g. Slack channels: #engineering, #platform-alerts, #deployments]
- [ ] [Add your required accounts]

### Tools to install

```bash
# Replace with your actual required tools and install commands

[e.g. brew install pyenv]
[e.g. brew install terraform]
[e.g. brew install kubectl]
[e.g. pip install poetry]
[e.g. brew install pre-commit]
```

### Connect your AI to our standards (do this on Day 1)

```json
// Mac: ~/Library/Application Support/Claude/claude_desktop_config.json
// Windows: %APPDATA%\Claude\claude_desktop_config.json
{
  "mcpServers": {
    "dev-standards": {
      "command": "npx",
      "args": [
        "-y",
        "@modelcontextprotocol/server-filesystem",
        "/path/to/dev-standards-starter"
      ]
    }
  }
}
```

Then say: **"Read our dev standards and help me get started."**

---

## Day 1-3 — Read these standards

In order:

1. **`STANDARDS.md`** — the master overview (15 min)
2. **`standards/languages/primary-language.md`** — our main stack (20 min)
3. **`standards/infrastructure/pipelines.md`** — how we ship code (15 min)
4. **`standards/security/authentication.md`** — how we handle auth and secrets (20 min)
5. **`standards/quality/code-review.md`** — how we review code (10 min)
6. **`methodology/decision-log.md`** — why we made key decisions (variable)

---

## First week — do this

- [ ] Run an existing project locally and make sure the tests pass
- [ ] Make a small PR (a typo fix, a small improvement) and go through the review process
- [ ] Attend a sprint planning, standup, or tech session
- [ ] Ask questions — use [e.g. #engineering in Slack]

---

## Our way of working

### Git workflow

```
main              ← always deployable to production
  └── feature/your-feature
  └── fix/bug-description
  └── chore/maintenance
```

**Branch naming:** `type/short-description` in kebab-case  
**Commit format:** Conventional Commits (`feat:`, `fix:`, `docs:`, etc.)  
**Merge strategy:** [e.g. Squash and merge — no merge commits on main]

### PR process

See `standards/quality/code-review.md`.

---

## Things that trip people up

> Fill this in honestly. Every team has gotchas.

- [e.g. The staging environment uses a different secret path in Vault — ask platform team]
- [e.g. You need to run `terraform init` with specific backend args — see iac.md]
- [Add your team's actual gotchas here]

---

## Getting help

| Question | Go to |
|---|---|
| Technical architecture | [e.g. #engineering in Slack or your tech lead] |
| Access issues | [e.g. #platform or IT helpdesk] |
| Security questions | [e.g. security@yourcompany.com] |
| Changing a standard | Open a PR on this repo |
| Emergencies | See `docs/runbook.md` of the affected service |
