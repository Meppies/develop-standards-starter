# General Coding Principles

> These principles apply to all languages and all projects in our team.  
> Language-specific rules are in `standards/languages/primary-language.md`.

---

## Principles we follow

> Keep this short. These are the principles every developer should be able to recite.

1. **[Add your first principle — e.g. Single responsibility: one function does one thing]**
2. **[Add your second principle — e.g. Explicit over implicit: no magic, no surprises]**
3. **[Add your third principle — e.g. Consistency over personal preference]**
4. **[Add more as needed]**

---

## Naming

Choose descriptive names. If you need a comment to explain what a variable does, choose a better name.

```
# Bad:  d = 0.10
# Good: discount_rate = 0.10

# Bad:  process(x, y, True)
# Good: calculate_price(base_price, tax_rate, include_vat=True)
```

---

## No magic numbers

```
# Bad:  if retries > 3: raise TimeoutError()
# Good: MAX_RETRIES = 3
#        if retries > MAX_RETRIES: raise TimeoutError()
```

---

## Error handling

- Never swallow exceptions silently (`except: pass` is banned)
- Always log context when catching an error (what were you trying to do?)
- Use custom exceptions for domain errors
- Catch specific exceptions, not `Exception` unless re-raising

---

## No dead code

- No commented-out code blocks in PRs
- No unused imports
- No `TODO` older than one sprint without a linked issue

---

## Configuration

- All config via environment variables or a dedicated config system
- No hardcoded URLs, IPs, ports, or credentials — anywhere
- `.env.example` must exist and list all required variables (with placeholder values)

---

## Secrets

**Never** put secrets in:
- Source code
- Config files that go into git
- Log output
- Error messages
- URL parameters

Always use: [your secret manager — fill this in]

---

## Commit messages

We follow [Conventional Commits](https://www.conventionalcommits.org/):

```
feat: add OAuth authentication to users endpoint
fix: correct validation error on empty email (#123)
docs: update README with deployment instructions
refactor: extract order validation into separate service
test: add edge case tests for negative quantities
chore: upgrade [framework] to [version]
ci: add security scan to pipeline
```

One commit = one logical change. No "fixed stuff" or "WIP" on main.

---

## Branch naming

```
feature/short-description
fix/bug-description
chore/maintenance-task
docs/what-you-documented
```

---

## What belongs in a PR

A PR should be reviewable in under 30 minutes. If it's larger, split it.

Every PR needs:
- A clear description: what changed, why, how to test it
- Tests for new functionality
- Updated README (if applicable)
- No unrelated changes

See `standards/quality/code-review.md` for the full review checklist.
