# Prompt: Task 03 Part 2, Review Decision, Authorisation and Consolidated Operational Blueprint

Status: DRAFT for your review. Paste everything below the line into Claude Code, run from the repository root, only after Part 1 has been run and you have reviewed its outputs.

How it is built: Part A records your review decision on Part 1 and authorises Part 2. Part B is the execution protocol. Part 2 completes Task 03: state model, rules and decision model, requirements, operational controls, traceability matrix and the consolidated operational blueprint.

Before you paste it: the lines marked REVIEW in Part A depend on what Part 1 produced. Read the Part 1 completion record and the OPS files first, and edit every REVIEW line to match your actual decision. Do not paste it with those lines unedited.

Numbering note: the OPS numbers below are a proposal. OPS-002, OPS-003 and OPS-009 are taken by Part 1. If your reference material defines different numbers for Part 2, change them here before running it.

---

# TASK 03 PART 1 REVIEW DECISION AND AUTHORISATION

I have reviewed the Task 03 Part 1 execution report and completion record.

REVIEW: I APPROVE TASK 03 PART 1 AS THE WORKING OPERATIONAL PROCESS FOUNDATION for the Guided Payroll Activation project. (Edit if you accept it only with changes, and list the changes.)

This is not formal approval of the operational blueprint. All outstanding external decisions, assumptions and confirmations must remain visible and retain their current statuses.

## Approved working baseline

Accept the following as the initial inputs to Part 2:

- OPS-002: the operational process model (processes PRC-xx and their steps).
- OPS-003: the exception and human-review pathways (EXC-xx).
- OPS-009: the Task 03 register, as the tracker to be extended.

REVIEW: list any process or exception you do not accept, or accept only provisionally.

Continue to treat ARC-001, ARC-002 and ARC-006 as the working architecture baseline, and AIB-001 to AIB-012 as binding design constraints. AIB-005 and AIB-006 remain pending security confirmation.

## Provisional assumptions

Retain as provisional assumptions, not confirmed business decisions:

- Every process and exception is a proposal until validated with a real client.
- Ownership in ARC-004, and any role assigned in OPS-002 or OPS-003.
- Business rules BR-001 to BR-009 and any rule added in this task.
- ASM-001 to ASM-014 remain unvalidated.

Do not silently convert these assumptions into approved requirements.

## Decisions recorded in this review

REVIEW: record any open question from Part 1 that you have now decided, with the decision and who made it. If there is none, state that no open decision has been resolved.

The proposed baseline changes PCR-001 to PCR-013 and any added in Part 1 remain unapplied.

## Outstanding decisions

Keep unresolved, with their current statuses:

- DEC-001 statutory jurisdiction.
- DEC-005 KPI baselines, cohorts and measurement rules.
- DEC-006 blocking, review and informational issue policy.
- DEC-007 permissions and approvals for corrections, bulk fixes and activation.
- OQ-001 business sponsor and approval authority.
- OQ-002 applicable statutory and regulatory obligations.
- OQ-004 and OQ-005 volumes and current performance.
- All other open decisions and questions.

For DEC-006 and DEC-007, the decision model must present the options and show the decision as pending. Do not choose a policy, an approval authority or an escalation destination, and do not set numeric thresholds.

## Validation tooling authorisation

The same authorisation as in Part 1 applies: npx js-yaml and npx -p @mermaid-js/mermaid-cli mmdc may be used. If blocked, report the limitation and do not work around it. Install nothing else and add nothing to the repository.

## AUTHORISATION

I explicitly authorise Claude Code to begin:

TASK 03, PART 2: REQUIREMENTS, RULES, DECISION MODEL AND CONSOLIDATED OPERATIONAL BLUEPRINT.

Use the approved Part 1 working baseline as the source of truth.

Part 2 must:

1. Define the batch and record lifecycle (state model).
2. Define the business rules and decision model, with decision rights shown as resolved or unresolved.
3. Write testable business-level requirements traced to stories, capabilities, objectives and KPIs.
4. Define operational controls.
5. Build the traceability matrix across the whole chain.
6. Consolidate the operational blueprint.
7. Extend OPS-009 with actual status and validation results.
8. Validate all structured outputs and report open assumptions and decisions.
9. Create a Part 2 completion and validation report, then stop.

Maintain the distinction between business requirements, operational processes and technical implementation.

Do not start Task 04.

Do not modify Task 01, Task 02 or Part 1 artifacts, the baseline files, or the roadmap without recording a proposed change and its rationale.

Do not commit or push. I will review and commit.

At the end, stop and present the Part 2 deliverables for human review and approval.

Final instruction: Proceed with Task 03 Part 2 under these conditions.

---

# PART B: TASK 03 PART 2 EXECUTION PROTOCOL

## 1. Your role

Act as a Senior Business Analyst, Payroll Domain Analyst and Decision Modelling specialist. Do the work, create the artifacts, validate them, and report the results.

## 2. Preconditions and sources

Read CLAUDE.md and README.md first and follow them. Confirm the repository, branch and git status. Confirm these exist: OPS-002, OPS-003, OPS-009, validation/task-03-part-1-completion-record.md, and the Task 01 and Task 02 artifacts. If any is missing, STOP and say so.

Also read product-backlog.md and the six epic files (acceptance criteria and measures), ARC-006 (business rules BR-001 to BR-009 and decision points), BIZ-004 (KPIs), BIZ-005 (decisions and risks) and BIZ-007 (AI opportunities and boundary rules).

## 3. Principles

1. Do not name technologies, databases, APIs, frameworks, vendors or infrastructure. Requirements are business-level and testable, not designs.
2. Do not invent policies, thresholds, volumes, service levels, regulatory obligations or approval authority. Where a number is needed and no source gives it, record a requirement without the number and an open question.
3. Every requirement traces to a story, a capability, an objective and, where relevant, a KPI.
4. Apply AIB-001 to AIB-012. AI never approves, activates or decides validity.
5. A failing record never blocks the batch, and corrected records are revalidated on their own.
6. Keep confirmed facts, assumptions, proposals and open questions distinct.

## 4. Stage 1: batch and record lifecycle, OPS-006

Create docs/operations/OPS-006-batch-and-record-state-model.yaml. Define the states of a batch and of an individual record, the allowed transitions, what triggers each, which process step causes it, and who or what may cause it (deterministic, AI-supported, human). Show how one failing record is isolated, how interrupted processing is retried without duplication, and how corrected records re-enter validation alone. State which transitions are reserved to an authorised human. Use local state identifiers. Include a state diagram in docs/diagrams/.

## 5. Stage 2: business rules and decision model, OPS-005

Create docs/operations/OPS-005-business-rules-and-decision-model.yaml. Elaborate BR-001 to BR-009 and the ARC-006 decision points into decision tables. At minimum cover: whether a record is eligible for activation; the severity class of a finding (blocking, review or informational); whether a mapping suggestion may be proposed automatically or needs review; and when a batch may start activation. For each decision record: inputs, rules or options, outcomes, the decision owner (or unresolved), whether it is deterministic, AI-assisted or human, and the related open decision. Where DEC-006 or DEC-007 governs, give the options and mark the decision pending.

## 6. Stage 3: requirements, OPS-004

Create docs/operations/OPS-004-requirements-catalogue.yaml. Write functional (REQ-F-001 and onward) and non-functional (REQ-NF-001 and onward) business requirements for the P0 stories and for the capabilities in scope. Cover, where sources support them: record-level error reporting with row and column location and a suggested correction; isolation of failing records; progress visibility; safe retry; remediation and bulk fixes; revalidation of corrected records; audit and history; role-based visibility; protection of sensitive data; and measurement against the target metrics. Each requirement is a testable statement with a rationale, priority from the backlog, source story, capability, objective, KPI, owning role (proposed), and verification approach. Mark scale, performance and retention needs as assumptions with open questions unless a source gives a value.

## 7. Stage 4: operational controls, OPS-007

Create docs/operations/OPS-007-operational-controls.yaml. Define business controls that keep the operation safe and auditable: validation before activation, segregation of duties where decision rights allow, human approval points, audit trail, change records for corrections and bulk fixes, protection of sensitive data, handling of AI suggestions, and monitoring of the target metrics. Link each control to the risks in BIZ-005, the rules and the requirements. Do not invent approval authority.

## 8. Stage 5: traceability matrix, OPS-008

Create docs/operations/OPS-008-operational-traceability-matrix.yaml. Trace the full chain in both directions: bottleneck, problem, objective, KPI, capability, value stream stage, process, step, exception, rule or decision, requirement, control, story and role. List any item with a missing link as a gap.

## 9. Stage 6: consolidated operational blueprint, OPS-001

Create docs/operations/OPS-001-operational-blueprint.md consolidating the operational model for a reader: purpose, how the work flows (with diagrams), processes, exceptions and human review, state model, rules and decisions, requirements summary, controls, open decisions and assumptions. Compare it with the Task 02 blueprint and record proposed changes without editing earlier files.

## 10. Register and validation

Extend OPS-009 with the Part 2 deliverables, status, sources, assumptions, open questions, proposed changes and validation results. Validate: YAML syntax; identifier consistency; two-way traceability; no requirement without a source; no invented number, policy, authority or technology; AI boundary rules wherever AI appears; no earlier file modified. Do not claim a check passed unless you ran it. Report every limitation.

## 11. Required artifacts

- docs/operations/OPS-001-operational-blueprint.md
- docs/operations/OPS-004-requirements-catalogue.yaml
- docs/operations/OPS-005-business-rules-and-decision-model.yaml
- docs/operations/OPS-006-batch-and-record-state-model.yaml
- docs/operations/OPS-007-operational-controls.yaml
- docs/operations/OPS-008-operational-traceability-matrix.yaml
- docs/operations/OPS-009-task-03-register.yaml (extended)
- docs/diagrams/ (state model and overview diagrams, one .mmd each)
- validation/task-03-part-2-validation-report.md
- validation/task-03-part-2-completion-record.md

Mark every artifact DRAFT. Use only: DRAFT, UNDER_REVIEW, VALIDATED, APPROVED, PENDING_EXTERNAL_CONFIRMATION.

## 12. Final report

Present: the source inventory; the state model summary; the decision model summary with pending decisions; the requirements summary by priority; the controls summary; traceability results and gaps; open assumptions and decisions with who must confirm them; files created and their status; validation results and limitations; issues requiring human review; and readiness for Task 04.

## 13. Strict boundaries

Do not: modify earlier-task or baseline files; change the roadmap; start Task 04 or any implementation; select technologies; invent regulatory obligations, policies, thresholds, volumes or approval authority; resolve decisions without evidence and human confirmation; commit or push.

Complete the task, present the artifacts and validation evidence, and STOP. Wait for explicit human approval before Task 04.
