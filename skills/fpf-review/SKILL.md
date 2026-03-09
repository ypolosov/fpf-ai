---
name: fpf-review
description: "Code or architecture review using first-principles checklist. Use when the user wants to review code quality, architectural decisions, boundary discipline, or composition correctness. Can target specific files or the overall architecture."
user_invocable: true
---

# FPF Review

Review code or architecture against first-principles engineering checklist.

## Usage

```
/fpf-review [file paths or architecture description]
```

## What this skill does

Reviews against six quality dimensions:

1. **Boundary discipline** — Are component boundaries clean? Do they leak internals?
2. **Naming quality** — Are terms precise, consistent, and unambiguous?
3. **Composition correctness** — Do parts compose properly? Are interfaces compatible?
4. **Trust calibration** — Are assumptions explicit? Are critical paths verified?
5. **Responsibility separation** — Is each component responsible for one clear thing?
6. **Evolution readiness** — Can the system change without cascading breakage?

## Instructions

When this skill is invoked:

1. Take the target from `$ARGUMENTS` — can be file paths, directory, or architecture description

2. If file paths are given, read the code first

3. Delegate to the **fpf-analyst** agent with this task:
   > Review the following code/architecture using the first-principles review checklist.
   > Load FPF sections on: naming discipline, composition rules, interfaces, trust calculus, evolution.
   > Target: {$ARGUMENTS}
   > [Include code content if files were read]

4. Output format — for each dimension, provide:
   - **Status**: Pass / Warning / Fail
   - **Finding**: What was observed
   - **Recommendation**: What to improve (if not Pass)

5. End with:
   - **Summary score** (e.g., 4/6 dimensions pass)
   - **Top 3 priorities** for improvement

## Review Checklist Detail

### Boundary Discipline
- [ ] Components have explicit boundaries (modules, packages, services)
- [ ] Internal details are not leaked through interfaces
- [ ] Dependencies flow in one direction
- [ ] Cross-boundary communication uses explicit contracts

### Naming Quality
- [ ] Terms are precise and unambiguous
- [ ] Same concept has the same name everywhere
- [ ] Different concepts have different names
- [ ] No misleading abbreviations or overloaded terms

### Composition Correctness
- [ ] Interfaces are compatible at connection points
- [ ] Data transformations at boundaries are explicit
- [ ] Error handling respects component boundaries
- [ ] Composition can be tested independently

### Trust Calibration
- [ ] Assumptions are documented or explicit in code
- [ ] Critical paths are tested (not just assumed to work)
- [ ] External inputs are validated at system boundaries
- [ ] Uncertainty is handled proportionally to risk

### Responsibility Separation
- [ ] Each component has a single clear responsibility
- [ ] Responsibilities don't overlap between components
- [ ] Changes to one responsibility don't cascade
- [ ] Roles and processes are documented

### Evolution Readiness
- [ ] Stable parts are separated from changing parts
- [ ] Interfaces allow extension without modification
- [ ] Configuration is separated from logic
- [ ] Migration paths exist for schema/API changes

## Important

- All output in standard engineering language
- Be specific — point to exact lines/files when reviewing code
- Prioritize actionable findings over theoretical concerns
- If FPF-Spec.md is not found, still perform review using quick-reference principles
