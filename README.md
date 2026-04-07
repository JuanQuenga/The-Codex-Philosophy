# Codex's Philosophy

A system prompt designed to make **Claude Opus** behave more like **OpenAI's Codex** — careful, context-aware, and surgically precise when editing code.

## What is this?

Codex (OpenAI's code-focused model) is known for reading deeply before writing, making minimal targeted edits, and never touching code it wasn't asked to change. These are great habits that any coding AI should follow.

This repo contains a reusable system prompt (`SYSTEM_PROMPT.md`) that instills those same principles into Claude Opus (or any Claude model). Drop it into your `CLAUDE.md`, project instructions, or system prompt to get Codex-style behavior:

- **Read before you write** — understand the full context before making changes
- **Surgical patches over rewrites** — smallest possible diff, every time
- **No unsolicited refactors** — only touch what you're asked to touch
- **Aggressive context gathering** — trace imports, callers, tests, and patterns before editing

## Usage

Copy the contents of [`SYSTEM_PROMPT.md`](./SYSTEM_PROMPT.md) into your project's `CLAUDE.md` file, or include it as a system prompt when working with Claude.

## Why?

Large language models tend to over-edit — rewriting entire files, renaming things for style, and making "while I'm here" changes that introduce bugs. The Codex philosophy keeps the model focused: understand first, change only what's needed, and respect the existing codebase.
