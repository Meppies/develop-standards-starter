# Testing Standards

> **Minimum coverage:** [e.g. 80%] — pipeline blocks below this.  
> **Principle:** Test behavior, not implementation.

---

## Test framework

**Tool:** [e.g. pytest / Jest / JUnit / go test / NUnit]  
**Coverage tool:** [e.g. pytest-cov / Istanbul / JaCoCo]  
**Minimum coverage:** [e.g. 80%]

---

## Test types we use

| Type | Purpose | Speed | Required? |
|---|---|---|---|
| Unit tests | Individual functions in isolation | Fast | ✅ Yes |
| Integration tests | Service + database / external service | Medium | ✅ Yes |
| E2E tests | Full user flow | Slow | [e.g. For critical paths only] |

Target split: [e.g. 70% unit / 25% integration / 5% E2E]

---

## Folder structure

```
tests/
├── [e.g. conftest.py]       # Shared fixtures
├── unit/
│   └── test_[feature].py
└── integration/
    └── test_[feature].py
```

---

## What you always test

1. **Happy path** — normal input, expected output
2. **Validation errors** — invalid input returns the right error
3. **Auth errors** — missing/invalid token returns 401
4. **Authorization errors** — wrong role returns 403
5. **Not found** — missing resource returns 404
6. **Business rule violations** — domain rules that are broken

---

## What you don't test

- Framework internal behavior (your framework tests itself)
- Trivial getters/setters with no logic
- [Add your team's exceptions here]

---

## Test configuration

```
[Paste your actual test configuration here — pytest.ini, jest.config.js, etc.]
```

---

## Running tests locally

```bash
# Run all tests
[e.g. poetry run pytest]

# With coverage report
[e.g. poetry run pytest --cov=app --cov-report=html]

# Unit tests only
[e.g. poetry run pytest tests/unit/]
```

---

## Fixtures and test data

**Rule:** [e.g. No real external services in unit tests — use mocks]  
**Rule:** [e.g. No production data in tests — ever]  
**Tool for test data:** [e.g. factory-boy / Faker / fixtures]

---

## Notes

[Add team-specific testing notes, exceptions, or patterns here.]
