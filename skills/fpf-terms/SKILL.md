---
name: fpf-terms
description: "Build a terminology sheet (glossary) for a domain with precise definitions, common names, dangerous aliases, and usage contexts. Use when the user needs to establish shared vocabulary, resolve naming conflicts, or document domain terms."
user_invocable: true
---

# FPF Terms

Build a structured terminology sheet for a domain.

## Usage

```
/fpf-terms <domain or topic>
```

## Examples

```
/fpf-terms "payment processing"
/fpf-terms "user authentication"
/fpf-terms "order management"
```

## What this skill does

Creates a terminology sheet (Ubiquitous Terminology Sheet) covering:
- **Technical name** — precise, unambiguous term
- **Common name** — everyday usage
- **Definition** — what it means in this specific context
- **Context** — where this term applies
- **Dangerous aliases** — similar-sounding terms that mean something different
- **Related terms** — connected concepts

## Instructions

When this skill is invoked:

1. Take the domain from `$ARGUMENTS`

2. Read `${CLAUDE_PLUGIN_ROOT}/reference/fpf-quick-reference.md` (section on Naming Discipline)

3. If FPF-Spec.md is available, search for naming-related sections in the index and load them

4. If the user has code in the current project, scan for relevant domain terms using Grep/Glob

5. Build the terminology sheet:

### Output Format

```
## Terminology Sheet: <Domain>

### Terms

#### 1. <Technical Name>
- **Common name:** <everyday name>
- **Definition:** <precise definition in this context>
- **Context:** <where/when this term is used>
- **Dangerous aliases:** <terms that look similar but mean something different>
- **Example:** <concrete usage example>

#### 2. <Next Term>
...

### Naming Rules for This Domain
1. Always use "<term>" when referring to <concept>
2. Never use "<alias>" — it means <something else> in <other context>
3. ...

### Cross-Reference
| Term | Used in | Confused with |
|------|---------|--------------|
| ...  | ...     | ...          |
```

## Important

- All output in standard engineering language
- Scan the user's codebase for existing terms if possible
- Flag naming conflicts (same name, different meanings)
- Flag naming gaps (important concepts without names)
- Keep definitions short and precise (1-2 sentences)
