# Code Review Standards

> **Principle:** We review code, not people. Feedback is always about the code.

---

## The process

1. Author opens a PR with a clear description
2. CI pipeline must be green before requesting review
3. Minimum **[e.g. 1]** reviewer required — **[e.g. 2]** for security-related changes
4. Reviewer uses the checklist below
5. All comments must be resolved before merge
6. Author squash-merges (no merge commits on main)

---

## Reviewer checklist

Before approving, check:

### Functionality
- [ ] The code does what the PR description says
- [ ] Edge cases are handled
- [ ] Error handling is present and meaningful

### Security
- [ ] No secrets in code
- [ ] Input validation on external inputs
- [ ] Authentication/authorization correctly applied on new endpoints
- [ ] Audit logging present for sensitive operations

### Code quality
- [ ] [e.g. Type hints present on public functions]
- [ ] [e.g. Docstrings on public functions and classes]
- [ ] No dead code or commented-out blocks
- [ ] Function/variable names are descriptive

### Tests
- [ ] Tests exist for new functionality
- [ ] Both happy path and error paths are tested
- [ ] Coverage has not dropped

### Documentation
- [ ] README updated if endpoints, env vars, or structure changed
- [ ] CHANGELOG updated for user-facing changes
- [ ] ADR created if a significant technology choice was made

---

## How to give feedback

Use labels in your comments:

| Label | Meaning |
|---|---|
| `[blocker]` | Must fix — I won't approve without this |
| `[suggestion]` | Would be better, but not a blocker |
| `[question]` | I don't understand this — help me understand |
| `[nit]` | Minor style point — entirely up to you |
| `[praise]` | This is well done! |

---

## Turnaround expectations

| Priority | Expected response time |
|---|---|
| Hotfix / incident | [e.g. < 2 hours — ping reviewer directly] |
| Normal PR | [e.g. < 1 business day] |
| Large refactor | [e.g. < 2 business days — flag this in the PR] |

If a reviewer hasn't responded after [e.g. 1 day], ping them in [e.g. Slack].

---

## PR template

> Copy this to `.github/pull_request_template.md` in your projects.

```markdown
## What does this PR do?

[One paragraph description]

## Why?

[The reason for this change]

## How to test it?

[Steps to verify this works]

## Checklist

- [ ] Tests added/updated
- [ ] README updated (if applicable)
- [ ] No secrets in code
- [ ] CHANGELOG updated (if user-facing change)
```
