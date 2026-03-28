# Infrastructure as Code Standards

> **Status:** Template — fill this in using `starter-interview.md` or manually.  
> **Tool:** [e.g. Terraform / Pulumi / AWS CDK / CloudFormation]  
> **Owner:** [PLATFORM TEAM OR PERSON]

---

## Tool & version

**IaC tool:** [e.g. Terraform]  
**Required version:** [e.g. >= 1.5.0]  
**Provider:** [e.g. hashicorp/azurerm ~> 3.90]

---

## Folder structure

> Replace with your actual structure.

```
[your-iac-folder]/
├── modules/
│   └── [module-name]/     # All reusable components go here
│       ├── main.tf
│       ├── variables.tf
│       ├── outputs.tf
│       ├── versions.tf
│       └── README.md      # Auto-generated via terraform-docs
│
└── environments/
    ├── dev/
    ├── staging/
    └── production/
```

**Rule:** [e.g. No loose resources in environments/ — everything via modules]

---

## State management

**Backend:** [e.g. Azure Storage / S3 / Terraform Cloud]  
**Rule:** [e.g. Local state is never used in shared projects]

```hcl
# Example backend config — replace with your actual setup
terraform {
  backend "[your-backend]" {
    # [your backend config here]
  }
}
```

---

## Naming conventions

| Resource type | Pattern | Example |
|---|---|---|
| [e.g. Resource groups] | [e.g. rg-{project}-{env}] | [e.g. rg-myapp-prod] |
| [Add your resources] | | |

---

## Required on every resource

> What tags/labels/metadata must every resource have?

```hcl
# Example — replace with your required tags
locals {
  common_tags = {
    Environment = var.environment
    Project     = var.project_name
    ManagedBy   = "[your-iac-tool]"
    Owner       = var.owner_team
    # [add your required tags]
  }
}
```

---

## Variables

**Rules:**
- [e.g. Every variable must have a description]
- [e.g. Use validation blocks for critical variables]
- [e.g. No default values for environment-specific variables]

---

## Secrets

- [e.g. Never put secrets in .tfvars or variable defaults]
- [e.g. Use data sources to fetch from Key Vault / Secrets Manager]
- [e.g. .tfvars files with sensitive data are in .gitignore]

---

## CI/CD pipeline gates

The IaC pipeline must run in this order:

1. [e.g. terraform fmt -check]
2. [e.g. terraform validate]
3. [e.g. tflint]
4. [e.g. tfsec or checkov — security scan]
5. [e.g. terraform plan — save output as artifact]
6. **Manual approval required for [staging / production]**
7. [e.g. terraform apply]

---

## Documentation

[e.g. Use terraform-docs to auto-generate README.md for every module. Never edit module READMEs manually.]
