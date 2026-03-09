---
name: fpf-characterize
description: "Build a characteristics chain from idea to measurable metrics, indicators, scoring criteria, and decision thresholds. Use when the user needs to define quality attributes, acceptance criteria, SLAs, or measurable properties for a system or feature."
user_invocable: true
---

# FPF Characterize

Build a characteristics chain: from abstract idea to measurable engineering metrics.

## Usage

```
/fpf-characterize <idea, feature, or quality attribute>
```

## Examples

```
/fpf-characterize "payment processing reliability"
/fpf-characterize "API response time"
/fpf-characterize "developer onboarding experience"
```

## What this skill does

Builds a complete measurement chain:

1. **Characteristic** — the abstract quality (e.g., "reliability")
2. **Indicators** — observable signs of that quality (e.g., "uptime percentage", "error rate")
3. **Metrics** — specific measurements (e.g., "99.9% uptime over 30 days")
4. **Scoring** — how to rate the metric (e.g., "green >99.9%, yellow 99-99.9%, red <99%")
5. **Decision criteria** — what actions to take at each score level

## Instructions

When this skill is invoked:

1. Take the subject from `$ARGUMENTS`

2. Read `${CLAUDE_PLUGIN_ROOT}/reference/fpf-quick-reference.md` for context

3. If FPF-Spec.md is available, search `${CLAUDE_PLUGIN_ROOT}/reference/fpf-index.md` for sections on characteristics, quality attributes, and indicators, then load relevant sections

4. Build the characteristics chain:

### Output Format

```
## Characteristics Chain: <Subject>

### 1. Characteristic Definition
- **Name:** <precise technical name>
- **Description:** <what this quality means in context>
- **Stakeholders:** <who cares about this>

### 2. Indicators
| Indicator | What it shows | How to observe |
|-----------|--------------|----------------|
| ...       | ...          | ...            |

### 3. Metrics
| Metric | Unit | Collection method | Frequency |
|--------|------|-------------------|-----------|
| ...    | ...  | ...               | ...       |

### 4. Scoring
| Level | Threshold | Meaning |
|-------|-----------|---------|
| Green | ...       | Healthy |
| Yellow| ...       | Warning |
| Red   | ...       | Critical|

### 5. Decision Criteria
| Score | Action | Owner | Timeline |
|-------|--------|-------|----------|
| Green | Continue monitoring | ... | Ongoing |
| Yellow| Investigate and plan | ... | This sprint |
| Red   | Immediate action | ... | Now |

### Trust Assessment
- **Verified (Fact):** ...
- **Assumed (Guess):** ...
- **Unknown (Rumor):** ...
```

## Important

- All output in standard engineering language
- Be specific to the user's domain — don't give generic metrics
- Include trust levels for each metric (is this actually measurable?)
- Suggest starting with the simplest useful metric, not the most comprehensive
