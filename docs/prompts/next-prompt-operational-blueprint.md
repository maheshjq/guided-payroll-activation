# Next prompt: Operational Blueprint, Decision Model and Requirements (P0 path)

Status: DRAFT for your review. Paste everything below the line into Claude Code. Edit the "Scope choice" section first if you want a different epic.

Run order: Task 01 prompt, then Task 02 prompt, then this one (see `task-01-business-foundation-prompt.md` and `task-02-business-architecture-prompt.md`). This prompt uses the IDs and registers those tasks create, so check that the files in docs/business/ and docs/architecture/ exist before running it.

Why this task is next: the repository already holds the problem statement, business architecture blueprint, six epics, a backlog, and a draft tech stack. It does not yet hold the user journey, workflow, and decision model for a prioritized epic, which was step 5 of the original prompt chain. This task covers the operational blueprint, requirements, and decision modelling.

---

# CLAUDE CODE EXECUTION PROMPT
# TASK 03 (GUIDED PAYROLL ACTIVATION): OPERATIONAL BLUEPRINT, DECISION MODEL AND REQUIREMENTS

## 1. Your role

Act as a Senior Business Analyst, Payroll Domain Analyst, and AI-Native Engineering Architect. Do the work, create the artifacts, validate them, and report the results. Do not only describe what should be done.

## 2. Context and source of truth

This is the existing repository guided-payroll-activation. Read CLAUDE.md and README.md first and follow them. Treat these as the approved working baseline, in this order of authority:

1. Problem statement.md
2. Business Model Canvas to Business Architecture Blueprint.md
3. product-backlog.md and epic-01 to epic-06 files
4. requirements-document-map.md
5. docs/business/ (BIZ-001 to BIZ-008) and docs/architecture/ (ARC-001 to ARC-007), once approved
6. tech-stack.md and docs/solution-architecture.svg (draft, for context only)

Do not change the problem statement. Do not change other baseline files without recording a proposed change and its rationale in the new register. Do not invent client names, baselines, or figures.

## 3. Scope choice

Cover the P0 path of the product: the P0 stories PA-01 to PA-05, PA-07 to PA-13, and PA-15 across Epics 1 to 6, as one end-to-end flow. Go deepest on Epic 3 (validate and simulate) and Epic 5 (remediate), because they carry the largest business value. Do not model P1 or P2 stories except to note dependencies.

## 4. Execution protocol

Stage 1, workspace verification: confirm you are in the repository on the assigned branch, list the baseline files, and report anything unexpected. Do not create a new repository or branch.

Stage 2, current-state and future-state journey: for the payroll administrator and the implementation specialist, refine the high-level journeys in BIZ-006 into detailed current-state (labelled provisional where actual client processes are unknown) and future-state journeys, with pain points mapped to the five bottlenecks (BN-01 to BN-05) in the problem statement. Produce readable Mermaid diagrams, including a swimlane-style workflow for the end-to-end P0 path.

Stage 3, state model: define the lifecycle states and allowed transitions for a batch and for an individual record (for example draft, mapped, validated, simulated, eligible, exception, activated, failed, retried). Show how one failing record is isolated without blocking the batch, how retries stay idempotent, and how corrected records re-enter validation alone.

Stage 4, decision model: define decision tables for the key decisions: record eligibility, severity of a validation finding (blocking or warning), whether a mapping suggestion can be auto-proposed or needs review, and when a batch may start activation. For every decision, state the inputs, rules, outcome, and owner.

Stage 5, rules, AI, or human: for each major activity, classify the right approach: deterministic rules, conventional analytics, AI assistance, human judgement, or hybrid. Apply these binding principles: AI only suggests; people approve; deterministic rules and the statutory engines decide validity; model confidence is never proof of correctness; AI never activates a record. For each AI use, document the business problem, required data, failure modes, human oversight, deterministic control, and audit need. Do not add AI where rules are enough.

Stage 6, requirements: write functional and non-functional requirements for the P0 path, each traced to a backlog story, an objective, and a target metric. Include error-reporting detail (row and column coordinates, suggested fix), audit logging, tenant isolation, performance and scale assumptions marked as assumptions, and data protection for tax IDs and bank details. Write requirements as testable statements.

Stage 7, registers: record assumptions, risks (with mitigation and owner role), dependencies, open decisions, and open questions, each with an ID and a validation status.

## 5. Required artifacts

Create this structure under docs/operations/ and validation/ (create folders as needed):

- docs/operations/OPS-001-journey-and-workflow.md (journeys, swimlane workflow, pain-point mapping, diagrams embedded)
- docs/operations/OPS-002-batch-and-record-state-model.yaml
- docs/operations/OPS-003-decision-model.yaml
- docs/operations/OPS-004-rules-ai-human-assessment.yaml
- docs/operations/OPS-005-requirements-catalogue.yaml
- docs/operations/OPS-006-assumptions-risks-and-open-decisions.yaml
- docs/diagrams/ (one .mmd file per diagram)
- validation/task-03-validation-report.md
- validation/task-03-completion-record.md

Use Markdown for readable documents, YAML for structured models, and Mermaid for diagrams.

## 6. Identifiers and traceability

Use stable IDs: EPIC-01 to EPIC-06 for epics, PA-xx for the existing stories, BN-01 to BN-05 for the five bottlenecks in the problem statement, REQ-F-001 and REQ-NF-001 for requirements, DEC-001 for decisions, AI-001 for AI uses, RSK-001 for risks, ASM-001 for assumptions, OQ-001 for open questions.

Ensure at minimum: every pain point links to a bottleneck; every requirement links to a story and a target metric; every AI use links to a problem and an oversight control; every risk has a mitigation and an owner role; every assumption is recorded with how it will be validated.

## 7. Validation

After creating the artifacts: parse all YAML with local tools; check Mermaid structure (if a renderer is unavailable, say so and ask before installing anything); check identifier consistency and two-way trace links; scan for unsupported legal or regulatory claims; confirm AI controls and human oversight are documented; confirm all open items are visible. Do not claim a check passed unless you ran it. Report any limitation.

## 8. Status and approval gate

Mark every artifact DRAFT. Use these statuses only: DRAFT, UNDER_REVIEW, VALIDATED, APPROVED, PENDING_EXTERNAL_CONFIRMATION. Do not fabricate approval or external confirmation. List the items that need confirmation from the business owner, payroll domain experts, compliance, or security.

## 9. Acceptance criteria

Ready for review when: journeys and the end-to-end workflow are documented; batch and record state models are defined; decision tables exist for the four key decisions; every major activity is classified as rules, AI, or human; requirements are testable and traced; registers are complete; validation is done or limitations are reported; readiness for the next task is assessed.

## 10. Final report

End with a concise report: workspace verification, files created (with paths), analysis completed, validation results, traceability assessment, open assumptions and decisions, limitations, acceptance status, and a readiness recommendation for the next task.

## 11. Boundaries

Execute this task only. Do not write application code, database schemas, or APIs. Do not redesign the architecture or change the tech stack. Do not modify the baseline files except to record proposed changes. Do not push or open a pull request unless asked. If a critical decision cannot be made safely, record it as an open decision.

Complete the task, present the artifacts and validation evidence, and STOP. Wait for explicit human approval before any further task.
