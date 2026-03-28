# 🏗️ Dev Standards Starter

**An open source framework for building a shared AI knowledge system for engineering teams.**

Connect your AI tool to your team's coding standards via MCP — and every developer always has the right context, every conversation.

---

## What this is

A **dev standards system** is a folder of markdown files that describes how your team builds software. When developers connect their AI tool to it via MCP, the AI knows:

- Which languages and frameworks you use (and which you don't)
- What your project structures look like
- How README files should be written
- Which authentication mechanisms to use
- How your Terraform/Ansible/pipeline standards work
- What your code review expectations are

The AI becomes a true team member — not a generic assistant, but one that knows *your* way of working.

This isn't an app. It's a pattern that works with Claude Desktop, Claude Code, Cursor, or any AI tool that reads files via MCP.

---

## Three ways to use this

### 1. Connect via MCP and set it up interactively (easiest)

Add this to your Claude Desktop config:

**Mac:** `~/Library/Application Support/Claude/claude_desktop_config.json`  
**Windows:** `%APPDATA%\Claude\claude_desktop_config.json`

```json
{
  "mcpServers": {
    "dev-standards": {
      "command": "npx",
      "args": [
        "-y",
        "@modelcontextprotocol/server-filesystem",
        "/path/to/dev-standards-starter"
      ]
    }
  }
}
```

Restart Claude Desktop, then say: **"Help me set up our dev standards."**

The `starter-interview.md` guides the AI through building your standards interactively.

### 2. Fork and customize (for teams)

```bash
git clone https://github.com/your-org/dev-standards-starter.git dev-standards
cd dev-standards
# Open in Claude Code or your preferred AI tool
# Say: "Read STANDARDS.md and help me customize this for our stack"
```

### 3. Read and fill in manually

Browse the `standards/` folder and fill in the placeholders yourself.

---

## What's inside

```
dev-standards-starter/
├── STANDARDS.md                  # Master AI instruction file (read this first)
├── starter-interview.md          # Guided setup conversation
│
├── standards/
│   ├── languages/
│   │   ├── primary-language.md   # Your main language & framework
│   │   └── general.md            # Principles that apply to all code
│   ├── infrastructure/
│   │   ├── iac.md                # Terraform / Pulumi / CloudFormation
│   │   ├── config-management.md  # Ansible / Chef / Puppet
│   │   └── pipelines.md          # CI/CD standards
│   ├── security/
│   │   └── authentication.md     # Auth mechanisms & security requirements
│   └── quality/
│       ├── code-review.md        # Review process & checklist
│       ├── testing.md            # Testing standards & coverage requirements
│       └── documentation.md      # Docs requirements incl. README standard
│
├── templates/
│   └── README-template.md        # Mandatory README format for all projects
│
└── methodology/
    ├── overview.md               # Why these standards exist
    ├── decision-log.md           # Architecture Decision Records (ADR)
    └── onboarding.md             # Checklist for new developers
```

---

## Philosophy

- **Files, not databases.** Markdown in git. You own them. Any AI can read them. No vendor lock-in.
- **Standards, not rules.** This is a living document your team maintains together — not bureaucracy.
- **AI-first.** Every file is written so an AI can read it and act on it immediately.
- **Consistency over perfection.** Consistently applied standards beat inconsistent best practices every time.
- **The AI enforces it.** Unlike every style guide you've abandoned, this one reminds developers automatically.

---

## How the MCP connection works

The `@modelcontextprotocol/server-filesystem` package exposes your local folder as an MCP server. Claude reads the files as context at the start of every conversation.

```
Developer's Claude Desktop
        │
        │  MCP (filesystem)
        ▼
dev-standards-starter/      ← Claude reads these files
    STANDARDS.md            ← First: master instructions
    standards/*.md          ← Then: detailed standards
    templates/*.md          ← Then: templates to apply
```

No internet connection required. No API keys. Just a local folder.

---

## After setup

Once your standards are in place, tell every developer on your team to:

1. Clone this repo
2. Add the MCP config to their Claude Desktop
3. Say: "Read our dev standards and help me start a new project"

Every AI-assisted code session now happens within your team's context.

---

## Contributing to your standards

When something should change:

1. Open a PR on your fork of this repo
2. Discuss in your engineering channel
3. Merge — all connected AI tools immediately pick up the change on next `git pull`

---

## License

MIT — fork it, customize it, make it yours.
