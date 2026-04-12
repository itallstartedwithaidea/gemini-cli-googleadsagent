# Gemini CLI + Google Ads Agent

[English](README.md) | [Français](README.fr.md) | [Español](README.es.md) | [中文](README.zh.md) | [Nederlands](README.nl.md) | [Русский](README.ru.md) | [한국어](README.ko.md)

> **Open-source Google Ads management commands and AI agent skills for
> [Gemini CLI](https://github.com/google-gemini/gemini-cli).** Analyze campaign
> performance, audit accounts, optimize PPC spend, and generate GAQL queries —
> all from your terminal.

[![License](https://img.shields.io/github/license/google-gemini/gemini-cli)](https://github.com/google-gemini/gemini-cli/blob/main/LICENSE)
[![Version](https://img.shields.io/npm/v/@google/gemini-cli)](https://www.npmjs.com/package/@google/gemini-cli)
[![Wiki](https://img.shields.io/badge/docs-Wiki-blue)](https://github.com/itallstartedwithaidea/gemini-cli-googleadsagent/wiki)
[![Advertising Hub](https://img.shields.io/badge/ecosystem-Advertising%20Hub-orange)](https://github.com/itallstartedwithaidea/advertising-hub)
[![googleadsagent.ai](https://img.shields.io/badge/site-googleadsagent.ai-green)](https://googleadsagent.ai)

**Part of the
[Advertising Hub](https://github.com/itallstartedwithaidea/advertising-hub)
ecosystem** — 14 ad platform APIs, 25+ AI agents, MCP servers |
[googleadsagent.ai](https://googleadsagent.ai) |
[MiniAgent](https://github.com/itallstartedwithaidea/MiniAgent)

---

## Which Tool Do You Need?

| I use...                      | Install this                                                                                                                                                | Setup time |
| ----------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------- |
| **Gemini CLI** (terminal)     | [google-ads-gemini-extension](https://github.com/itallstartedwithaidea/google-ads-gemini-extension)                                                         | ~15 min    |
| **Claude** (Desktop or Code)  | [google-ads-skills](https://github.com/itallstartedwithaidea/google-ads-skills) + [google-ads-mcp](https://github.com/itallstartedwithaidea/google-ads-mcp) | ~15 min    |
| **Cursor / Windsurf / Other** | [google-ads-mcp](https://github.com/itallstartedwithaidea/google-ads-mcp) (Python, 29 tools)                                                                | ~15 min    |
| **Just want it managed**      | [googleadsagent.ai](https://googleadsagent.ai) — no setup needed                                                                                            | 0 min      |

> **Step-by-step setup guide with screenshots:**
> **[googleadsagent.ai/setup](https://googleadsagent.ai/setup/)** — covers every
> path, every credential, every gotcha. No engineering degree required.

---

## Google Ads Commands

This fork extends Gemini CLI with three Google Ads slash commands and a
domain-specific agent skill.

### `/google-ads-analyze` — Campaign Performance Analysis

```
/google-ads-analyze Show me top spending campaigns last 30 days with declining ROAS
```

- Suggests relevant GAQL queries to pull the data
- Presents findings in clear tables
- Identifies anomalies and opportunities
- Recommends specific, actionable next steps

### `/google-ads-audit` — Comprehensive Account Audit

```
/google-ads-audit Full audit of the Hopeworks nonprofit account
```

Covers 7 audit areas with severity ratings (Critical / High / Medium / Low):

- Account structure, bidding strategy, budget allocation
- Keyword health, ad creative, targeting, conversion tracking

### `/google-ads-optimize` — Optimization Recommendations

```
/google-ads-optimize We need to reduce CPA by 15% without losing volume
```

- Identifies top 3-5 highest-impact optimization opportunities
- Prioritizes by effort vs. impact with risk levels
- Covers wasted spend, bid efficiency, creative fatigue, and targeting gaps

### Google Ads Agent Skill

The included skill (`.gemini/skills/google-ads-agent/`) activates automatically
for any advertising-related question. It provides:

- **GAQL expertise** — knows Google Ads Query Language syntax, common patterns,
  and cost micro conversion
- **API v22 knowledge** — current API version, auth patterns, rate limits
- **Campaign analysis** — trends, anomalies, underperformers, budget allocation
- **Write safety** — always presents proposed changes before execution

## Quick Start — I Just Want to Use It

Most users want this path. Three commands, ~15 minutes:

```bash
# 1. Install Gemini CLI
npm install -g @google/gemini-cli

# 2. Install the Google Ads extension (MCP server + commands + skills)
gemini extensions install https://github.com/itallstartedwithaidea/google-ads-gemini-extension

# 3. Enter your Google Ads credentials (one-time setup)
gemini extensions config google-ads-agent

# 4. Start using it
gemini
> Show me my Google Ads accounts
```

You need 5 credential values from Google Ads, Google Cloud Console, and OAuth
Playground. The **[full setup guide](https://googleadsagent.ai/setup/)** walks
through every step with screenshots.

### Quick Start — I Want to Contribute / Develop

If you want to modify the CLI itself (not just use the extension):

```bash
git clone https://github.com/itallstartedwithaidea/gemini-cli-googleadsagent.git
cd gemini-cli-googleadsagent
npm install
npm run build
npm start
```

Or copy just the Google Ads commands/skills to any project:

```bash
cp -r gemini-cli-googleadsagent/.gemini/commands/google-ads-*.toml your-project/.gemini/commands/
cp -r gemini-cli-googleadsagent/.gemini/skills/google-ads-agent/ your-project/.gemini/skills/
```

## Related Projects

| Project                                                                                               | Description                                                    |
| ----------------------------------------------------------------------------------------------------- | -------------------------------------------------------------- |
| [**advertising-hub**](https://github.com/itallstartedwithaidea/advertising-hub)                       | One-stop shop for 14 ad platform APIs, MCP servers, and agents |
| [**google-ads-api-agent**](https://github.com/itallstartedwithaidea/google-ads-api-agent)             | Enterprise Google Ads agent — 28 API actions, live read/write  |
| [**google-ads-mcp**](https://github.com/itallstartedwithaidea/google-ads-mcp)                         | MCP server for Google Ads API access                           |
| [**google-ads-skills**](https://github.com/itallstartedwithaidea/google-ads-skills)                   | Claude Code / Codex / Gemini CLI skills for Google Ads         |
| [**MiniAgent**](https://github.com/itallstartedwithaidea/MiniAgent)                                   | Trainable 26M-param advertising AI + 14 MCP servers            |
| [**google-ads-claudecodeskill**](https://github.com/itallstartedwithaidea/google-ads-claudecodeskill) | Claude Code skill for Google Ads management                    |

---

## Documentation

Full documentation is available on the
**[Wiki](https://github.com/itallstartedwithaidea/gemini-cli-googleadsagent/wiki)**:

- [Getting Started](https://github.com/itallstartedwithaidea/gemini-cli-googleadsagent/wiki/Getting-Started)
  — Installation, authentication, first run
- [Commands Reference](https://github.com/itallstartedwithaidea/gemini-cli-googleadsagent/wiki/Commands-Reference)
  — Full docs for all three commands with examples
- [Google Ads Agent Skill](https://github.com/itallstartedwithaidea/gemini-cli-googleadsagent/wiki/Google-Ads-Agent-Skill)
  — GAQL patterns, API v22 knowledge, write safety
- [Configuration](https://github.com/itallstartedwithaidea/gemini-cli-googleadsagent/wiki/Configuration)
  — Settings, env variables, model selection
- [Related Projects](https://github.com/itallstartedwithaidea/gemini-cli-googleadsagent/wiki/Related-Projects)
  — Full ecosystem overview

---

## About Gemini CLI (Upstream)

This is a fork of
[google-gemini/gemini-cli](https://github.com/google-gemini/gemini-cli) with
Google Ads-specific extensions.

Gemini CLI is an open-source AI agent that brings the power of Gemini directly
into your terminal. It provides lightweight access to Gemini, giving you the
most direct path from your prompt to our model.

Learn all about Gemini CLI in the
[official documentation](https://geminicli.com/docs/).

## 🚀 Why Gemini CLI?

- **🎯 Free tier**: 60 requests/min and 1,000 requests/day with personal Google
  account.
- **🧠 Powerful Gemini 3 models**: Access to improved reasoning and 1M token
  context window.
- **🔧 Built-in tools**: Google Search grounding, file operations, shell
  commands, web fetching.
- **🔌 Extensible**: MCP (Model Context Protocol) support for custom
  integrations.
- **💻 Terminal-first**: Designed for developers who live in the command line.
- **🛡️ Open source**: Apache 2.0 licensed.

## 📦 Installation

See
[Gemini CLI installation, execution, and releases](./docs/get-started/installation.md)
for recommended system specifications and a detailed installation guide.

### Quick Install

#### Run instantly with npx

```bash
# Using npx (no installation required)
npx @google/gemini-cli
```

#### Install globally with npm

```bash
npm install -g @google/gemini-cli
```

#### Install globally with Homebrew (macOS/Linux)

```bash
brew install gemini-cli
```

#### Install globally with MacPorts (macOS)

```bash
sudo port install gemini-cli
```

#### Install with Anaconda (for restricted environments)

```bash
# Create and activate a new environment
conda create -y -n gemini_env -c conda-forge nodejs
conda activate gemini_env

# Install Gemini CLI globally via npm (inside the environment)
npm install -g @google/gemini-cli
```

## Release Cadence and Tags

See [Releases](./docs/releases.md) for more details.

### Preview

New preview releases will be published each week at UTC 23:59 on Tuesdays. These
releases will not have been fully vetted and may contain regressions or other
outstanding issues. Please help us test and install with `preview` tag.

```bash
npm install -g @google/gemini-cli@preview
```

### Stable

- New stable releases will be published each week at UTC 20:00 on Tuesdays, this
  will be the full promotion of last week's `preview` release + any bug fixes
  and validations. Use `latest` tag.

```bash
npm install -g @google/gemini-cli@latest
```

### Nightly

- New releases will be published each day at UTC 00:00. This will be all changes
  from the main branch as represented at time of release. It should be assumed
  there are pending validations and issues. Use `nightly` tag.

```bash
npm install -g @google/gemini-cli@nightly
```

## 📋 Key Features

### Code Understanding & Generation

- Query and edit large codebases
- Generate new apps from PDFs, images, or sketches using multimodal capabilities
- Debug issues and troubleshoot with natural language

### Automation & Integration

- Automate operational tasks like querying pull requests or handling complex
  rebases
- Use MCP servers to connect new capabilities, including
  [media generation with Imagen, Veo or Lyria](https://github.com/GoogleCloudPlatform/vertex-ai-creative-studio/tree/main/experiments/mcp-genmedia)
- Run non-interactively in scripts for workflow automation

### Advanced Capabilities

- Ground your queries with built-in
  [Google Search](https://ai.google.dev/gemini-api/docs/grounding) for real-time
  information
- Conversation checkpointing to save and resume complex sessions
- Custom context files (GEMINI.md) to tailor behavior for your projects

### GitHub Integration

Integrate Gemini CLI directly into your GitHub workflows with
[**Gemini CLI GitHub Action**](https://github.com/google-github-actions/run-gemini-cli):

- **Pull Request Reviews**: Automated code review with contextual feedback and
  suggestions
- **Issue Triage**: Automated labeling and prioritization of GitHub issues based
  on content analysis
- **On-demand Assistance**: Mention `@gemini-cli` in issues and pull requests
  for help with debugging, explanations, or task delegation
- **Custom Workflows**: Build automated, scheduled and on-demand workflows
  tailored to your team's needs

## 🔐 Authentication Options

Choose the authentication method that best fits your needs:

### Option 1: Login with Google (OAuth login using your Google Account)

**✨ Best for:** Individual developers as well as anyone who has a Gemini Code
Assist License. (see
[quota limits and terms of service](https://cloud.google.com/gemini/docs/quotas)
for details)

**Benefits:**

- **Free tier**: 60 requests/min and 1,000 requests/day
- **Gemini 3 models** with 1M token context window
- **No API key management** - just sign in with your Google account
- **Automatic updates** to latest models

#### Start Gemini CLI, then choose _Login with Google_ and follow the browser authentication flow when prompted

```bash
gemini
```

#### If you are using a paid Code Assist License from your organization, remember to set the Google Cloud Project

```bash
# Set your Google Cloud Project
export GOOGLE_CLOUD_PROJECT="YOUR_PROJECT_ID"
gemini
```

### Option 2: Gemini API Key

**✨ Best for:** Developers who need specific model control or paid tier access

**Benefits:**

- **Free tier**: 1000 requests/day with Gemini 3 (mix of flash and pro)
- **Model selection**: Choose specific Gemini models
- **Usage-based billing**: Upgrade for higher limits when needed

```bash
# Get your key from https://aistudio.google.com/apikey
export GEMINI_API_KEY="YOUR_API_KEY"
gemini
```

### Option 3: Vertex AI

**✨ Best for:** Enterprise teams and production workloads

**Benefits:**

- **Enterprise features**: Advanced security and compliance
- **Scalable**: Higher rate limits with billing account
- **Integration**: Works with existing Google Cloud infrastructure

```bash
# Get your key from Google Cloud Console
export GOOGLE_API_KEY="YOUR_API_KEY"
export GOOGLE_GENAI_USE_VERTEXAI=true
gemini
```

For Google Workspace accounts and other authentication methods, see the
[authentication guide](./docs/get-started/authentication.md).

## 🚀 Getting Started

### Basic Usage

#### Start in current directory

```bash
gemini
```

#### Include multiple directories

```bash
gemini --include-directories ../lib,../docs
```

#### Use specific model

```bash
gemini -m gemini-2.5-flash
```

#### Non-interactive mode for scripts

Get a simple text response:

```bash
gemini -p "Explain the architecture of this codebase"
```

For more advanced scripting, including how to parse JSON and handle errors, use
the `--output-format json` flag to get structured output:

```bash
gemini -p "Explain the architecture of this codebase" --output-format json
```

For real-time event streaming (useful for monitoring long-running operations),
use `--output-format stream-json` to get newline-delimited JSON events:

```bash
gemini -p "Run tests and deploy" --output-format stream-json
```

### Quick Examples

#### Start a new project

```bash
cd new-project/
gemini
> Write me a Discord bot that answers questions using a FAQ.md file I will provide
```

#### Analyze existing code

```bash
git clone https://github.com/google-gemini/gemini-cli
cd gemini-cli
gemini
> Give me a summary of all of the changes that went in yesterday
```

## 📚 Documentation

### Getting Started

- [**Quickstart Guide**](./docs/get-started/index.md) - Get up and running
  quickly.
- [**Authentication Setup**](./docs/get-started/authentication.md) - Detailed
  auth configuration.
- [**Configuration Guide**](./docs/reference/configuration.md) - Settings and
  customization.
- [**Keyboard Shortcuts**](./docs/reference/keyboard-shortcuts.md) -
  Productivity tips.

### Core Features

- [**Commands Reference**](./docs/reference/commands.md) - All slash commands
  (`/help`, `/chat`, etc).
- [**Custom Commands**](./docs/cli/custom-commands.md) - Create your own
  reusable commands.
- [**Context Files (GEMINI.md)**](./docs/cli/gemini-md.md) - Provide persistent
  context to Gemini CLI.
- [**Checkpointing**](./docs/cli/checkpointing.md) - Save and resume
  conversations.
- [**Token Caching**](./docs/cli/token-caching.md) - Optimize token usage.

### Tools & Extensions

- [**Built-in Tools Overview**](./docs/reference/tools.md)
  - [File System Operations](./docs/tools/file-system.md)
  - [Shell Commands](./docs/tools/shell.md)
  - [Web Fetch & Search](./docs/tools/web-fetch.md)
- [**MCP Server Integration**](./docs/tools/mcp-server.md) - Extend with custom
  tools.
- [**Custom Extensions**](./docs/extensions/index.md) - Build and share your own
  commands.

### Advanced Topics

- [**Headless Mode (Scripting)**](./docs/cli/headless.md) - Use Gemini CLI in
  automated workflows.
- [**Architecture Overview**](./docs/architecture.md) - How Gemini CLI works.
- [**IDE Integration**](./docs/ide-integration/index.md) - VS Code companion.
- [**Sandboxing & Security**](./docs/cli/sandbox.md) - Safe execution
  environments.
- [**Trusted Folders**](./docs/cli/trusted-folders.md) - Control execution
  policies by folder.
- [**Enterprise Guide**](./docs/cli/enterprise.md) - Deploy and manage in a
  corporate environment.
- [**Telemetry & Monitoring**](./docs/cli/telemetry.md) - Usage tracking.
- [**Tools reference**](./docs/reference/tools.md) - Built-in tools overview.
- [**Local development**](./docs/local-development.md) - Local development
  tooling.

### Troubleshooting & Support

- [**Troubleshooting Guide**](./docs/resources/troubleshooting.md) - Common
  issues and solutions.
- [**FAQ**](./docs/resources/faq.md) - Frequently asked questions.
- Use `/bug` command to report issues directly from the CLI.

### Using MCP Servers

Configure MCP servers in `~/.gemini/settings.json` to extend Gemini CLI with
custom tools:

```text
> @github List my open pull requests
> @slack Send a summary of today's commits to #dev channel
> @database Run a query to find inactive users
```

See the [MCP Server Integration guide](./docs/tools/mcp-server.md) for setup
instructions.

## 🤝 Contributing

We welcome contributions! Gemini CLI is fully open source (Apache 2.0), and we
encourage the community to:

- Report bugs and suggest features.
- Improve documentation.
- Submit code improvements.
- Share your MCP servers and extensions.

See our [Contributing Guide](./CONTRIBUTING.md) for development setup, coding
standards, and how to submit pull requests.

Check our [Official Roadmap](https://github.com/orgs/google-gemini/projects/11)
for planned features and priorities.

## 📖 Resources

- **[Official Roadmap](./ROADMAP.md)** - See what's coming next.
- **[Changelog](./docs/changelogs/index.md)** - See recent notable updates.
- **[NPM Package](https://www.npmjs.com/package/@google/gemini-cli)** - Package
  registry.
- **[GitHub Issues](https://github.com/google-gemini/gemini-cli/issues)** -
  Report bugs or request features.
- **[Security Advisories](https://github.com/google-gemini/gemini-cli/security/advisories)** -
  Security updates.

### Uninstall

See the [Uninstall Guide](./docs/resources/uninstall.md) for removal
instructions.

## 📄 Legal

- **License**: [Apache License 2.0](LICENSE)
- **Terms of Service**: [Terms & Privacy](./docs/resources/tos-privacy.md)
- **Security**: [Security Policy](SECURITY.md)

---

<p align="center">
  Upstream: Built with ❤️ by Google and the open source community<br>
  Google Ads extensions by <a href="https://github.com/itallstartedwithaidea">John Williams</a> — Team Lead, Paid Media @ Seer Interactive | <a href="https://googleadsagent.ai">googleadsagent.ai</a>
</p>
