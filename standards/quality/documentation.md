# Documentation Standards

---

## Required documents per project

| Document | Required | When to update |
|---|---|---|
| `README.md` | ✅ Always | Every change that affects behavior, endpoints, or config |
| `CHANGELOG.md` | ✅ Always | Every release |
| `docs/architecture.md` | ✅ For services | When architecture changes |
| `docs/runbook.md` | ✅ For production services | When operational procedures change |
| `docs/adr/` | For major decisions | When a significant tech choice is made |

---

## README update rule (enforced by AI)

The README **must be updated in the same PR** when:

- A new API endpoint is added or removed
- An environment variable is added, changed, or removed
- A new required dependency is added
- The project structure significantly changes
- The deployment process changes
- The minimum version of any core tool changes

> The AI will check this on every code change. If the README is out of date, it will flag it.

---

## Docstrings

**Required on:** All public functions, classes, and methods  
**Style:** [e.g. Google-style / NumPy-style / JSDoc]  
**Not required on:** Private functions, trivial properties

```
[Paste an example docstring in your preferred style here]
```

---

## CHANGELOG format

We follow [Keep a Changelog](https://keepachangelog.com/) format:

```markdown
## [Unreleased]
### Added
- ...

## [1.2.0] - YYYY-MM-DD
### Added
- New feature description

### Changed
- What changed

### Fixed
- Bug that was fixed (#issue-number)

### Removed
- Deprecated thing that was removed
```

---

## Architecture Decision Records (ADR)

When to write an ADR:
- Choosing a new framework, library, or tool
- Changing an authentication mechanism
- Significant refactoring that affects the whole system
- Any decision that future developers will ask "why did we do it this way?"

Location: `docs/adr/NNNN-short-title.md`

Template: see `methodology/decision-log.md`
