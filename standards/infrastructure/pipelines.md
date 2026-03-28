# CI/CD Pipeline Standards

> **Status:** Template — fill this in using `starter-interview.md` or manually.  
> **Platform:** [e.g. GitHub Actions / Azure DevOps / GitLab CI / Jenkins]  
> **Owner:** [PLATFORM TEAM OR PERSON]

---

## Platform

**CI/CD tool:** [e.g. GitHub Actions]  
**Pipeline file location:** [e.g. .github/workflows/ci-cd.yml]

---

## Required pipeline stages (in order)

Every pipeline **must** run these stages in sequence. A failing stage stops everything downstream.

| # | Stage | What it does | Blocks on failure? |
|---|---|---|---|
| 1 | Lint & Format | [e.g. black --check, ruff, eslint] | ✅ Yes |
| 2 | Security scan | [e.g. Trivy, Snyk, bandit] | ✅ Yes |
| 3 | Unit tests | [e.g. pytest, jest] with coverage check | ✅ Yes |
| 4 | Build | Docker image or artifact | ✅ Yes |
| 5 | Integration tests | [e.g. against test database] | ✅ Yes |
| 6 | Push to registry | [e.g. GHCR, ACR, ECR] | ✅ Yes |
| 7 | Deploy → DEV | Automatic on merge to main | ✅ Yes |
| 8 | Deploy → Staging | Automatic after DEV success | ✅ Yes |
| 9 | Deploy → Production | **Manual approval required** | ✅ Yes |

> **Rule:** Never auto-deploy to production without human approval.

---

## Secrets in pipelines

- [e.g. GitHub: use secrets.* — configured in repo settings, never in YAML]
- [e.g. Azure DevOps: use Variable Groups linked to Key Vault]
- **Never** hardcode secrets or tokens in pipeline YAML files

---

## Branch protection rules

Configure in [GitHub / Azure DevOps / your platform]:

- `main` is protected — direct push is forbidden
- Minimum [e.g. 1] reviewer required for PR merge
- Pipeline must pass before merge
- [e.g. Delete branch after merge — enabled]

---

## Image / artifact tagging

| Situation | Tag |
|---|---|
| Pull request build | `pr-{number}` |
| Merge to main | `{git-sha}` (short) |
| Release | `{semver}` e.g. `v1.2.3` |
| Latest stable | `latest` (production only) |

---

## Notifications

- Pipeline failures → [e.g. Slack #platform-alerts]
- Production deployments → [e.g. Slack #deployments]

---

## Pipeline template

> Paste your actual pipeline template here so developers can copy it for new projects.

```yaml
# [your-pipeline-platform] pipeline template
# Copy this to your project and fill in the blanks

# [paste your template here]
```

---

## Notes

[Add team-specific notes, exceptions, or approved deviations here.]
