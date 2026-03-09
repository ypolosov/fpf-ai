# Topic to FPF Sections Mapping

Maps common software engineering topics to relevant FPF-Spec.md sections.
Use this to determine which sections to load for a given analysis task.

## How to use

1. Identify the engineering topic from the user's question
2. Find the matching row(s) below
3. Load **primary sections** first (most relevant)
4. Load **secondary sections** if deeper analysis is needed
5. Look up exact line ranges in `fpf-index.md` by searching for section IDs (e.g., "A.1 -")

## Mapping Table

| Engineering Topic | Primary Sections (search fpf-index.md for these) | Secondary Sections |
|---|---|---|
| **Architecture & system design** | A.1 (Holonic Foundation), A.6 (Signature Stack & Boundary), C.13 (Mereology) | A.4 (Temporal Duality), A.5 (Kernel & Extension Layering) |
| **Service boundaries & decomposition** | A.1.1 (BoundedContext), A.1 (Holonic Foundation), A.6 (Boundary Discipline) | A.7 (Strict Distinction), F.5 (Naming Discipline) |
| **API design & interfaces** | A.6 (Signature Stack), A.6.C (Contract Unpacking), A.2.2 (Capability) | A.2.3 (PromiseContent), A.7 (Strict Distinction) |
| **Domain modeling (DDD)** | A.1.1 (BoundedContext), F.5 (Naming Discipline), C.3 (Kinds & Typed Reasoning) | A.1 (Holonic Foundation), A.2 (Role Taxonomy), F.17 (UTS) |
| **Code quality & reviews** | F.5 (Naming Discipline), A.6 (Boundary Discipline), A.7 (Strict Distinction) | B.3 (Trust Calculus), A.15 (Role-Method-Work) |
| **Team structure & responsibilities** | A.2 (Role Taxonomy), A.15 (Role-Method-Work), A.2.1 (RoleAssignment) | A.13 (Agential Role), B.4 (Evolution Loop) |
| **Trust & decision-making** | B.3 (Trust & Assurance F-G-R), B.5 (Reasoning Cycle), A.2.4 (EvidenceRole) | B.3.4 (Evidence Decay), B.5.2 (Abductive Loop) |
| **Technical debt & evolution** | B.4 (Evolution Loop), C.19 (Explore-Exploit Governor), A.4 (Temporal Duality) | B.2 (Meta-Holon Transition), B.3.4 (Evidence Decay) |
| **Testing strategy** | B.3 (Trust Calculus), A.2.4 (EvidenceRole), C.16 (Measurement & Metrics) | A.15 (Role-Method-Work), B.1 (Aggregation Algebra) |
| **Requirements & characteristics** | A.17 (Canonical Characteristic), A.18 (CSLC), A.19 (CharacteristicSpace) | C.16 (Measurement), C.25 (Q-Bundle: Quality Bundles) |
| **Terminology & naming** | F.5 (Naming Discipline), F.17 (Unified Term Sheet UTS), F.2 (Term Harvesting) | F.3 (Sense Clustering), F.13 (Lexical Continuity), E.10 (Lexical Rules) |
| **Deployment & operations** | A.4 (Temporal Duality), A.15 (Role-Method-Work), A.16 (Language-State Transduction) | B.4 (Evolution Loop), A.6 (Boundary Discipline) |
| **Innovation & experimentation** | C.19 (Explore-Exploit Governor), C.18 (Open-Ended Search NQD), C.17 (Creativity) | B.5.2 (Abductive Loop), C.19.1 (Bitter-Lesson Preference) |
| **Metrics & measurement** | C.16 (Measurement & Metrics), A.19 (CharacteristicSpace), A.19.USCM (Scoring) | A.19.UINDM (Indicatorization), A.19.CPM (Comparison) |
| **Risk assessment** | B.3 (Trust Calculus F-G-R), B.5 (Reasoning Cycle), B.3.4 (Evidence Decay) | A.2.4 (EvidenceRole), C.19 (Explore-Exploit) |
| **Integration & composition** | B.1 (Aggregation Algebra), C.13 (Mereology), A.6 (Boundary Discipline) | A.6.C (Contract Unpacking), A.1.1 (BoundedContext) |
| **Scaling & growth** | B.2 (Meta-Holon Transition), A.1 (Holonic Foundation), B.4 (Evolution Loop) | A.5 (Extension Layering), B.1 (Aggregation) |
| **Documentation** | F.5 (Naming Discipline), F.17 (UTS), E.17 (Multi-View Publication Kit) | E.8 (Authoring Conventions), F.7 (Concept-Set Table) |
| **Process design** | A.15 (Role-Method-Work), A.3 (Transformer Constitution), A.3.1 (Method) | B.4 (Evolution Loop), B.5 (Reasoning Cycle) |
| **Security boundaries** | A.1.1 (BoundedContext), B.3 (Trust Calculus), A.6 (Boundary Discipline) | A.2.8 (Commitment), A.6.9 (CrossContext Disambiguation) |
