# Prompt: Task 03 Part 1, Review Decision, Authorisation and Operational Process Foundation

Status: DRAFT for your review. Paste everything below the line into Claude Code, run from the repository root.

How it is built: Part A records your review decision on Task 02 and authorises Task 03 Part 1. Part B is the execution protocol. Part 1 produces the process model and the exception and human-review pathways. Part 2 (a separate prompt) produces the state model, rules and decision model, requirements, controls, traceability matrix and consolidated operational blueprint.

Before you paste it: Part A states that you reviewed the Task 02 outputs and makes decisions in your name. Read at least ARC-001, ARC-002, ARC-006 and validation/task-02-completion-record.md first, and edit any line you do not agree with. The recommended answers already built in are: CAP-008 and CAP-009 stay provisional (PCR-010); the business rules BR-001 to BR-009 and the ownership in ARC-004 stay proposals; the hand-off to the first live payroll stays a boundary (DEC-021); DEC-006 and DEC-007 stay open; PCR items stay unapplied.

---

# TASK 02 REVIEW DECISION AND AUTHORISATION

I have reviewed the Task 02 execution report and completion record.

I APPROVE TASK 02 AS THE WORKING BUSINESS ARCHITECTURE FOUNDATION for the Guided Payroll Activation project.

This is not formal approval of the final business case or architecture. All outstanding external decisions, assumptions and confirmations must remain visible and retain their current statuses.

## Approved working baseline

Accept the following artifacts as the initial inputs to Task 03 Part 1:

- ARC-001: the capability map, as the canonical capability definition. CAP-001 to CAP-007 keep their names. CAP-008 and CAP-009 remain proposed capabilities pending the decision in PCR-010.
- ARC-002: the value stream VS-01 to VS-06, with the revalidation loop and the open boundary VSB-01.
- ARC-006: the business architecture blueprint, including the business rules BR-001 to BR-009 and the decision points. The business rules are proposals, not approved rules, until the payroll or compliance owner confirms them.

Accept AIB-001 to AIB-012 as binding design constraints. AIB-005 and AIB-006 (data protection and masking) remain pending security confirmation and must be shown with that status.

Use ARC-003, ARC-004, ARC-005, ARC-007 and BIZ-001 to BIZ-008 as supporting inputs in their current DRAFT status. They are not approved baselines.

## Provisional assumptions

Retain the following as provisional assumptions, not confirmed business decisions:

- All 38 ownership assignments in ARC-004, and in particular the nine that rely on the inferred roles STK-010 to STK-013.
- CAP-030 (operational reporting against targets), pending DEC-023.
- Every process modelled in this task is a proposed process. The current-state process remains illustrative until validated with a real client.
- ASM-001 to ASM-014 remain unvalidated.

Do not silently convert these assumptions into approved business requirements.

## Decisions recorded in this review

- The hand-off to the first live payroll remains a boundary (VSB-01) because DEC-021 is open. Do not model a process for it unless it is shown only as a boundary.
- The proposed baseline changes PCR-001 to PCR-013 remain unapplied, except where Task 02 records them as already applied. Carry them forward. Add any new proposed changes to the Task 03 register. Do not apply any change to a baseline or earlier-task file.

## Outstanding decisions

Keep the following unresolved, with their current statuses:

- DEC-001 statutory jurisdiction.
- DEC-005 KPI baselines, cohorts and measurement rules.
- DEC-006 blocking, review and informational issue policy. Present options where a process needs it. Do not choose one.
- DEC-007 permissions and approvals for corrections, bulk fixes and activation. Present options. Do not choose one, and do not invent approval authority or escalation destinations.
- OQ-001 business sponsor and approval authority.
- OQ-002 applicable statutory and regulatory obligations.
- OQ-006 financial parameters.
- All other open decisions and questions in BIZ-005.

Do not invent answers to these questions.

## Validation tooling authorisation

You may run npx js-yaml to validate YAML, and npx -p @mermaid-js/mermaid-cli mmdc to render Mermaid diagrams, for the Task 03 files and, read-only, for earlier files. If the permission system blocks a tool, report the limitation and do not attempt a workaround. Do not install anything else or add dependencies or build files to the repository. Keep rendered images and helper scripts in the session scratchpad.

## AUTHORISATION

I explicitly authorise Claude Code to begin:

TASK 03, PART 1: OPERATIONAL MODELLING AND PROCESS FOUNDATION.

Use the approved Task 02 working baseline as the source of truth.

Task 03 Part 1 must:

1. Inspect the repository and prepare a source inventory.
2. Create the Task 03 register (OPS-009) first.
3. Create the operational process model (OPS-002).
4. Create the exception and human-review pathways (OPS-003).
5. Map each process to capabilities, objectives, KPIs, roles, value stream stages, epics and stories.
6. Distinguish deterministic activities, AI-supported activities, human review and decisions reserved to an authorised human.
7. Preserve human accountability and show unresolved authority as unresolved.
8. Validate all structured outputs and report open assumptions and decisions.
9. Update OPS-009 with actual status and validation results.
10. Create a Part 1 completion and validation report, then stop.

Do not start Part 2.

Do not modify Task 01 or Task 02 artifacts, the baseline files, or the roadmap. Record any needed change as a proposed change with a rationale.

Do not commit or push. I will review and commit.

At the end, stop and present the Part 1 deliverables for human review and approval.

Final instruction: Proceed with Task 03 Part 1 under these conditions.

---

# PART B: TASK 03 PART 1 EXECUTION PROTOCOL

## 1. Your role

Act as a Senior Business Analyst and Payroll Domain Analyst with enterprise operating-model experience. Do the work, create the artifacts, validate them, and report the results. Do not only describe what should be done.

## 2. Objective

Translate the business architecture from Task 01 and Task 02 into an operational model that explains how the work is carried out:

- Which processes deliver the capabilities and outcomes.
- What triggers each process and what must be true before it starts.
- Which roles take part, what information enters and leaves, and where decisions and handovers occur.
- How exceptions and human interventions are managed.

This is operational modelling, not application implementation or technical solution architecture.

## 3. Repository inspection and source inventory

Read CLAUDE.md and README.md first and follow them. Confirm the repository, branch and git status. Then read:

- docs/business/ (BIZ-001 to BIZ-008) and docs/architecture/ (ARC-001 to ARC-007).
- docs/diagrams/ and validation/ for Tasks 01 and 02.
- Problem statement.md, the business architecture blueprint file, product-backlog.md and the six epic files.

Identify the actual file paths and identifier conventions. Prepare a short source inventory stating which artifacts inform each part of Task 03. Do not invent missing information; record it as an open item.

## 4. Principles

1. Use the real context established in Task 01 and Task 02.
2. Preserve existing objectives, capabilities, KPIs and value stream identifiers.
3. Every process must have a business justification traced to a capability and an objective.
4. Do not invent stakeholders, process owners, policies, thresholds, regulatory obligations or approval authority. Use roles from BIZ-003 only.
5. Distinguish confirmed facts, assumptions, proposals and unresolved questions.
6. Do not name technologies, databases, APIs, frameworks, vendors or infrastructure.
7. Distinguish human activities, deterministic activities and AI-supported activities, and apply AIB-001 to AIB-012.
8. Retain human accountability wherever judgement or approval is required.
9. An AI recommendation is never an authorised decision.
10. The batch is never blocked by one failing record, and corrected records are revalidated on their own.

## 5. Stage 1: the Task 03 register, OPS-009

Create docs/operations/OPS-009-task-03-register.yaml first. It tracks: deliverable identifiers and names, status, version, source artifacts, dependencies, outstanding questions, assumptions, decisions requiring human review, proposed changes, and validation status. Use the repository's existing YAML and metadata conventions. Set every new artifact to DRAFT. Do not mark anything complete just because a file exists.

## 6. Stage 2: the operational process model, OPS-002

Create docs/operations/OPS-002-operational-process-model.yaml.

Identify the processes needed to deliver the capabilities in ARC-001 across the value stream stages VS-01 to VS-06. Expect roughly one process per value stream stage. Add a cross-cutting process only where a capability clearly needs one. Elaborate ARC-002 and BIZ-006; do not duplicate them. Use process identifiers PRC-01 and onward, and local step identifiers (S1, S2 and so on) inside each process. Do not create other enterprise-wide ID families.

For each process, record:

- Identifier, name and business purpose.
- Value stream stage, capabilities, objectives, KPIs, epics and stories it relates to.
- Trigger and preconditions.
- Participating roles (from BIZ-003) and their part.
- Ordered steps, each classified as deterministic, AI-supported, human review or reserved human decision.
- Inputs, outputs and the business information used.
- Decision points, who holds authority (or unresolved), and what happens after each outcome.
- Handoffs between roles or processes.
- Links to the exceptions in OPS-003.
- Human intervention points.
- Automation opportunities and limitations.
- Controls, open questions and assumptions.

The model must explain what happens when information is incomplete, where a decision takes place, who is accountable, and how the outcome is recorded. Show the revalidation loop from remediation back to validation. Show VSB-01 as a boundary only.

## 7. Stage 3: exception and human-review pathways, OPS-003

Create docs/operations/OPS-003-exception-and-human-review-pathways.yaml.

Identify situations where a process cannot continue as expected. Consider, where the sources support them:

- Missing or incomplete required fields.
- Conflicting information between sources.
- Unmapped or ambiguous pay codes.
- Entity or jurisdiction that cannot be resolved.
- Failed format, field or statutory validation.
- Failed bank-credential validation.
- A dry run that disagrees with expected results.
- An unavailable source or statutory engine.
- Interrupted or partly failed processing.
- A correction or bulk fix that needs approval.
- An error with no safe automatic recommendation (DEC-020).
- Escalation and referral situations.

Mark each category as supported by a source or proposed. For each exception, record: identifier (EXC-01 and onward), description, triggering condition, related process and step, initial handling, responsible or proposed responsible role, human-review requirement, escalation path (or unresolved), permitted outcomes, required information, resolution evidence, related business rules (BR) and decisions (DEC), and open questions.

Do not invent approval authority or escalation destinations. Where DEC-006 or DEC-007 would decide the handling, present the options and mark the destination as unresolved.

## 8. Human and AI boundaries

For every step, distinguish:

- Deterministic activities.
- Activities where AI may assist (suggest, summarise, classify, explain).
- Activities requiring human review.
- Decisions reserved to an authorised human.

AI never approves, activates, or clears a validation finding. Sensitive values are masked before any model call (AIB rules).

## 9. Validation

After creating the files:

- Parse all YAML with the authorised tooling.
- Check identifier consistency and that every reference to an earlier artifact exists.
- Check capability, objective, KPI, role and story traceability, in both directions.
- Check that every process has a business justification and covers its value stream stage.
- Check exception coverage and that every exception refers to a real process and step.
- Check human accountability and that no approval authority or destination was invented.
- Scan for invented facts, thresholds, regulatory claims and technology names.
- Check that no Task 01, Task 02 or baseline file was changed.

Update OPS-009 with the actual status and validation results. Do not claim a check passed unless you ran it. Report every limitation.

## 10. Required artifacts

- docs/operations/OPS-009-task-03-register.yaml
- docs/operations/OPS-002-operational-process-model.yaml
- docs/operations/OPS-003-exception-and-human-review-pathways.yaml
- docs/diagrams/ops-002-process-overview.mmd (one overview diagram of the processes and the exception loop)
- validation/task-03-part-1-validation-report.md
- validation/task-03-part-1-completion-record.md

Use only these statuses: DRAFT, UNDER_REVIEW, VALIDATED, APPROVED, PENDING_EXTERNAL_CONFIRMATION. Mark every artifact DRAFT. Do not fabricate approval.

## 11. Final report

Present:

1. Source inventory.
2. Process inventory.
3. Capability-to-process mapping.
4. KPI-to-process mapping.
5. Exception and human-review summary.
6. Open assumptions and decisions, and who must confirm them.
7. Files created and their status.
8. Validation results and limitations.
9. Issues requiring human review.
10. Readiness for Part 2.

Show the actual file paths and file changes.

## 12. Strict boundaries

Do not: modify Task 01 or Task 02 artifacts or baseline files; change the roadmap; start Part 2 or any later task; select technologies or technical components; invent regulatory obligations, policies, thresholds or approval authority; resolve decisions without evidence and human confirmation; commit or push.

Complete the task, present the artifacts and validation evidence, and STOP. Wait for explicit human approval before Part 2.
