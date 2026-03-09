---
name: fpf-evolve
description: "Plan system evolution with explore/exploit balance, state-of-the-art review, and incremental migration roadmap. Use when the user needs to plan technical modernization, migration strategy, or evolutionary architecture changes."
user_invocable: true
---

# FPF Evolve

Plan system evolution using explore/exploit balance and incremental strategy.

## Usage

```
/fpf-evolve <system or component to evolve>
```

## Examples

```
/fpf-evolve "migrate monolith to microservices"
/fpf-evolve "upgrade authentication system"
/fpf-evolve "modernize data pipeline"
```

## What this skill does

Produces an evolution plan covering:
1. **Current state assessment** — where the system is now
2. **State-of-the-art review** — what modern approaches exist
3. **Explore/exploit balance** — what to experiment with vs what to optimize
4. **Incremental plan** — step-by-step evolution path
5. **Risk assessment** — what could go wrong and how to mitigate

## Instructions

When this skill is invoked:

1. Take the subject from `$ARGUMENTS`

2. Delegate to the **fpf-analyst** agent with this task:
   > Plan the evolution of the following system.
   > Load FPF sections on: evolution cycles, explore/exploit, creation chain, operational space.
   > Also load sections on: system levels, holons (for decomposition of change).
   > System: {$ARGUMENTS}

3. If the user has code in the current project, the agent should scan it to assess current state

4. Output format:

### Output Format

```
## Evolution Plan: <System>

### 1. Current State
- **Architecture:** <current structure>
- **Strengths:** <what works well>
- **Pain points:** <what needs to change>
- **Trust assessment:** <what's verified vs assumed about current state>

### 2. State of the Art
- **Modern approaches:** <relevant current practices>
- **Applicable patterns:** <what fits this system>
- **Not applicable:** <what doesn't fit and why>

### 3. Explore vs Exploit
| Area | Strategy | Rationale |
|------|----------|-----------|
| <component> | Explore: try X | <why experiment here> |
| <component> | Exploit: optimize Y | <why stabilize here> |

### 4. Incremental Plan
| Phase | Change | Risk | Rollback |
|-------|--------|------|----------|
| 1 | <smallest useful change> | Low | <how to revert> |
| 2 | <next change> | Medium | <how to revert> |
| ... | ... | ... | ... |

### 5. Risk Assessment
| Risk | Probability | Impact | Mitigation |
|------|-------------|--------|------------|
| ... | ... | ... | ... |

### Key Principle
> Change the smallest part that delivers value. Verify before proceeding to the next phase.
```

## Important

- All output in standard engineering language
- Each phase must be independently valuable (no "big bang" migrations)
- Each phase must have a rollback plan
- Trust levels for each assumption about current and target state
- If FPF-Spec.md is not found, use quick-reference principles and suggest `/fpf-setup`
