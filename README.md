# AI Era Action Principles

A skill that helps AI assistants turn vague goals into expert resources, meaningful gateway actions, evidence, and persistent learning.

## The Problem

In the AI era, information is abundant.
But ordinary users still struggle with:
- not knowing which resources experts check first
- relying on noisy tutorials and feeds
- taking toy-level actions that do not build real understanding
- vibe-coding without retention
- failing to preserve lessons as reusable playbooks

## The Solution

This skill makes the assistant follow a resource-action loop:

```
Need / Problem
→ Expert Resource Map
→ Expert Operating Path
→ Gateway Minimal Action
→ Evidence
→ Persistent Note
→ Optional Retro
```

## Core Principles

1. Expert Resources First
2. Resource → Action → Evidence
3. Gateway Minimal Action
4. Persistence Over One-Off Answers
5. Optional Retro After Action

## Why This Exists

AI gives ordinary users access to powerful tools, platforms, and information.
But access is not the same as capability.

Many people can open the same documentation, platforms, repositories, and feeds.
Experts get more value because they know:
- which resources contain primary truth
- which resources are noisy
- what actions to take on each resource
- what evidence proves progress
- what to preserve for next time

This skill makes that workflow explicit.

## Install

**Option A: Claude Code Plugin (recommended)**

From within Claude Code, first add the marketplace:

```
/plugin marketplace add dli1986/AI-era-action-principles-skills
```

Then install the plugin:

```
/plugin install ai-era-action-principles-skills@ai-era-action-principles
```

This installs the skill as a Claude Code plugin, making it available across all your projects.

**Option B: CLAUDE.md (per-project)**

New project:

```bash
curl -o CLAUDE.md https://raw.githubusercontent.com/dli1986/AI-era-action-principles-skills/main/CLAUDE.md
```

Existing project (append):

```bash
echo "" >> CLAUDE.md
curl https://raw.githubusercontent.com/dli1986/AI-era-action-principles-skills/main/CLAUDE.md >> CLAUDE.md
```

## Examples

See [EXAMPLES.md](EXAMPLES.md) for complete worked examples showing how a vague goal becomes an expert resource map, a gateway minimal action, and a persistent note.

## How to Know It's Working

The skill is working if you see:

- Resource lists with attached actions — not bare link dumps
- Gateway actions that expose real workflows — not "hello world" starters
- Compact Action Cards by default — not unsolicited long tutorials
- Something saved at the end — not just a chat answer

## Repository Structure

```text
.claude-plugin/
├── plugin.json          ← plugin descriptor
└── marketplace.json     ← marketplace descriptor
skills/
└── ai-era-action-principles/
    ├── SKILL.md          ← runtime behavior contract
    ├── references/       ← domain routing, patterns, playbooks
    └── templates/        ← action card and dossier templates
CLAUDE.md                 ← direct install (append to your CLAUDE.md)
EXAMPLES.md               ← standalone worked examples
```

## License

MIT
