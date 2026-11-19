# Business Artifacts: Task 01

Status: DRAFT. Produced by Task 01 (Business Problem, Intent and Value Model). Nothing in this folder is approved.

This folder formalizes the existing prose baseline into structured, ID-based, traceable business artifacts. It does not replace the baseline. Where an artifact and a baseline document disagree, the baseline wins and the disagreement is recorded in `validation/task-01-completion-record.md`.

## Source baseline, in order of authority

1. `Problem statement.md`, the verified source. Never changed by this task.
2. `Business Model Canvas to Business Architecture Blueprint.md`.
3. `product-backlog.md` and the six epic files `epic-01` to `epic-06`.
4. `requirements-document-map.md`.
5. `tech-stack.md` and `docs/solution-architecture.svg`, used as context only. No architecture is designed in Task 01.

## Artifact index

| Artifact | File | Format | Defines |
| :-- | :-- | :-- | :-- |
| BIZ-001 | BIZ-001-business-context-and-problem-statement.md | Markdown | BN, BP, HYP |
| BIZ-002 | BIZ-002-business-case-and-value-model.md | Markdown | OPT, BEN |
| BIZ-003 | BIZ-003-stakeholder-register.yaml | YAML | STK |
| BIZ-004 | BIZ-004-business-objectives-and-kpi-catalogue.yaml | YAML | BO, KPI |
| BIZ-005 | BIZ-005-assumptions-constraints-and-risks.yaml | YAML | ASM, CON, RSK, DEP, DEC, OQ |
| BIZ-006 | BIZ-006-activation-journey.md | Markdown with Mermaid | JS |
| BIZ-007 | BIZ-007-ai-opportunity-assessment.yaml | YAML | AI, AIB |
| BIZ-008 | BIZ-008-scope-and-boundaries.yaml | YAML | CAP, IS, OOS |

Diagrams are in `docs/diagrams/`. Validation evidence and the execution record are in `validation/`.

## Status model

| Status | Meaning |
| :-- | :-- |
| DRAFT | Generated or edited, not yet reviewed. Every Task 01 artifact starts here. |
| UNDER_REVIEW | Submitted to a named reviewer. |
| VALIDATED | Checked for internal consistency and traceability. Not a business approval. |
| APPROVED | Accepted by the accountable business owner. Only a person can set this. |
| PENDING_EXTERNAL_CONFIRMATION | Depends on confirmation from payroll-domain, compliance, security or business owners outside the product team. |

## ID conventions

IDs are stable, zero-padded and sequential. An ID is never reused. A retired ID keeps its entry with `status: deprecated`. Each ID is defined in exactly one artifact, shown below, and only referenced elsewhere.

| Prefix | Meaning | Defined in | Range in Task 01 |
| :-- | :-- | :-- | :-- |
| BN | Bottleneck from the problem statement | BIZ-001 | BN-01 to BN-05 |
| BP | Business problem, one per impact dimension | BIZ-001 | BP-001 to BP-005 |
| HYP | Root-cause hypothesis | BIZ-001 | HYP-001 to HYP-007 |
| OPT | Business case option | BIZ-002 | OPT-0 to OPT-2 |
| BEN | Expected benefit | BIZ-002 | BEN-001 to BEN-008 |
| STK | Stakeholder | BIZ-003 | STK-001 to STK-013 |
| BO | Business objective | BIZ-004 | BO-001 to BO-008 |
| KPI | Performance indicator | BIZ-004 | KPI-001 to KPI-022 |
| ASM | Assumption | BIZ-005 | ASM-001 to ASM-014 |
| CON | Constraint | BIZ-005 | CON-001 to CON-008 |
| RSK | Risk | BIZ-005 | RSK-001 to RSK-013 |
| DEP | Dependency | BIZ-005 | DEP-001 to DEP-009 |
| DEC | Open decision | BIZ-005 | DEC-001 to DEC-023 |
| OQ | Open question | BIZ-005 | OQ-001 to OQ-012 |
| JS | Journey stage | BIZ-006 | JS-01 to JS-13 |
| AI | AI opportunity, including rejected uses | BIZ-007 | AI-001 to AI-009 |
| AIB | AI boundary rule | BIZ-007 | AIB-001 to AIB-012 |
| CAP | Business capability, provisional reference only | BIZ-008 | CAP-001 to CAP-007 |
| IS | In-scope item | BIZ-008 | IS-001 to IS-011 |
| OOS | Out-of-scope item | BIZ-008 | OOS-001 to OOS-018 |

Existing baseline identifiers are referenced, not redefined: EPIC-01 to EPIC-06 for the six epic files in journey order, and PA-01 to PA-16 for the stories in `product-backlog.md`.

CAP-001 to CAP-007 are assigned in the reading order of the seven capabilities in the blueprint, section 3. They exist for traceability only. The capability model itself belongs to Task 02.

## Traceability chain

Bottleneck (BN) → Business problem (BP) → Business objective (BO) → KPI → Capability (CAP) → Journey stage (JS) → Epic and story (EPIC, PA) → AI opportunity (AI) under boundary rules (AIB) → Benefit (BEN) → Business value.

Assumptions (ASM), constraints (CON), risks (RSK), dependencies (DEP), decisions (DEC) and questions (OQ) attach to any link in the chain.

## Rules for editing these artifacts

- Do not change a baseline document to make it agree with an artifact. Record the proposed change instead.
- Do not raise an artifact's status above DRAFT without a named human reviewer.
- Do not add a baseline, target, jurisdiction, regulation, client name or monetary figure that no baseline document states.
