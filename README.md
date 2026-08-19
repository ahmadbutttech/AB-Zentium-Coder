<div align="center">

# ◈ Zentium Lab AI

**Agentic coding assistant for your terminal and desktop.**

Multi-provider · Tool-using · Streaming · Cross-platform

[![Version](https://img.shields.io/badge/version-2.0.0-22d3c7?style=flat-square)](#)

<br>

<!-- Demo SVG from CDN -->
<img src="https://cdn.imageurlgenerator.com/uploads/ebef913f-5f42-4502-aa36-cdc9d7165f70.svg" alt="Zentium Lab AI terminal demo" width="850">

<br>
<br>

Zentium Lab AI drops into a project, reads what it needs, edits real files, runs real commands, and reports back — from a terminal REPL or a desktop app, whichever fits the moment. It isn't tied to one model provider: point it at Claude, GPT, Gemini, or half a dozen others and keep the same workflow.

<br>

## Contents

- [Highlights](#highlights)
- [Providers & Models](#providers--models)
- [Tools](#tools)
- [Terminal Features](#terminal-features)
- [Desktop App](#desktop-app)
- [Code Intelligence](#code-intelligence)
- [MCP Support](#mcp-support)
- [Install](#install)
- [Quick Start](#quick-start)
- [Keyboard Shortcuts](#keyboard-shortcuts)
- [Slash Commands](#slash-commands)
- [Updating](#updating)
- [Configuration](#configuration)
- [License](#license)

<br>

## Highlights

- **Full agentic loop** — plans, calls tools, reads the results, and keeps going until the task is actually done, with permission prompts before anything destructive.
- **Multi-provider from day one** — Anthropic, OpenAI, Google Gemini, Zhipu GLM, DeepSeek, Mistral, Groq, and OpenRouter, all behind one interface.
- **Two front ends, one engine** — a fast terminal REPL and a PySide6 desktop GUI, sharing the same tools, sessions, and config.
- **Live streaming everywhere** — token-by-token output and a real-time tool activity feed, not a spinner.
- **Deep code understanding** — an AST-based repo graph across 20+ languages, with an LSP fallback when a tree-sitter grammar isn't available.
- **Extensible by design** — MCP client for external tool servers, a skills system for reusable playbooks, and custom instructions per project.
- **Runs as a real citizen of your OS** — system control tools, a live resource monitor, cost tracking, and a self-installing Windows build.

<br>

## Providers & Models

Switch providers without switching workflows — the same tool loop, the same commands, the same sessions.

| Provider | Notes |
|---|---|
| **Anthropic Claude** | Sonnet, Opus, Haiku, and preview tiers |
| **OpenAI GPT** | GPT-5.x family, including a Codex-tuned variant |
| **Google Gemini** | Gemini 3.x and 2.5, native SDK or Vertex-compatible gateway |
| **Zhipu GLM (Z.AI)** | GLM-4.x line, including a fast "flash" default |
| **DeepSeek** | Chat and reasoning-tuned models |
| **Mistral AI** | General, code (Codestral), and vision (Pixtral) models |
| **Groq** | Low-latency inference for Llama, Mixtral, Gemma, and Qwen |
| **OpenRouter** | One key, routed access to models across every major lab |

Each provider stores its own API key, base URL, and default model, so you can keep several configured and switch mid-session.

<br>

## Tools

Everything the agent can actually *do* — every call goes through a permission check before it touches your disk or your system.

**Filesystem & code**
- Read — files, directories, and images, with a graph-aware skeleton view before full content
- Write / Edit — create and patch files with targeted diffs
- Glob / Grep — fast pattern-based file discovery and content search
- Repo graph & AST skeleton — structural map of a file or whole project

**Shell & system**
- Bash — persistent working-directory shell execution
- System control — shutdown, restart, lock, and sleep, on Windows and POSIX
- System monitor — live CPU, RAM, disk, and temperature

**Web & data**
- Web search and web fetch
- Weather lookups by location or coordinates
- Date/time resolution and natural-language date queries
- Document reader for common office and text formats

**Workflow**
- Todo list — the agent tracks and updates its own task list mid-run
- Skills — reusable prompt playbooks loaded from your project
- Session memory — save, list, and resume past conversations
- Self-update — check, download, and install new versions from the terminal

**Connectivity**
- MCP client — connect, list, call, refresh, and disconnect external MCP servers, with bearer-token and OAuth 2.0 + PKCE support
- Sub-agent dispatch — delegate a scoped task to a fresh agent instance and get a clean summary back

<br>

## Terminal Features

- Rich, colorized REPL built on `prompt_toolkit` and `rich` — history search, multi-line input, and graceful plain-text fallback if either library is missing
- Live tool activity feed with per-step status, not a black-box "thinking…"
- Auto-continue when a tool-call limit is hit mid-task, so long jobs don't stall waiting for a manual nudge
- Running cost tracker — token counts and estimated USD spend for the session
- Crash safety net — a persistent flag and log so a bad exit is recoverable, not a black hole

<br>

## Desktop App

A PySide6 GUI for people who want the same agent without living in a terminal:

- Sidebar chat history across sessions
- Built-in web preview tab
- Settings panel for provider/model switching and update management
- Same permission model as the terminal — nothing runs without a visible prompt

<br>

## Code Intelligence

- Tree-sitter–based structural graphs across Python, JavaScript, TypeScript, C, C++, Java, Go, Rust, and more
- Falls back to a local Language Server when a tree-sitter grammar isn't installed
- Smart file reads pull the structural skeleton first, then only the byte ranges actually needed — large files stay cheap to reason about
- `/graph` command for an on-demand AST map of any file or directory

<br>

## MCP Support

Zentium speaks [Model Context Protocol](https://modelcontextprotocol.io) natively:

- Connect to any MCP server over HTTP(S), with bearer-token or full OAuth 2.0 + PKCE flows
- List active connections, call their tools directly, refresh credentials, or disconnect
- Works alongside the built-in tool set — an MCP tool and a native tool are just two entries in the same permission-gated loop

<br>

## Install

```bash
git clone https://github.com/ahmadbutttech/AB-Zentium-Coder.git
cd AB-Zentium-Coder
pip install -r requirements.txt
