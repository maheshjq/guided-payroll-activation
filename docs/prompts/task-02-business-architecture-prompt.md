# Prompt: Task 02, Review Decision, Authorisation and Business Architecture Modelling

Status: DRAFT for your review. Paste everything below the line into Claude Code, run from the repository root.

How it is built: Part A records your review decision on Task 01 and authorises Task 02, in the same structure as a formal approval record. Part B is the execution protocol.

Before you paste it: Part A states that you reviewed the Task 01 outputs and makes decisions in your name. Read at least BIZ-001, BIZ-007, BIZ-008 and validation/task-01-completion-record.md first, and edit any line you do not agree with. The recommended answers already built in are: the technology stack is a proposal (DEC-022); the three scope items that came only from the Task 01 prompt stay provisional; the five proposed baseline changes (PCR-001 to PCR-005) stay unapplied; and package-based validation tools may be used.

---

# TASK 01 REVIEW DECISION AND AUTHORISATION

I have reviewed the Task 01 execution report and completion record.

I APPROVE TASK 01 AS THE WORKING BUSINESS FOUNDATION for the Guided Payroll Activation project.

This is not formal approval of the final business case. All outstanding external decisions, assumptions and confirmations must remain visible and retain their current statuses.

## Approved working baseline

Accept the following artifacts as the initial inputs to Task 02:

- BIZ-001: Business Context and Problem Statement.
- BIZ-007: AI Opportunity Assessment.
- BIZ-008: Scope and Boundaries.

Accept AIB-001 to AIB-012 as binding design constraints for subsequent business and solution modelling. AIB-005 and AIB-006 (data protection and masking) remain pending security confirmation and must be shown with that status.

Use BIZ-002 to BIZ-006 (business case, stakeholder register, objectives and KPIs, registers, activation journey) as supporting inputs in their current DRAFT status. They are not approved baselines.

## Provisional assumptions

Retain the following as provisional assumptions, not confirmed business decisions:

- Enterprise clients activating hundreds or thousands of employee profiles as the initial segment. Whether this includes existing customers undergoing restructuring remains open (DEC-002).
- Delivery surface and integrations remain subject to selection (DEC-003, DEC-004).
- The four stakeholder roles marked as assumptions in BIZ-003 (STK-010 to STK-013).
- CAP-001 to CAP-007 as starting references only, not an approved capability model.
- The current-state journey remains illustrative until validated with a real client.
- The industry classification (ASM-012) and the three scope items that came only from the Task 01 prompt (IS-011, OOS-003, OOS-006) remain provisional.
- None of ASM-001 to ASM-014 has been validated.

Do not silently convert these assumptions into approved business requirements.

## Decisions recorded in this review

- DEC-022 is decided: the proposed technology stack in tech-stack.md is a proposal, not a constraint. Task 02 must not treat it as a constraint and must not design technical architecture. Record this decision as a proposed status update to BIZ-005; do not edit BIZ-005 directly.
- The proposed baseline changes PCR-001 to PCR-005 remain unapplied. Carry them forward, and add any new proposed changes that Task 02 identifies, in the proposed-changes artifact. Do not apply any change to a baseline file.

## Outstanding decisions

Keep the following unresolved, with their current statuses:

- DEC-001 statutory jurisdiction.
- DEC-002 customer segment.
- DEC-005 KPI baselines, cohorts and measurement rules.
- DEC-006 blocking, review and informational issue policy.
- DEC-007 permissions and approvals for corrections, bulk fixes and activation.
- OQ-001 business sponsor and approval authority.
- OQ-002 applicable statutory and regulatory obligations.
- OQ-006 financial parameters.
- All other open decisions and questions in BIZ-005.

Do not invent answers to these questions.

## Validation tooling authorisation

You may run npx js-yaml to validate YAML, and npx -p @mermaid-js/mermaid-cli mmdc to render Mermaid diagrams, for the Task 02 files and, read-only, for the Task 01 files and diagrams. Report the results in the Task 02 validation report. Do not fix Task 01 files; record any defect as a proposed change. Do not install anything else, do not add dependencies or build files to the repository, and keep rendered images and helper scripts in the session scratchpad unless I ask otherwise. If the network or tools are unavailable, report the limitation.

## AUTHORISATION

I explicitly authorise Claude Code to begin:

TASK 02: BUSINESS ARCHITECTURE AND CAPABILITY MODELLING.

Use the approved Task 01 working baseline as the source of truth.

Task 02 must:

1. Identify and structure the business capabilities required for the bulk guided activation domain.
2. Develop a hierarchical business capability map.
3. Define the guided activation value stream.
4. Map capabilities to Task 01 business objectives, problems and bottlenecks.
5. Identify stakeholders, capability ownership and accountability.
6. Identify capability relationships and dependencies.
7. Develop the business architecture blueprint.
8. Maintain traceability to Task 01 artifacts, epics and stories.
9. Validate all structured outputs and report unresolved assumptions.
10. Create a Task 02 completion and validation report.

Maintain the distinction between business capabilities, operational processes, solution capabilities and technical implementation components.

Do not start Task 03.

Do not modify the baseline files, and do not change approved Task 01 artifacts without recording a proposed change and its rationale.

At the end, stop and present the Task 02 deliverables for human review and approval.

Final instruction: Proceed with Task 02 under these conditions.

---

# PART B: TASK 02 EXECUTION PROTOCOL

## 1. Your role

Act as a Senior Enterprise Business Architect and Payroll Domain Analyst. Do the work, create the artifacts, validate them, and report the results. Do not only describe what should be done.

## 2. Preconditions and sources

Read CLAUDE.md and README.md first and follow them. Confirm that these files exist: docs/business/BIZ-001 to BIZ-008, docs/diagrams/ (the two journey diagrams), validation/task-01-completion-record.md and validation/task-01-validation-report.md. If any is missing, STOP and say so.

Also read Problem statement.md, Business Model Canvas to Business Architecture Blueprint.md, product-backlog.md and the six epic files. The existing blueprint's capabilities and value stream are a starting point to be structured, not overwritten.

Confirm the repository, branch and git status before starting. Do not create a new repository or branch.

## 3. Keep these concepts separate

- Business capability: what the organization must be able to do, regardless of how.
- Operational process: how work flows (belongs mainly to the next task).
- Solution capability: a function of the proposed application.
- Technical component: an implementation element (out of scope here).

Do not mix them. Example: pay code mapping is a business capability; AI-suggested mapping is a solution capability; a model call is a technical component.

## 4. Execution stages

Stage 1, workspace verification: confirm repository, branch, baseline files and that nothing will be modified. Create an execution record.

Stage 2, capability map: build a hierarchical map with Level 1, Level 2 and useful Level 3 capabilities (CAP-001 and onward), starting from CAP-001 to CAP-007, the existing blueprint and the six epics. Give each capability a definition and purpose. Add criticality or maturity notes only where source documents support them.

Stage 3, value stream: define the guided activation value stream from batch initiation to reviewed results and hand-off, with stages, entry and exit criteria, value created at each stage, and the stakeholders involved. Include the exception path and the return of corrected records. Produce Mermaid diagrams.

Stage 4, mappings: map capabilities to Task 01 bottlenecks (BN), problems (BP), objectives (BO), KPIs, epics (EPIC-01 to EPIC-06) and stories (PA-xx). Map stakeholders (STK) to capabilities.

Stage 5, ownership and accountability: for each capability define an owning role, an accountable role and consulted roles, using role names from BIZ-003 only. Mark any assignment you propose as an assumption.

Stage 6, relationships and dependencies: record how capabilities depend on each other and which are shared across epics. Produce a dependency diagram.

Stage 7, blueprint: consolidate intent, value stream, capabilities, stakeholders, rules and decision points, information handled, governance and the AI boundary rules into a business architecture blueprint. Compare it with the existing blueprint file and list proposed changes separately; do not edit the existing file.

Stage 8, traceability: ensure every capability supports at least one objective, every objective is supported by at least one capability, every epic maps to capabilities, and no capability lacks a source.

## 5. Required artifacts

- docs/architecture/ARC-001-capability-map.yaml
- docs/architecture/ARC-002-value-stream.md
- docs/architecture/ARC-003-traceability-matrix.yaml
- docs/architecture/ARC-004-capability-ownership.yaml
- docs/architecture/ARC-005-capability-dependencies.yaml
- docs/architecture/ARC-006-business-architecture-blueprint.md
- docs/architecture/ARC-007-proposed-changes-to-baseline.yaml (carry forward PCR-001 to PCR-005 and the DEC-022 status update)
- docs/diagrams/ (one .mmd file per diagram)
- validation/task-02-validation-report.md
- validation/task-02-completion-record.md

Use Markdown for readable documents, YAML for structured models and Mermaid for diagrams. Use stable, consistent IDs and cross-references.

## 6. Validation

Validate YAML and render Mermaid diagrams using the tooling authorised in Part A. Check ID consistency, two-way trace links, and that no capability, relationship or owner is unsupported. Scan for unsupported legal or regulatory claims. Confirm the AI boundary rules appear wherever AI is mentioned. Confirm no baseline or approved Task 01 file was modified. Do not claim a check passed unless you ran it, and report every limitation.

## 7. Status and approval gate

Mark every artifact DRAFT, using only: DRAFT, UNDER_REVIEW, VALIDATED, APPROVED, PENDING_EXTERNAL_CONFIRMATION. Do not fabricate approval. List the unresolved assumptions and decisions that carry over, and who must confirm each.

## 8. Acceptance criteria and final report

Ready for review when: the capability map is hierarchical and sourced; the value stream is defined; capabilities map to objectives, problems, epics and stakeholders; ownership and dependencies are documented; the blueprint is consolidated; proposed changes to the baseline are listed; validation is done or limitations reported; readiness for the next task (operational blueprint, requirements and decision modelling) is assessed.

End with a concise report: precondition check, files created (paths), analysis completed, validation results, traceability assessment, open items, limitations, acceptance status, and a readiness recommendation for the next task. Provide actual file paths.

## 9. Boundaries

Execute Task 02 only. Do not start the next task. Do not write application code, schemas or APIs, and do not design technical architecture. Do not modify the baseline files or approved Task 01 artifacts. Do not push or open a pull request unless asked. If a critical decision cannot be made safely, record it as an open decision.

Complete the task, present the artifacts and validation evidence, and STOP. Wait for explicit human approval before the next task.
