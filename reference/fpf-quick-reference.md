# FPF Quick Reference — Engineering Language

This file provides the 10 key FPF concepts translated into standard engineering language.
Use this as a translation layer when working with FPF-Spec.md sections.

---

## 1. Holonic Decomposition → Component Hierarchy with Boundaries

Every system is composed of parts, and each part is itself a system with its own boundary.
A component at any level has:
- A clear **boundary** separating inside from outside
- **Interfaces** defining how it interacts with neighbors
- **Internal structure** invisible to the outside (encapsulation)

Engineering parallel: microservices, bounded contexts in DDD, module decomposition.

## 2. Bounded Context → Service/Module Domain Boundary

Each part of the system owns a specific domain of meaning. The same word can mean different things in different contexts. Boundaries must be explicit and enforced.

Engineering parallel: DDD bounded contexts, API contracts between services, schema ownership.

## 3. F-G-R Trust Calculus → Confidence Levels (Fact / Guess / Rumor)

Every piece of information has a trust level:
- **Fact (F)** — verified, tested, documented with evidence
- **Guess (G)** — reasonable assumption based on experience, not yet verified
- **Rumor (R)** — hearsay, unverified claim, someone's opinion without evidence

Decisions should be calibrated to trust levels. Don't build critical paths on rumors.

Engineering parallel: test coverage (fact), design assumptions (guess), "I heard that..." (rumor).

## 4. Role-Method-Work → Responsibility-Process-Deliverable

Every actor in the system has:
- **Role** — what they are responsible for (who)
- **Method** — how they perform that responsibility (how)
- **Work product** — what they deliver (what)

Engineering parallel: RACI matrices, job descriptions, CI/CD pipeline stages.

## 5. Mereology → Part-Whole Composition Rules

Rules governing how parts compose into wholes:
- Parts must be **compatible** at interfaces
- Composition must be **valid** (not just any parts can connect)
- The whole has **emergent properties** not present in individual parts

Engineering parallel: API compatibility, type system composition, integration testing.

## 6. Affordance → Interface Capability / Contract

What a component offers to its environment — the actions it enables. An affordance is defined by the component but realized by the user of that component.

Engineering parallel: API endpoints, SDK methods, CLI commands, event bus topics.

## 7. Alpha → Key Work Product / Artifact

A tracked artifact whose state matters for decision-making. Has a defined lifecycle with states and transition criteria.

Engineering parallel: PR status, deployment artifacts, design documents, test results.

## 8. Operational Space vs Creation Chain → Runtime vs Build Pipeline

Two fundamentally different contexts:
- **Operational space** — where the system runs and serves users
- **Creation chain** — where the system is designed, built, tested, and deployed

Engineering parallel: production environment vs CI/CD pipeline, runtime vs build time.

## 9. Naming Discipline → Terminology Precision

Every term in the system should have:
- A **technical name** (precise, unambiguous)
- A **common name** (for everyday communication)
- A **context** (where this term applies)
- **Dangerous aliases** (terms that look similar but mean different things)

Engineering parallel: ubiquitous language (DDD), glossary, API naming conventions.

## 10. Evolution Cycles → Explore/Exploit Balance

Systems evolve through cycles:
- **Explore** — try new approaches, prototype, experiment
- **Exploit** — optimize what works, standardize, scale

Healthy evolution balances both. Too much exploit = stagnation. Too much explore = chaos.

Engineering parallel: tech spikes vs production features, innovation time vs tech debt paydown.
