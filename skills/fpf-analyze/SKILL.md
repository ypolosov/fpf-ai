---
name: fpf-analyze
description: "Systematic analysis of a software system or engineering problem using first principles. Use when the user wants to understand system structure, find architectural issues, or decompose a complex problem. Accepts a system description as argument."
user_invocable: true
---

# FPF Analyze

Perform a systematic first-principles analysis of a software system or engineering problem.

## Usage

```
/fpf-analyze <system or problem description>
```

## What this skill does

Analyzes the described system across six dimensions:
1. **Component boundaries** — what are the parts and where do they start/end?
2. **Part-whole decomposition** — how do parts compose into the whole?
3. **Interface contracts** — what do components expose and consume?
4. **Trust calibration** — what's verified vs assumed vs unknown?
5. **Responsibility assignment** — who does what and delivers what?
6. **Evolution readiness** — where is the system exploring vs exploiting?

## Instructions

When this skill is invoked:

1. Take the user's description from `$ARGUMENTS`

2. Delegate to the **fpf-analyst** agent with this task:
   > Analyze the following system using the full analysis framework.
   > Load relevant FPF sections based on the topic.
   > System description: {$ARGUMENTS}

3. The agent will:
   - Read `${CLAUDE_PLUGIN_ROOT}/reference/topic-to-sections.md` to identify relevant sections
   - Read `${CLAUDE_PLUGIN_ROOT}/reference/fpf-index.md` for line ranges
   - Load specific sections from FPF-Spec.md
   - Produce a structured analysis

4. Output format:
   - **System Overview** (2-3 sentences)
   - **Component Map** (table or list)
   - **Key Findings** (numbered, prioritized)
   - **Trust Assessment** (Fact / Guess / Rumor breakdown)
   - **Recommendations** (actionable, prioritized)

## Important

- All output in standard engineering language — no FPF jargon
- If FPF-Spec.md is not found, suggest running `/fpf-setup`
- Focus on practical, actionable insights
