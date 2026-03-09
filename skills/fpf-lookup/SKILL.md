---
name: fpf-lookup
description: "Find and explain an FPF concept in standard engineering language. Use when the user asks about a specific FPF concept, wants to understand a term, or needs to find a section in the FPF specification. Accepts a concept name or keyword as argument."
user_invocable: true
---

# FPF Lookup

Find and explain an FPF concept in standard engineering language.

## Usage

```
/fpf-lookup <concept or keyword>
```

## Examples

```
/fpf-lookup holon
/fpf-lookup trust calculus
/fpf-lookup bounded context
/fpf-lookup evolution cycles
```

## Instructions

When this skill is invoked:

1. Take the search term from `$ARGUMENTS`

2. **Search in quick reference first**:
   Read `${CLAUDE_PLUGIN_ROOT}/reference/fpf-quick-reference.md`
   — Check if the concept is one of the 10 key concepts

3. **Search in the master index**:
   Use Grep to search `${CLAUDE_PLUGIN_ROOT}/reference/fpf-index.md` for the term
   — Find matching section(s) with line ranges

4. **Load the relevant section from FPF-Spec.md**:
   Read FPF-Spec.md with the line range from the index
   — Load only the specific section (200-500 lines max)

5. **Explain in engineering language**:
   - What is this concept? (1-2 sentences, plain language)
   - Why does it matter for software engineering? (1-2 sentences)
   - Engineering parallel (what's the equivalent in standard practice?)
   - Practical example (how you'd apply this in a real project)
   - Related concepts (what else to look at)

## Output Format

```
## <Concept Name> (Engineering Translation)

**What it is:** ...

**Why it matters:** ...

**Engineering parallel:** ...

**Example:** ...

**Related:** concept1, concept2, concept3

**Source:** FPF-Spec.md lines N-M (section title)
```

## Important

- Translate ALL FPF terms to engineering language in the output
- If the concept isn't found, suggest the closest match
- If FPF-Spec.md is not found, explain from quick-reference and suggest `/fpf-setup`
- Keep explanations practical and grounded in real engineering
