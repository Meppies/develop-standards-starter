# Configuration Management Standards

> **Status:** Template — fill this in using `starter-interview.md` or manually.  
> **Tool:** [e.g. Ansible / Chef / Puppet / none]  
> **Owner:** [PLATFORM TEAM OR PERSON]

---

## Tool & version

**Tool:** [e.g. Ansible]  
**Required version:** [e.g. >= 2.14]

> If you don't use configuration management, delete this file and remove the reference from STANDARDS.md.

---

## Folder structure

```
[your-config-folder]/
├── inventories/
│   ├── dev/
│   │   ├── hosts.yml
│   │   └── group_vars/
│   ├── staging/
│   └── production/
│
├── roles/
│   └── [role-name]/
│       ├── tasks/main.yml
│       ├── handlers/main.yml
│       ├── templates/
│       ├── defaults/main.yml
│       └── README.md
│
└── playbooks/
    └── site.yml
```

---

## Core rules

- **[e.g. Idempotency is required — every playbook must be safely re-runnable]**
- **[e.g. Roles-based structure — no monolithic playbooks]**
- **[e.g. FQCN (Fully Qualified Collection Name) required on all modules]**
- **[e.g. YAML format for inventories — no INI format]**

---

## Secrets

**Tool:** [e.g. Ansible Vault / external Vault integration]

**Rules:**
- [e.g. No plaintext secrets in any file that goes into git]
- [e.g. Vault password always fetched from Key Vault in CI/CD — never stored in repo]

---

## Naming conventions

| Element | Convention | Example |
|---|---|---|
| Role names | [e.g. snake_case] | [e.g. nginx_config] |
| Variables | [e.g. snake_case with role prefix] | [e.g. nginx_port] |
| Task names | [e.g. Descriptive sentence] | [e.g. Ensure nginx is running] |
| Templates | [e.g. .j2 extension] | [e.g. nginx.conf.j2] |

---

## Testing

**Tool:** [e.g. Molecule / none]

[e.g. Every new role must have a Molecule test scenario before merge.]

---

## Notes

[Add any team-specific notes, exceptions, or quirks here.]
