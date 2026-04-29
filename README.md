# GitHub Copilot CLI

> The power of GitHub Copilot, now in your terminal. AI-powered coding assistance directly in your command line, enabling you to build, debug, and understand code through natural language conversations.

---

## Table of Contents

- [Description](#description)
- [Installation](#installation)
- [Usage](#usage)
- [Configuration](#configuration)
- [Contributing](#contributing)
- [License](#license)
- [Contact](#contact)

---

## Description

GitHub Copilot CLI brings AI-powered coding assistance directly to your command line, powered by the same agentic harness as GitHub's Copilot coding agent. It provides intelligent assistance while staying deeply integrated with your GitHub workflow.

See [the official documentation](https://docs.github.com/copilot/concepts/agents/about-copilot-cli) for more information.

![Image of the splash screen for the Copilot CLI](https://github.com/user-attachments/assets/f40aa23d-09dd-499e-9457-1d57d3368887)

Key features:

- **Terminal-native development:** Work with Copilot coding agent directly in your command line -- no context switching required
- **GitHub integration out of the box:** Access your repositories, issues, and pull requests using natural language, all authenticated with your existing GitHub account
- **Agentic capabilities:** Build, edit, debug, and refactor code with an AI collaborator that can plan and execute complex tasks
- **MCP-powered extensibility:** Ships with GitHub's MCP server by default and supports custom MCP servers to extend capabilities
- **Full control:** Preview every action before execution -- nothing happens without your explicit approval
- **Autopilot mode:** Encourages the agent to continue working until a task is completed (experimental)
- **LSP support:** Language Server Protocol integration for enhanced code intelligence

---

## Installation

### Supported Platforms

- **Linux**
- **macOS**
- **Windows**

### Prerequisites

- (On Windows) **PowerShell** v6 or higher
- An **active Copilot subscription**. See [Copilot plans](https://github.com/features/copilot/plans?ref_cta=Copilot+plans+signup&ref_loc=install-copilot-cli&ref_page=docs).

### Install via Script (macOS and Linux)

```sh
curl -fsSL https://gh.io/copilot-install | bash
```

Or:

```sh
wget -qO- https://gh.io/copilot-install | bash
```

Use `| sudo bash` to run as root and install to `/usr/local/bin`.

Set `PREFIX` to install to `$PREFIX/bin/` directory. Defaults to `/usr/local` when run as root or `$HOME/.local` when run as a non-root user.

Set `VERSION` to install a specific version:

```sh
curl -fsSL https://gh.io/copilot-install | VERSION="v0.0.369" PREFIX="$HOME/custom" bash
```

### Install via Homebrew (macOS and Linux)

```sh
brew install copilot-cli
# Or prerelease:
brew install copilot-cli@prerelease
```

### Install via WinGet (Windows)

```sh
winget install GitHub.Copilot
# Or prerelease:
winget install GitHub.Copilot.Prerelease
```

### Install via npm (macOS, Linux, and Windows)

```sh
npm install -g @github/copilot
# Or prerelease:
npm install -g @github/copilot@prerelease
```

---

## Usage

### Launching the CLI

```sh
copilot
```

On first launch, you'll be greeted with an animated banner. If you'd like to see it again, launch with `--banner`.

If you're not logged in to GitHub, use the `/login` slash command and follow the on-screen instructions to authenticate.

#### Authenticate with a Personal Access Token (PAT)

1. Visit https://github.com/settings/personal-access-tokens/new
2. Under "Permissions," click "add permissions" and select "Copilot Requests"
3. Generate your token
4. Add the token to your environment via `GH_TOKEN` or `GITHUB_TOKEN` (in order of precedence)

### Working with Copilot

Launch `copilot` in a folder that contains code you want to work with.

By default, `copilot` utilizes Claude Sonnet 4.5. Run the `/model` slash command to choose from other available models, including Claude Sonnet 4 and GPT-5.

### Experimental Mode

Activate experimental mode for access to new features still in development:

```sh
copilot --experimental
```

Or use the `/experimental` slash command from within the CLI. Once activated, the setting is persisted in your config.

**Experimental features:**
- **Autopilot mode:** Press `Shift+Tab` to cycle through modes. Encourages the agent to continue working until a task is completed.

Each prompt submission reduces your monthly quota of premium requests by one. See [About premium requests](https://docs.github.com/copilot/managing-copilot/monitoring-usage-and-entitlements/about-premium-requests).

---

## Configuration

### LSP Servers

GitHub Copilot CLI supports Language Server Protocol (LSP) for enhanced code intelligence (go-to-definition, hover information, diagnostics).

LSP servers are not bundled -- install them separately. For example, for TypeScript:

```sh
npm install -g typescript-language-server
```

Configure LSP servers at the user level or repository level:

**User-level:** Edit `~/.copilot/lsp-config.json`

**Repository-level:** Create `.github/lsp.json` in your repository root

Example configuration:

```json
{
  "lspServers": {
    "typescript": {
      "command": "typescript-language-server",
      "args": ["--stdio"],
      "fileExtensions": {
        ".ts": "typescript",
        ".tsx": "typescript"
      }
    }
  }
}
```

Check configured LSP servers using the `/lsp` command in an interactive session.

For more information, see the [changelog](./changelog.md).

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

## License

This project is licensed under the [GitHub Copilot CLI License](LICENSE.md).

---

## Contact

- **Organization:** [ATC-O48](https://github.com/ATC-O48)
- **Project Link:** https://github.com/ATC-O48/copilot-cli

---
