<div align="center">

# Command Code

### The first frontier coding agent that both builds software and continuously learns your coding taste.

Ships full-stack projects, features, fixes bugs, writes tests, and refactors — all while learning how you write code.

---

**Install**

```sh
npm i -g command-code
```

**Run**

```sh
cd your-project && cmd
```

[Explore the quickstart guide &rarr;](#quickstart)

</div>

---

## Take command of your code

<table>
<tr>
<td align="center" width="33%">

### Models
**Opus, Sonnet, Haiku**

Claude frontier LLMs

</td>
<td align="center" width="33%">

### Taste
**`taste-1` meta neuro-symbolics**

Learns how you code

</td>
<td align="center" width="33%">

### Extend
**CLI, Skills, MCP**

Build on top of it

</td>
</tr>
<tr>
<td align="center" width="33%">

### Code
**10x faster**

Ship features fast

</td>
<td align="center" width="33%">

### Review
**2x quicker**

Slash review time in half

</td>
<td align="center" width="33%">

### Bugs
**5x slashed**

Catch issues early

</td>
</tr>
</table>

---

## What you can do

- **Build projects in anyone's taste** — match any coding style automatically
- **Automate the tedious stuff** — repetitive tasks, boilerplate, scaffolding
- **Review PRs in seconds** — get instant, contextual feedback
- **Create commits and pull requests** — ship directly from the CLI
- **Refactor without breaking things** — safe, taste-aware transformations
- **Plan before you build** — structured reasoning before code generation
- **Connect your tools with MCP** — extend with Model Context Protocol servers
- **Customize with skills and taste** — tailor behavior to your workflow
- **Write tests and docs** — generate comprehensive coverage and documentation
- **Pipe, script, and automate** — composable CLI for any workflow

[Explore common workflows and examples &rarr;](#common-workflows)

---

## How taste works

<table>
<tr>
<td width="33%">

### Continuously Learning

Every accept, reject, and edit becomes a signal that shapes your taste profile.

</td>
<td width="33%">

### Meta Neuro-Symbolic AI

`taste-1` enforces the invisible logic of your choices and coding taste.

</td>
<td width="33%">

### Share with your team

Portable via `npx taste push/pull`. Rules decay. Taste compounds.

</td>
</tr>
</table>

[Explore how taste learns your style &rarr;](#taste)

---

## Explore the docs

| Topic | Description |
|-------|-------------|
| **[Core Concepts](#core-concepts)** | Interactive, headless, and plan modes. |
| **[Taste](#taste)** | Learns your coding style and applies it to every project automatically. |
| **[Skills](#skills)** | Reusable slash commands to share. |
| **[MCP](#mcp)** | Connect external tools and services via Model Context Protocol. |
| **[Studio](#studio)** | Manage taste profiles, API keys, and team organizations. |
| **[Troubleshooting](#troubleshooting)** | Common issues, FAQs, and errors. |

---

## Quickstart

### 1. Install

```sh
npm i -g command-code
```

### 2. Navigate to your project

```sh
cd your-project
```

### 3. Launch

```sh
cmd
```

On first launch, you'll be guided through authentication and initial taste calibration.

---

## Core Concepts

Command Code operates in three modes:

| Mode | Description | Usage |
|------|-------------|-------|
| **Interactive** | Conversational coding with real-time feedback | `cmd` (default) |
| **Headless** | Non-interactive execution for CI/CD and scripts | `cmd --headless "task"` |
| **Plan** | Structured planning before code generation | `cmd --plan` |

### Models

Command Code is powered by Claude frontier LLMs:

- **Opus** — Maximum capability for complex, multi-step tasks
- **Sonnet** — Balanced performance for everyday development
- **Haiku** — Fast responses for quick edits and simple tasks

Switch models with the `/model` command during an interactive session.

---

## Taste

`taste-1` is a meta neuro-symbolic system that continuously learns your coding preferences.

### How it works

1. **Observation** — Every accept, reject, and edit you make is recorded as a signal
2. **Modeling** — `taste-1` builds a symbolic representation of your coding patterns
3. **Enforcement** — Your taste profile is applied to all generated code automatically

### Sharing taste profiles

```sh
# Push your taste profile to the team
npx taste push

# Pull a team member's taste profile
npx taste pull
```

> Rules decay. Taste compounds.

---

## Skills

Skills are reusable slash commands that extend Command Code's capabilities.

```sh
# List available skills
/skills

# Use a skill
/skill:deploy
```

Create custom skills as markdown files and share them with your team.

---

## MCP

Command Code supports the [Model Context Protocol](https://modelcontextprotocol.io/) for connecting external tools and services.

### Built-in MCP servers

Command Code ships with GitHub's MCP server by default.

### Custom MCP servers

Configure additional MCP servers in your project's `.command/mcp.json`:

```json
{
  "servers": {
    "my-server": {
      "command": "npx",
      "args": ["my-mcp-server"]
    }
  }
}
```

---

## Studio

Manage your Command Code environment:

- **Taste profiles** — Create, edit, and switch between taste profiles
- **API keys** — Configure authentication and model access
- **Team organizations** — Manage team members and shared configurations

---

## Common Workflows

### Build a new feature

```sh
cmd "add dark mode toggle to settings page"
```

### Fix a bug

```sh
cmd "fix the race condition in the auth flow"
```

### Review a PR

```sh
cmd "review PR #42"
```

### Write tests

```sh
cmd "write tests for the payment module"
```

### Refactor

```sh
cmd "refactor the database layer to use connection pooling"
```

### Pipe and automate

```sh
cat issue.md | cmd --headless
```

---

## CLI Reference

### `devin` entry point

```sh
devin                            # Start interactive REPL (no prompt)
devin -- your prompt here        # Start REPL with initial prompt
devin -p "prompt"                # Single-turn, no REPL: print response to stdout and exit
devin -p -- prompt words here    # Same, using -- separator (still works)
```

| Flag | Description |
|------|-------------|
| `-p`, `--print` | Single-turn mode — print response and exit |
| `-m`, `--model <name>` | Select model (`opus`, `sonnet`, `haiku`) |
| `--headless` | Non-interactive mode for CI/CD and scripts |
| `--plan` | Structured planning before code generation |
| `-h`, `--help` | Show help message |
| `-v`, `--version` | Show version |

### `cmd` entry point

```
Usage: cmd [options] [prompt]

Options:
  --headless          Run in non-interactive mode
  --plan              Enter plan mode
  --banner            Show the splash banner
  --experimental      Enable experimental features
  --model <name>      Set the model (opus, sonnet, haiku)

Slash Commands:
  /model              Switch the active model
  /skills             List available skills
  /skill:<name>       Run a specific skill
  /taste              View or edit your taste profile
  /login              Authenticate with your account
  /feedback           Submit feedback
  /experimental       Toggle experimental features
  /lsp                Check configured LSP servers
```

---

## Troubleshooting

| Issue | Solution |
|-------|----------|
| `command not found: cmd` | Ensure `command-code` is installed globally: `npm i -g command-code` |
| Authentication failed | Run `/login` to re-authenticate |
| Model not available | Check your subscription plan supports the selected model |
| MCP server not connecting | Verify your `.command/mcp.json` configuration |
| Taste not applying | Run `npx taste pull` to sync your latest profile |

---

## Contributing

Contributions are welcome! Please follow these guidelines:

1. **Fork the repository**
2. **Create a new branch**
   ```sh
   git checkout -b feature/your-feature-name
   ```
3. **Make your changes**
4. **Test your changes**
5. **Commit and push**
   ```sh
   git commit -m "Add feature: your-feature-name"
   git push origin feature/your-feature-name
   ```
6. **Open a pull request**

**Issues & Suggestions:**
Open an issue for bugs, questions, or feature requests using the provided issue templates.

**Feedback from the CLI:**
Run `/feedback` from within the CLI to submit a confidential feedback survey.

---

## Next Steps

- **[Quickstart](#quickstart)** — Walk through your first real task
- **[Common Workflows](#common-workflows)** — Real examples of what to build
- **[CLI Reference](#cli-reference)** — Every command, flag, and configuration option
- **[Core Concepts](#core-concepts)** — Interactive, headless, and plan modes

[Explore the community on Discord &rarr;](https://discord.gg/command-code)

---

## License

This project is licensed under the [Command Code License](LICENSE.md).

---

## Contact

- **Organization:** [ATC-O48](https://github.com/ATC-O48)
- **Project Link:** https://github.com/ATC-O48/copilot-cli

---
