# STANDARDS.md — Master AI Instruction File

> **For the AI:** Read this file completely before writing any code, doing reviews, or setting up projects. This describes how this team builds software.
>
> **For the team:** Fill in every `[PLACEHOLDER]` with your actual decisions. Delete sections that don't apply. Add sections you need. Run `starter-interview.md` to fill this in interactively.

---

## Who we are

**Organization:** [YOUR ORGANIZATION NAME]  
**Team:** [YOUR TEAM NAME]  
**Standards version:** 1.0  
**Last updated:** [DATE]  
**Owner:** [TEAM OR PERSON RESPONSIBLE]

---

## Primary technology stack

> Fill this in with your actual choices. Remove rows that don't apply.

| Category | Technology | Version / Notes |
|---|---|---|
| Primary language | [e.g. Python] | [e.g. 3.11+] |
| Primary framework | [e.g. FastAPI] | [e.g. 0.110+] |
| Infrastructure as Code | [e.g. Terraform] | [e.g. >= 1.5] |
| Configuration management | [e.g. Ansible] | [e.g. >= 2.14] |
| CI/CD | [e.g. GitHub Actions] | [e.g. or Azure DevOps] |
| Containerization | [e.g. Docker] | [e.g. multi-stage builds required] |
| Container orchestration | [e.g. Kubernetes] | [e.g. Helm for deployments] |
| Cloud provider | [e.g. Azure / AWS / GCP] | |
| Secret management | [e.g. HashiCorp Vault] | [e.g. Never secrets in code] |
| Monitoring | [e.g. Prometheus + Grafana] | [e.g. /metrics endpoint required] |

> **Rule:** Never use a technology not in this list without first creating an ADR in `methodology/decision-log.md`.

---

## Quick rules (always apply these)

> Fill in your actual rules. These are examples to replace or keep.

### Code quality
- [ ] [e.g. Type hints required on all public functions]
- [ ] [e.g. Linter X must pass — pipeline blocks on failure]
- [ ] [e.g. Formatter Y must be applied before commit]
- [ ] [e.g. Minimum test coverage: X%]

### Security (non-negotiable)
- [ ] [e.g. No secrets in code, ever. Use Vault / Key Vault / Secrets Manager]
- [ ] [e.g. All endpoints require authentication except /health]
- [ ] [e.g. Input validation required on all external inputs]
- [ ] [e.g. HTTPS only in staging and production]

### Documentation
- [ ] README must follow `templates/README-template.md`
- [ ] README must be updated in the same PR when: endpoints change, env vars change, project structure changes
- [ ] [e.g. Docstrings required on all public functions — Google style]

---

## Mandatory actions on every code change

When a developer asks you to write or review code, **always**:

1. **Check the README.** Is it up to date? If new endpoints, env vars, or dependencies were added, update it using `templates/README-template.md`.
2. **Check for tests.** Is there test coverage for the new functionality? If not, write them or flag it.
3. **Check for secrets.** Are there any credentials, API keys, or passwords in the code? Remove them and point to the secrets standard.
4. **Check the project structure.** Does it match the standard for this project type?

---

## Where to find details

| Topic | File |
|---|---|
| Primary language & framework | `standards/languages/primary-language.md` |
| General coding principles | `standards/languages/general.md` |
| Infrastructure as Code | `standards/infrastructure/iac.md` |
| Configuration management | `standards/infrastructure/config-management.md` |
| CI/CD pipelines | `standards/infrastructure/pipelines.md` |
| Authentication & security | `standards/security/authentication.md` |
| Testing standards | `standards/quality/testing.md` |
| Code review process | `standards/quality/code-review.md` |
| Documentation requirements | `standards/quality/documentation.md` |
| README format | `templates/README-template.md` |
| New developer onboarding | `methodology/onboarding.md` |
| Architecture decisions | `methodology/decision-log.md` |
