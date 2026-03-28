# Authentication & Security Standards

> **Status:** Template — fill this in using `starter-interview.md` or manually.  
> **Owner:** [SECURITY TEAM OR PERSON]

---

## Authentication mechanisms

> For each scenario, specify exactly which mechanism to use. Be prescriptive.

| Scenario | Required mechanism |
|---|---|
| User → Web application | [e.g. OAuth 2.0 + OIDC via Azure Entra ID] |
| Service → Service (internal) | [e.g. mTLS + service account tokens] |
| Pipeline → Cloud resources | [e.g. Managed Identity / Workload Identity] |
| Developer → Production systems | [e.g. SSO + MFA — no shared accounts] |
| External API → our API | [e.g. OAuth 2.0 client credentials] |

> **Rule:** [e.g. Password-based authentication to production systems is forbidden]

---

## Identity provider

**IdP:** [e.g. Azure Entra ID / Okta / Auth0 / Keycloak]  
**Protocol:** [e.g. OAuth 2.0 + OIDC]  
**Tenant/Realm:** [e.g. your-tenant.onmicrosoft.com]

---

## Secret management

**Tool:** [e.g. HashiCorp Vault / AWS Secrets Manager / Azure Key Vault]  
**URL/endpoint:** [e.g. https://vault.internal.yourcompany.com]

**Rules:**
- Never put secrets in code, config files in git, logs, or error messages
- [e.g. Kubernetes: use Workload Identity or Vault Agent — no Kubernetes Secrets for app secrets]
- [e.g. Local dev: use .env file — never commit it]

---

## HTTPS & TLS

- HTTPS only in staging and production — no exceptions
- [e.g. TLS 1.2 minimum, TLS 1.3 preferred]
- [e.g. HTTP → HTTPS redirect at load balancer level]
- [e.g. Certificates via Let's Encrypt + cert-manager in Kubernetes]

---

## Required security headers

> List the HTTP security headers every API/web service must return.

```
[e.g. Strict-Transport-Security: max-age=31536000; includeSubDomains]
[e.g. X-Content-Type-Options: nosniff]
[e.g. X-Frame-Options: DENY]
[add your required headers]
```

---

## Input validation

**Rule:** All external input must be validated before processing.  
**Tool:** [e.g. Pydantic / Joi / Bean Validation / your choice]

Never process raw user input. Never concatenate user input into SQL queries.

---

## Audit logging

Audit logs are **required** for:
- [e.g. Any DELETE operation]
- [e.g. Changes to user permissions]
- [e.g. Authentication failures]
- [Add your requirements]

Audit logs must include: actor identity, target resource, timestamp, IP address.  
Retention: [e.g. minimum 1 year]

---

## Security checklist for every PR

The AI will check these on every PR. Reviewers check these before approving.

- [ ] No secrets in code or committed config files
- [ ] All endpoints have authentication (except /health and documented exceptions)
- [ ] Input validation on all request bodies and parameters
- [ ] Audit logging on destructive operations
- [ ] Dependencies scanned for CVEs in pipeline
- [ ] No debug endpoints left in
- [ ] No sensitive data in logs or error messages

---

## Reporting a security issue

[e.g. Email security@yourcompany.com — do not open a public GitHub issue]
