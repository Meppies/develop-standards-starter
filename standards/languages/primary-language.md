# Primary Language & Framework Standards

> **Status:** Template — fill this in using `starter-interview.md` or manually.  
> **Owner:** [TEAM]  
> **Stack:** [LANGUAGE] + [FRAMEWORK]

---

## Project structure

> Replace this with the actual folder structure for your primary project type.  
> Be specific — show a real example with file names.

```
project-name/
├── [your standard folder structure here]
├── ...
├── tests/
├── README.md          ← Required — see templates/README-template.md
└── CHANGELOG.md       ← Required
```

---

## Required dependencies / package management

> List your mandatory dependencies and how you manage them.

```
[e.g. pyproject.toml, package.json, pom.xml, go.mod]
```

**Package manager:** [e.g. Poetry / npm / Maven / Go modules]

**Mandatory libraries:**

| Library | Purpose | Version |
|---|---|---|
| [e.g. pydantic] | [e.g. Data validation] | [e.g. ^2.0] |
| [add your own] | | |

---

## Code style

**Formatter:** [e.g. Black / Prettier / gofmt]  
**Linter:** [e.g. Ruff / ESLint / golangci-lint]  
**Type checking:** [e.g. mypy / TypeScript strict / none]

**Configuration:**

```
[Paste your actual formatter/linter config here]
```

**CI enforcement:** [e.g. Pipeline fails on any lint or format error — yes/no]

---

## Naming conventions

| Element | Convention | Example |
|---|---|---|
| Variables | [e.g. snake_case] | [e.g. user_count] |
| Functions | [e.g. snake_case] | [e.g. get_user()] |
| Classes | [e.g. PascalCase] | [e.g. UserService] |
| Constants | [e.g. UPPER_SNAKE_CASE] | [e.g. MAX_RETRIES] |
| Files | [e.g. snake_case] | [e.g. user_service.py] |
| Environment variables | [e.g. UPPER_SNAKE_CASE] | [e.g. DATABASE_URL] |

---

## Configuration management

> How do you handle application configuration?

**Method:** [e.g. pydantic-settings / dotenv / environment variables directly]

**Rules:**
- [e.g. Never use os.environ.get() directly in business logic]
- [e.g. All config in a single Settings class]
- [e.g. .env.example must list all variables (with fake values)]

---

## Logging

**Library:** [e.g. structlog / winston / zap / standard logging]

**Format:** [e.g. JSON in production, pretty in development]

**Rules:**
- [e.g. No print() statements — ever]
- [e.g. Always log with structured context: logger.info("event", key=value)]
- [e.g. Log levels: DEBUG for development, INFO for production events, ERROR for failures]

---

## API design (if applicable)

**Style:** [e.g. REST / GraphQL / gRPC]

**Versioning:** [e.g. URL versioning: /api/v1/... required]

**Required endpoints:**
- [e.g. GET /health — unauthenticated, returns {"status": "healthy"}]
- [e.g. GET /metrics — Prometheus format]

**Authentication:** See `standards/security/authentication.md`

---

## Docker (if applicable)

**Required:** [e.g. Yes — every service must have a Dockerfile]

**Rules:**
- [e.g. Multi-stage builds required — never ship build tools to production]
- [e.g. Non-root user required in runtime image]
- [e.g. Base image: python:3.11-slim or equivalent minimal image]

---

## Testing

See `standards/quality/testing.md` for full testing standards.

**Quick reference:**
- **Framework:** [e.g. pytest / Jest / JUnit / go test]
- **Minimum coverage:** [e.g. 80%]
- **Required test types:** [e.g. unit + integration]
