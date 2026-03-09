# FPF-AI — First Principles Framework for Claude Code

A Claude Code plugin that applies the First Principles Framework (FPF) as a thinking framework for software engineering tasks.

## What it does

FPF-AI helps you think systematically about software systems:

- **Analyze** systems by decomposing them into components, boundaries, trust levels, and responsibilities
- **Design** architectures using part-whole decomposition, interface contracts, and composition rules
- **Review** code and architecture against engineering principles (boundary discipline, naming quality, composition correctness)
- **Look up** FPF concepts and get explanations in standard engineering language
- **Characterize** ideas with measurable metrics and scoring criteria
- **Build terminology** sheets with precise definitions and dangerous aliases
- **Plan evolution** with explore/exploit balance and incremental roadmaps

All output uses **standard engineering language** — no FPF jargon.

## Prerequisites

1. [Claude Code](https://docs.anthropic.com/en/docs/claude-code) installed
2. FPF-Spec.md — the framework specification (~50,000 lines)

## Installation

```bash
# Clone the plugin
git clone https://github.com/user/fpf-ai.git

# Install in Claude Code (from any project)
claude plugins add /path/to/fpf-ai
```

## Setup

After installing the plugin, download the FPF specification:

```
/fpf-setup
```

This downloads `FPF-Spec.md` from the official repository into your current project root.

## Commands

| Command | Description |
|---------|-------------|
| `/fpf-setup` | Download FPF-Spec.md to project root |
| `/fpf-analyze <description>` | Systematic analysis of a system or problem |
| `/fpf-design <description>` | Architecture design using first principles |
| `/fpf-review [files]` | Review code or architecture |
| `/fpf-lookup <concept>` | Find and explain an FPF concept |
| `/fpf-characterize <idea>` | Build characteristics chain with metrics |
| `/fpf-terms <domain>` | Build terminology sheet for a domain |
| `/fpf-evolve <system>` | Plan system evolution |

## How it works

FPF-Spec.md is too large for the context window. The plugin uses a pre-built index system:

1. Maps your engineering topic to relevant FPF sections
2. Looks up exact line ranges in the master index
3. Loads only the needed 200-500 lines (out of 50,000)
4. Translates FPF concepts to standard engineering language

## License

MIT
