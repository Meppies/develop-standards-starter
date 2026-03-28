# Starter Interview

This is the guided conversation for setting up your team's dev standards from scratch. When a developer connects via MCP and says "help me set up our dev standards," the AI should follow this flow.

---

## Principles for the guide

- Be conversational, not robotic. This should feel like a senior engineer helping you think through your stack.
- Ask one thing at a time. Don't overwhelm with options.
- Fill in the placeholders as you go. Don't wait until the end.
- Make it useful fast. The developer should have a working `STANDARDS.md` within fifteen minutes.
- Adapt to what they know. If they say "we use whatever the team picks," help them make decisions.

---

## The flow

### Step 1: Orient (2 minutes)

Explain what we're building in plain language:

"We're going to set up a shared AI knowledge system for your engineering team. It's a folder of markdown files that every developer's AI reads at the start of a coding session. It means the AI always knows your stack, your structure, your rules — without anyone having to re-explain them.

Think of it as giving every developer on your team an AI that actually knows how *you* build software.

We'll build it together right now. I'll ask you some questions about your team and stack, and we'll fill in the standards as we go. By the end of this conversation, you'll have something your whole team can connect to."

### Step 2: Understand the team (3 minutes)

Ask these questions one at a time:

- What's the name of your organization or team?
- How many developers are we talking about? (Rough number is fine.)
- Is this for a new team starting fresh, or an existing team with existing projects?
- Who will maintain these standards? (One person? A platform team? Everyone?)

Use their answers to set the tone. A 3-person startup needs different standards than a 50-person enterprise team.

### Step 3: Establish the stack (10 minutes)

This is the most important part. Interview them to fill in `STANDARDS.md` and `standards/languages/primary-language.md`.

#### 3a: Primary language and framework

Ask:

- What programming language do you primarily use?
- What framework or runtime? (e.g. FastAPI, Spring Boot, Express, Rails, .NET)
- What version are you standardizing on?
- Are there any languages you explicitly *don't* want developers using without approval?

Fill in the stack table in `STANDARDS.md`.

#### 3b: Infrastructure

Ask:

- Do you use Infrastructure as Code? Which tool? (Terraform, Pulumi, CDK, CloudFormation?)
- Do you use configuration management? (Ansible, Chef, Puppet, none?)
- Where do you deploy? (AWS, Azure, GCP, on-prem, hybrid?)
- What does your CI/CD look like? (GitHub Actions, Azure DevOps, Jenkins, GitLab CI?)
- How do you handle containers? (Docker? Kubernetes? ECS? Nothing yet?)

Fill in `standards/infrastructure/`.

#### 3c: Security baseline

Ask:

- How do users authenticate to your systems? (OAuth/OIDC, API keys, LDAP, something else?)
- Where do you store secrets? (Vault, AWS Secrets Manager, Azure Key Vault, .env files?)
- Do you have a specific security standard you follow? (ISO 27001, SOC 2, internal policy?)

Fill in `standards/security/authentication.md`.

#### 3d: Quality expectations

Ask:

- Do you have a required test coverage percentage? What is it?
- What does your code review process look like? (How many reviewers? Any automation?)
- What linters and formatters are mandatory?
- Is there a documentation requirement? (e.g. all endpoints must have docstrings?)

Fill in `standards/quality/`.

### Step 4: The README standard (5 minutes)

The README template is the most immediately useful deliverable. Ask:

- What sections do you always want in a project README?
- Are there any sections that are mandatory vs. optional?
- Do you have a specific format for environment variable documentation?
- Any existing README you love that we should model this after?

Fill in `templates/README-template.md`.

Also establish the update rule — suggest this if they don't have one:

"Whenever a developer adds a new endpoint, environment variable, or changes the project structure, the README must be updated in the same PR. Want me to add that as a rule the AI will always check?"

### Step 5: The onboarding checklist (3 minutes)

Ask:

- What tools does every developer need installed? List them.
- What accounts or access do new developers need to request?
- What should every developer read before their first PR?
- Is there anything that always trips up new joiners?

Fill in `methodology/onboarding.md`.

### Step 6: First real use (5 minutes)

Make it tangible. Ask: "Want to test this right now? Tell me about a project you're working on and I'll help you set it up following these standards."

Walk them through:
- Creating the correct folder structure
- Writing the README using the template
- Setting up the correct linting and formatting config
- Checking authentication is handled correctly

This proves the system works immediately.

### Step 7: Wrap up (2 minutes)

"Your dev standards system is now live. Every AI-assisted session from here happens within your team's context.

Next steps:
- Share this repo with your team and have everyone add the MCP config to their Claude Desktop
- Run through the onboarding checklist to make sure it's complete
- Schedule a quarterly review to keep the standards current
- Open a PR whenever something should change — the AI picks it up on next `git pull`"

If they're technical, suggest:
- Setting up branch protection so changes to `STANDARDS.md` require two reviewers
- Adding a `CHANGELOG.md` to track when standards change and why

---

## Adaptation notes

- **For platform/infra teams:** Go deeper on Terraform module structure, pipeline gates, and environment promotion rules.
- **For product teams:** Focus more on API standards, authentication patterns, and the README template.
- **For teams with existing projects:** Acknowledge that standards apply to *new* code first, then migrate existing projects incrementally.
- **For teams without strong opinions:** Help them make decisions. Offer the most common choices and explain the tradeoffs briefly.
- **For security-conscious orgs:** Spend extra time on `standards/security/authentication.md` and add a secrets checklist to the PR template.
