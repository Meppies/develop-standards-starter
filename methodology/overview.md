# Why These Standards Exist

> Fill this in with your team's actual reasons. The more honest, the better.

---

## The problem without standards

In a team with multiple developers, without shared standards you typically get:

- Every project has a different folder structure — onboarding takes weeks per project
- Each developer makes different security decisions — vulnerabilities slip through
- Documentation is inconsistent or absent — nobody understands each other's code
- CI/CD pipelines are copy-pasted and half-understood
- Technology choices are made per project — knowledge doesn't transfer

**Result:** High cognitive load, slow onboarding, security risk, high maintenance cost.

---

## Why an AI-first approach

Traditional style guides get ignored. Nobody reads them, nobody enforces them.

By putting standards in markdown files connected to your AI tool via MCP:

1. **The AI always knows your stack** — no generic suggestions, only suggestions that match your way of working
2. **Standards are in git** — versioned, reviewable, everyone can contribute
3. **Onboarding is faster** — new developers connect their AI and are productive immediately
4. **The AI enforces it** — automatically checks README, tests, and secrets on every session

---

## Our principles

> Replace these with the principles your team actually believes in.

1. **Consistency over personal preference.** Consistent standards beat inconsistent best practices.
2. **Standards evolve.** Any developer can propose a change via PR. Good arguments get accepted.
3. **Security by default.** Security is built into every standard, not bolted on.
4. **AI-first documentation.** Every file is written so an AI can read it and act on it immediately.

---

## What's in scope

- Programming languages and frameworks
- Project structures
- Infrastructure as Code
- CI/CD pipelines
- Authentication and security
- Documentation requirements
- Code review process
- Onboarding

## What's out of scope

- Business logic of individual applications
- Team-specific working agreements (teams can add their own standards folder)
- Tools outside the approved stack (use an ADR to add something new)

---

## Ownership

**Maintained by:** [e.g. Platform Team]  
**Review cadence:** [e.g. Quarterly, or when the stack changes significantly]  
**Questions:** [e.g. #platform in Slack]

To change a standard: open a PR, discuss in your engineering channel, merge when there's consensus.
