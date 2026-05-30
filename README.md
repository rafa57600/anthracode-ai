<div align="center">

# AnthraCode

**An AI coding assistant for your terminal — a hardened fork of [OpenCode](https://github.com/sst/opencode) with production-quality fixes, new tools, and first-class Windows + Linux support.**

```bash
npm install -g anthracode-ai
anthracode
```

[![npm](https://img.shields.io/npm/v/anthracode-ai?color=4F46E5&label=anthracode-ai)](https://www.npmjs.com/package/anthracode-ai)
[![platforms](https://img.shields.io/badge/platforms-Windows%20x64%20%7C%20Linux%20x64-444)](#supported-platforms)
[![license](https://img.shields.io/badge/license-MIT-444)](LICENSE)

</div>

---

## What is it?

AnthraCode runs in your terminal as a full-screen TUI. Connect it to any AI provider — Anthropic, OpenAI, Google Gemini, Groq, Ollama, and 40+ others — then ask it to read, edit, run, and reason about your codebase.

It works on your **local files and tools**. No cloud upload, no proprietary workspace.

---

## Features

### Tools

| Tool | Description |
|------|-------------|
| `read` / `edit` / `write` | Read, patch, or create files |
| `shell` | Run commands, stream output, kill when done |
| `grep` / `glob` | Fast codebase search |
| `ast` | Semantic code search — definitions, references, symbols |
| `worktree_enter` / `worktree_exit` | Isolated git worktrees per session |
| `repl` | Run Python / Node / Bun code inline |
| `notebook_edit` | Edit Jupyter notebooks by cell index or UUID |
| `checkpoint` | Snapshot + restore working-tree state |
| `multi_edit` | Atomic multi-file edits in one step |
| `typecheck` / `test_runner` | Surface TypeScript errors and test results |
| `pty_exec` / `pty_read` | Full pseudo-terminal for interactive programs |
| `webfetch` / `websearch` | Fetch URLs and search the web |
| `mcp_*` | Connect any MCP server as a tool source |

### Hardening vs upstream OpenCode

- **Windows + Linux x64 builds** — native binaries, cross-compiled and tested
- **Windows TUI** — alternate-screen mode, no terminal flood or stray escape codes
- **Permission approval timeout** — auto-denies after 60s if the TUI disconnects
- **Config parse crash → clear error** — shows file + line + column on bad JSON/JSONC
- **Compaction spinner** — visual feedback during context compaction
- **Background process buffer cap** — 10 MB ceiling on background output
- **Codex/ChatGPT usage guard** — reset-aware "usage limit reached" instead of a retry storm
- **Self-healing install** — recovers when npm skips the platform binary
- **Commit attribution** — optional trailer on agent-made commits (opt-out)

---

## Install

```bash
# npm (recommended)
npm install -g anthracode-ai

# pnpm
pnpm add -g anthracode-ai

# yarn
yarn global add anthracode-ai
```

### Supported platforms

**Windows x64** · **Linux x64**

> macOS builds are planned.

---

## Quick start

```bash
# Launch in the current project directory
anthracode

# Launch in a specific directory
anthracode /path/to/project
```

On first launch, AnthraCode prompts you to configure a provider.

---

## Configuration

Config file: `~/.config/anthracode/config.json` (or `anthracode.json` in the project root).

```json
{
  "$schema": "https://opencode.ai/config.json",
  "provider": {
    "anthropic": {
      "options": { "apiKey": "sk-ant-..." }
    }
  },
  "model": "anthropic/claude-sonnet-4-5"
}
```

Supported providers include Anthropic, OpenAI, Google Gemini, Groq, Mistral, Bedrock, Azure, Ollama, LM Studio, and any OpenAI-compatible endpoint.

For ChatGPT Plus / Codex browser auth:

```bash
anthracode auth login openai
```

---

## Updating

```bash
npm install -g anthracode-ai@latest
```

AnthraCode checks for updates on launch (cached 2h).

---

## Relation to OpenCode

AnthraCode is a fork of [OpenCode](https://github.com/sst/opencode), maintained by [@rafa57600](https://github.com/rafa57600). It tracks upstream releases with selective cherry-picks, production bug fixes, and AnthraCode-specific features.

---

## Privacy

AnthraCode is **local-first** — your code and prompts stay on your machine and are
sent only to the AI provider you configure. There are **no analytics or tracking
SDKs**. See [PRIVACY.md](PRIVACY.md) for the full, code-audited data-flow list.

---

## Legal & community

| Document | What it covers |
|----------|----------------|
| [LICENSE](LICENSE) | MIT (source code) + trademark reservation |
| [TERMS.md](TERMS.md) | Terms of use for the distributed binaries |
| [PRIVACY.md](PRIVACY.md) | What data leaves your machine, and when |
| [SECURITY.md](SECURITY.md) | How to report a vulnerability |
| [TRADEMARK.md](TRADEMARK.md) | Use of the AnthraCode name and logo |
| [NOTICE](NOTICE) | Third-party attributions |
| [CONTRIBUTING.md](CONTRIBUTING.md) | How to report bugs and improve docs |
| [CODE_OF_CONDUCT.md](CODE_OF_CONDUCT.md) | Community standards |

---

## License

AnthraCode's **source code** is licensed under the [MIT License](LICENSE) (the
original OpenCode copyright is retained). The **AnthraCode name and logo** are
trademarks — see [TRADEMARK.md](TRADEMARK.md). Use of the distributed binaries is
additionally governed by [TERMS.md](TERMS.md).
