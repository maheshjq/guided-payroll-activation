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

# TASK 3, PART 1

# Operational Modelling and Process Foundation

## Project context

You are continuing the existing Guided Payroll Activation project. Act as a Senior Business Analyst and Payroll Domain Analyst with enterprise operating-model experience. Do the work, create the artifacts, validate them, and report the results. Do not only describe what should be done.

The project has completed:

- Task 01: Business Problem, Intent and Value Model (docs/business/, BIZ-001 to BIZ-008).
- Task 02: Business Architecture and Capability Modelling (docs/architecture/, ARC-001 to ARC-007).

You are now implementing Task 03, Part 1 of the Operational Blueprint, Requirements and Decision Modelling task. Do not create a new project or change the roadmap.

## 1. Objective

Translate the business architecture established in Tasks 01 and 02 into an operational model.

The purpose is to establish:

- How the business capabilities operate in practice.
- Which operational processes deliver the intended business outcomes.
- Which roles participate in each process.
- What information enters and leaves each process.
- Where decisions, handovers and dependencies occur.
- How exceptions and human interventions are managed.

This is an operational modelling exercise, not application implementation or technical solution architecture.

## 2. Repository inspection and project continuity

Before creating anything, inspect the repository. Read CLAUDE.md and README.md first and follow them. Confirm the repository, branch and git status. Then read:

- docs/business/ (BIZ-001 to BIZ-008) and docs/architecture/ (ARC-001 to ARC-007).
- docs/diagrams/ and validation/ for Tasks 01 and 02.
- Problem statement.md, the business architecture blueprint file, product-backlog.md and the six epic files.

Identify the actual file paths and existing identifier conventions.

Prepare a short source inventory explaining which existing artifacts will inform Task 03.

Do not invent missing Task 01 or Task 02 artifacts. Report missing or incomplete information as an open item.

## 3. Implementation principles

1. Use the actual business context established in Tasks 01 and 02.
2. Preserve existing objectives, capabilities, KPIs and value stream identifiers.
3. Every proposed process must have a business justification, traced to a capability and an objective.
4. Do not invent stakeholders, process owners, policies, thresholds, regulatory obligations or approval authority. Use roles from BIZ-003 only.
5. Distinguish confirmed facts, assumptions, proposals and unresolved questions.
6. Do not introduce specific technologies, databases, APIs, frameworks, vendors or infrastructure.
7. Distinguish human activities, deterministic business activities and AI-supported activities, and apply AIB-001 to AIB-012.
8. Retain human accountability wherever business judgement or approval is required.
9. Do not treat an AI-generated recommendation as an authorised business decision.
10. A failing record never blocks the batch, and corrected records are revalidated on their own.

## 4. Establish the Task 03 working register: OPS-009

Create the Task 03 register first.

Location: docs/operations/OPS-009-task-03-register.yaml

The register tracks:

- Task 03 deliverable identifiers and names.
- Status and version.
- Source artifacts and dependencies.
- Outstanding questions and assumptions.
- Decisions requiring human review and proposed changes.
- Validation status.

Use the repository's existing metadata and YAML conventions. Use DRAFT status for newly created artifacts. Do not mark deliverables complete merely because files have been created.

## 5. Develop the Operational Process Model: OPS-002

Create docs/operations/OPS-002-operational-process-model.yaml.

Identify the operational processes required to deliver the capabilities in ARC-001 across the value stream stages VS-01 to VS-06. Expect roughly one process per value stream stage, and add a cross-cutting process only where a capability clearly needs one. Elaborate ARC-002 and BIZ-006; do not duplicate them.

For each process, describe:

- Process identifier (PRC-01 and onward), name and business purpose.
- Related business domain. The project has no separate domain model, so use the Level 1 capability group from ARC-001 as the domain, and record this mapping as an assumption in OPS-009.
- Related value stream stage, business capability, objective, KPI, epic and story.
- Trigger or initiating event, and preconditions.
- Participating business roles (from BIZ-003).
- Process activities and sequence, each classified as deterministic, AI-supported, human review or reserved human decision, and each naming the capability it exercises by ID and name.
- Inputs and outputs, and the business information used.
- Decision points, and who holds authority (or unresolved).
- Handoffs between roles or capabilities.
- Exceptions and dependencies, linked to OPS-003.
- Human intervention points.
- Automation opportunities and limitations.
- Related controls and unresolved matters.

Use local step identifiers (S1, S2 and so on) within each process rather than inventing additional enterprise-wide identifier families.

Give each Level 2 and Level 3 capability at least one step of its own. Do not merge distinct capabilities into one step, for example the separate validation checks for compensation, tax and withholding, benefits and banking details, unless they share the same trigger, owner and exceptions; if you merge them, record why.

### Process modelling expectations

The model should explain the actual business operation. For example:

- What triggers the process?
- Who performs the first activity?
- What information is required?
- What happens when information is incomplete?
- Where does a decision take place, and who is accountable for it?
- What happens after the decision?
- How is the outcome communicated or recorded?

Ensure the processes collectively cover the important capabilities and outcomes from Task 02. Show the revalidation loop from remediation back to validation. Show VSB-01 (hand-off to the first live payroll) as a boundary only.

### Capability operations view

The process model is organised by process. Also explain how each capability operates in practice, so a reader can start from a capability instead of a process. In OPS-002, add a capability operations section with one entry for every Level 2 and Level 3 capability in ARC-001, and a short summary for every Level 1 capability, including the cross-cutting CAP-008 and CAP-009.

For each capability, describe:

- Capability identifier and name, exactly as in ARC-001.
- How it operates in practice, in plain language, in two or three sentences.
- The processes and steps that exercise it.
- Performing, accountable and consulted roles (from ARC-004, marked as assumptions).
- Decision points that belong to it, and who holds authority (or unresolved).
- Exceptions from OPS-003 that affect it.
- Business rules (BR), constraints and controls that apply.
- AI involvement, if any, with the boundary rules that limit it.
- Open decisions and questions.
- Coverage note: whether it is exercised by its own steps, shares a step with another capability, or is not yet exercised. Never hide a capability that has no step; list it as a gap.

## 6. Develop Exception and Human-Review Pathways: OPS-003

Create docs/operations/OPS-003-exception-and-human-review-pathways.yaml.

Identify situations where normal operational processes cannot continue as expected.

Consider, where the sources support them:

- Missing or incomplete required fields.
- Conflicting information between sources.
- Unmapped or ambiguous pay codes.
- Entity or jurisdiction that cannot be resolved.
- Failed format, field or statutory validation.
- Failed bank-credential validation.
- A dry run that disagrees with expected results.
- An unavailable information source or statutory engine.
- Interrupted or partly failed processing.
- A correction or bulk fix that needs approval.
- An error with no safe automatic recommendation (DEC-020).
- Stakeholder disputes, for example a client or employee disputing a mapping, an entity or jurisdiction assignment, a validation finding or an activation outcome.
- Suspected fraud or risk indicators, where relevant, for example an unexpected change to direct-deposit banking details. Mark these as proposed, and do not invent detection rules, thresholds or investigation procedures.
- Requests requiring human judgement, escalation and referral situations.

Mark each category as supported by a source or proposed.

For each exception, define:

- Exception identifier (EXC-01 and onward) and description.
- Triggering condition.
- Related process and step.
- Related capability (ID and name).
- Initial handling activity.
- Responsible or proposed responsible role.
- Human-review requirement.
- Escalation path (or unresolved).
- Permitted outcomes.
- Required information and resolution evidence.
- Related business rules (BR) and decisions (DEC).
- Outstanding questions.

Where DEC-006 or DEC-007 would decide the handling, present the options and mark the destination as unresolved.

### Human and AI boundaries

Clearly distinguish:

- Activities that can be automated deterministically.
- Activities where AI can assist (suggest, summarise, classify, explain).
- Activities requiring human review.
- Decisions that must remain with an authorised human.

AI must not independently exercise authority that belongs to a human decision-maker. AI never approves, activates or clears a validation finding. Sensitive values are masked before any model call. Do not invent approval authority or escalation destinations.

## 7. Validate Part 1

After creating the deliverables:

- Check YAML syntax with the authorised tooling.
- Check identifier consistency and that every reference to an earlier artifact exists.
- Check capability, objective, KPI, role and story traceability, in both directions.
- Check that every Level 2 and Level 3 capability is exercised by at least one step and has a capability operations entry, and that every capability name matches ARC-001.
- Check that every process names its business domain and every exception names its capability.
- Check that all major processes have a meaningful business justification and cover their value stream stage.
- Check exception coverage and that every exception refers to a real process and step.
- Check human accountability and that no approval authority or destination was invented.
- Check for invented business facts, thresholds, regulatory claims, technology names or unsupported assumptions.
- Check that no Task 01, Task 02 or baseline file was changed.

Update OPS-009 with the actual deliverable status and validation results. Do not claim a check passed unless you ran it, and report every limitation.

## 8. Required files, final report and checkpoint

Create these files (create folders as needed):

- docs/operations/OPS-009-task-03-register.yaml
- docs/operations/OPS-002-operational-process-model.yaml
- docs/operations/OPS-003-exception-and-human-review-pathways.yaml
- docs/diagrams/ops-002-process-overview.mmd (one overview diagram of the processes and the exception loop)
- validation/task-03-part-1-validation-report.md
- validation/task-03-part-1-completion-record.md

Use only these statuses: DRAFT, UNDER_REVIEW, VALIDATED, APPROVED, PENDING_EXTERNAL_CONFIRMATION. Mark every artifact DRAFT. Do not fabricate approval.

Present:

1. Task 01 and Task 02 source inventory.
2. Operational process inventory.
3. Capability-to-process mapping and capability operations summary, including any capability with thin coverage (one step, or a step shared with another capability).
4. KPI-to-process mapping.
5. Exception and human-review summary.
6. Open assumptions and decisions, and who must confirm them.
7. Files created and their status.
8. Validation results and limitations.
9. Issues requiring human review.
10. A self-assessment against the human review checklist: each process traces to a real need, capability or outcome; triggers, steps, inputs, outputs and handovers are understandable; roles come from existing sources; decision points link to decision rights or are marked unresolved; KPIs connect to processes for a meaningful reason, not merely because the identifiers exist; exception categories are supported or marked proposed; human-review pathways do not invent authority or destinations; AI-supported activities are distinguished from deterministic activities and human decisions; assumptions, questions and dependencies are visible in OPS-009; earlier artifacts are unchanged.
11. Readiness for Part 2.

Show the actual file changes. Stop after Part 1. Do not begin Part 2 automatically. Wait for human review and confirmation.

## 9. Strict boundaries

Do not:

- Modify Task 01 or Task 02 artifacts, or the baseline files.
- Change the roadmap.
- Start Part 2, Task 04 or application implementation.
- Select technologies or technical components.
- Invent regulatory obligations, policies, thresholds or approval authority.
- Resolve decisions without evidence and human confirmation.
- Commit or push changes.

The objective is to establish a traceable operational foundation for Part 2.
