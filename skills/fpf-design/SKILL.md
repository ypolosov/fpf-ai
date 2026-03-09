---
name: fpf-design
description: "Architecture design using first principles. Use when the user wants to design a new system, plan decomposition, define service boundaries, or establish interface contracts. Accepts a system description or requirements as argument."
user_invocable: true
---

# FPF Design

Design software architecture using first-principles decomposition.

## Usage

```
/fpf-design <system description or requirements>
```

## What this skill does

Produces an architecture design covering:
1. **System boundaries** — where the system starts and ends
2. **Component decomposition** — hierarchical breakdown into parts
3. **Interface contracts** — what each component exposes
4. **Composition rules** — how parts connect and what constraints apply
5. **Domain contexts** — which components own which domain concepts
6. **Evolution strategy** — what changes first, what stays stable

## Instructions

When this skill is invoked:

1. Take the user's description from `$ARGUMENTS`

2. Delegate to the **fpf-analyst** agent with this task:
   > Design the architecture for the following system using first-principles decomposition.
   > Focus on boundaries, composition rules, and interface contracts.
   > Load FPF sections on: systems thinking, mereology, holons, bounded contexts, affordances, evolution.
   > System description: {$ARGUMENTS}

3. The agent will load relevant FPF sections and produce a design.

4. Output format:
   - **System Scope** — what's in and out of scope
   - **Component Hierarchy** — tree or table of components
   - **Boundary Definitions** — for each component: what's inside, what's exposed
   - **Interface Contracts** — key APIs/events between components
   - **Composition Constraints** — rules for how parts connect
   - **Domain Ownership** — which component owns which concepts
   - **Evolution Notes** — what's stable vs what will change

## Important

- All output in standard engineering language
- Prefer diagrams in ASCII or Mermaid when helpful
- Be specific about boundaries — vague boundaries are the #1 architecture problem
- If FPF-Spec.md is not found, suggest running `/fpf-setup`
