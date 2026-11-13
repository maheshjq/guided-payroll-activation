# Prompt: Task 02, Business Architecture and Capability Modelling

Status: DRAFT for your review. Paste everything below the line into Claude Code, run from the repository root, only after you have reviewed and accepted the Task 01 outputs.

Purpose: structure what the business must be able to do to deliver guided activation. This is business architecture, not software design.

---

# CLAUDE CODE EXECUTION PROMPT
# TASK 02 (GUIDED PAYROLL ACTIVATION): BUSINESS ARCHITECTURE AND CAPABILITY MODELLING

## 1. Your role

Act as a Senior Enterprise Business Architect and Payroll Domain Analyst. Do the work, create the artifacts, validate them, and report the results.

## 2. Preconditions

Before doing anything, confirm that these Task 01 files exist in docs/business/: BIZ-001 to BIZ-007, and validation/task-01-completion-record.md. If any is missing, STOP and say so. Treat the following as the approved working baseline, provided I accept them in this session or the completion record shows my acceptance: BIZ-001 (problem), BIZ-006 (AI opportunity assessment and boundary rules AIB-001 and onward, binding), BIZ-007 (scope and boundaries). If acceptance is not clear, ask me before proceeding.

Also read CLAUDE.md, README.md, Problem statement.md, the Business Model Canvas to Business Architecture Blueprint.md, product-backlog.md, and the epic files. The existing blueprint's capabilities and value stream are a starting point to be structured, not overwritten.

Do not change approved Task 01 artifacts. If a change seems needed, record a proposed change and its rationale. Do not invent answers to open decisions; keep them visible with their current status.

## 3. Keep these concepts separate

- Business capability: what the organization must be able to do, regardless of how.
- Operational process: how work flows (belongs mainly to Task 03).
- Solution capability: a function of the proposed application.
- Technical component: an implementation element (out of scope here).

Do not mix them. Example: Pay Code Mapping is a business capability; AI-suggested mapping is a solution capability; a model call is a technical component.

## 4. Execution protocol

Stage 1, workspace verification: confirm repository, branch, and baseline files. Report anything unexpected.

Stage 2, capability map: build a hierarchical map with Level 1, Level 2, and useful Level 3 capabilities (CAP-001 and onward), starting from the capabilities in the existing blueprint and the six epics. Give each capability a definition, a purpose, and a maturity or criticality note only if source documents support it.

Stage 3, value stream: define the guided activation value stream end to end, from batch initiation to reviewed results, with stages, entry and exit criteria, the value created at each stage, and the stakeholders involved. Include the exception path and the return of corrected records. Produce Mermaid diagrams.

Stage 4, mappings: map capabilities to Task 01 problems (BN, BP), objectives (BO), KPIs, and epics (EPIC-01 to EPIC-06) and stories (PA-xx). Map stakeholders (STK) to capabilities.

Stage 5, ownership and accountability: for each capability, define an owning role, accountable role, and consulted roles, using role names from Task 01 only. Mark any assignment you propose as an assumption.

Stage 6, relationships and dependencies: record how capabilities depend on each other, and which are shared across epics. Produce a dependency diagram.

Stage 7, blueprint: consolidate into a business architecture blueprint that links intent, value stream, capabilities, stakeholders, rules and decision points, information handled, governance, and the AI boundary rules. Compare it with the existing blueprint file and list proposed changes separately; do not edit the existing file.

Stage 8, traceability: ensure every capability supports at least one objective, every objective is supported by at least one capability, every epic maps to capabilities, and nothing in the capability map lacks a source.

## 5. Required artifacts

- docs/architecture/ARC-001-capability-map.yaml
- docs/architecture/ARC-002-value-stream.md
- docs/architecture/ARC-003-traceability-matrix.yaml
- docs/architecture/ARC-004-capability-ownership.yaml
- docs/architecture/ARC-005-capability-dependencies.yaml
- docs/architecture/ARC-006-business-architecture-blueprint.md
- docs/architecture/ARC-007-proposed-changes-to-baseline.yaml
- docs/diagrams/ (one .mmd per diagram)
- validation/task-02-validation-report.md
- validation/task-02-completion-record.md

## 6. Validation

Parse all YAML with local tools. Check Mermaid structure; if no renderer is available, say so and ask before installing anything. Check ID consistency, two-way trace links, and that no capability, relationship, or owner is unsupported. Scan for unsupported legal or regulatory claims. Confirm AI boundary rules appear wherever AI is mentioned. Do not claim a check passed unless you ran it.

## 7. Status and approval gate

Mark every artifact DRAFT, using only: DRAFT, UNDER_REVIEW, VALIDATED, APPROVED, PENDING_EXTERNAL_CONFIRMATION. Do not fabricate approval. List unresolved assumptions and decisions that carry over.

## 8. Acceptance criteria and final report

Ready for review when: the capability map is hierarchical and sourced; the value stream is defined; capabilities map to objectives, problems, epics, and stakeholders; ownership and dependencies are documented; the blueprint is consolidated; proposed changes to the baseline are listed; validation is done or limitations reported; readiness for Task 03 is assessed.

End with a concise report: precondition check, files created (paths), analysis, validation results, traceability assessment, open items, limitations, acceptance status, and a readiness recommendation for Task 03 (operational blueprint and decision model).

## 9. Boundaries

Execute Task 02 only. Do not start Task 03. Do not write application code, schemas, or APIs, and do not design technical architecture. Do not modify the baseline or approved Task 01 files. Do not push or open a pull request unless asked.

Complete the task, present the artifacts and validation evidence, and STOP. Wait for explicit human approval before Task 03.
