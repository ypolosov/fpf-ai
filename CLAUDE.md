# FPF-AI Plugin Instructions

## What is this plugin

FPF-AI applies the First Principles Framework (FPF) — a systems-engineering specification by Anatoly Levenchuk — as a thinking framework for software development. It helps with systematic analysis, architecture design, code reviews, and terminology.

## Critical rule: No FPF jargon

ALL outputs MUST use standard engineering language. Never expose raw FPF terminology to the user.

Translation table (FPF term → engineering term):
| FPF Term | Engineering Term |
|---|---|
| Holon | Component with defined boundary |
| Bounded context | Service/module domain boundary |
| F-G-R calculus | Trust levels (Fact / Guess / Rumor) |
| Mereology | Part-whole decomposition |
| Alpha | Key work product / artifact |
| Role-Method-Work | Responsibility-Process-Deliverable |
| Affordance | Interface capability / contract |
| Operational space | Runtime environment constraints |
| Creation chain | Build/delivery pipeline |
| Name card | Term definition with context |

## How the index system works

FPF-Spec.md is ~50,000 lines — never read it entirely. Always use this workflow:

1. **Determine topic** — what engineering domain does the user's question relate to?
2. **Read `reference/topic-to-sections.md`** — map the topic to FPF section IDs
3. **Read `reference/fpf-index.md`** — get exact line ranges for those sections
4. **Read FPF-Spec.md with line ranges** — load only the relevant 200-500 lines
5. **Read `reference/fpf-quick-reference.md`** — for translation context

Use `${CLAUDE_PLUGIN_ROOT}` for all paths within the plugin.

## Plugin components

### Skills (user-invocable)
- `/fpf-analyze` — systematic analysis of a system or problem
- `/fpf-design` — architecture design using first principles
- `/fpf-review` — code or architecture review
- `/fpf-lookup` — find and explain an FPF concept
- `/fpf-characterize` — build a characteristics chain (idea → metrics → scoring)
- `/fpf-terms` — build a terminology sheet for a domain
- `/fpf-evolve` — plan system evolution

### Agents
- **fpf-analyst** — deep analysis agent (main model), used by analyze/design/review skills
- **fpf-advisor** — quick recommendations agent (haiku), uses only quick-reference

### Commands
- `/fpf-setup` — download FPF-Spec.md from GitHub to project root

## File locations

- Reference files: `${CLAUDE_PLUGIN_ROOT}/reference/`
- FPF-Spec.md: expected at `./FPF-Spec.md` in user's project root (downloaded via `/fpf-setup`)

## Creation Chain (optional context)

fpf-ai can serve as a thinking layer in a creation chain — a sequence of
creating systems where each creates value for the next.
See `${CLAUDE_PLUGIN_ROOT}/reference/creation-chain.md` for details.
fpf-ai is fully universal — this context is informational only.
