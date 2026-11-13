# Prompt: Task 01, Business Problem, Intent and Value Model

Status: DRAFT for your review. Paste everything below the line into Claude Code, run from the repository root. Run this before Task 02 and before the operational blueprint prompt.

Purpose: turn the existing prose documents into structured, ID-based, traceable business artifacts without inventing facts.

---

# CLAUDE CODE EXECUTION PROMPT
# TASK 01: BUSINESS PROBLEM, INTENT AND VALUE MODEL

## 1. YOUR ROLE

Act as a Senior Enterprise Business Architect, Payroll Domain Analyst, Business Analyst and AI-Native Engineering Architect.

You are responsible for executing Task 01 of the Guided Payroll Activation project.

Do not merely explain what needs to be done. Perform the work, create the actual project artifacts, validate them and report the results.

Work systematically and maintain enterprise-grade documentation standards.

---

## 2. PROJECT IDENTITY

Project name: Guided Payroll Activation

Industry: Payroll management and human capital management software and services.

Business domain: Bulk guided activation of employee profiles during enterprise onboarding, tenant provisioning, or organizational restructuring.

Initial customer segment: Enterprise clients activating hundreds or thousands of employee profiles at once (taken from the problem statement; treat any further segmentation as a provisional assumption).

Engineering approach: Business-first, model-driven, AI-native engineering.

Project objective:

Establish a business-driven foundation for an automated, asynchronous and self-remediating activation capability that combines structured workflows, deterministic business and statutory rules, AI-assisted mapping and diagnostics, human oversight and governed execution.

Do not assume a specific payroll vendor, client, country or statutory jurisdiction.

Record jurisdiction-specific statutory and regulatory requirements as pending validation.

---

## 3. SOURCE DOCUMENTS AND PROJECT ISOLATION RULE

This is the existing repository guided-payroll-activation. Read CLAUDE.md and README.md first and follow them.

The following files are the approved baseline, in this order of authority. Formalize them; do not rewrite them.

1. Problem statement.md (the verified source; never change it)
2. Business Model Canvas to Business Architecture Blueprint.md
3. product-backlog.md and epic-01 to epic-06 files
4. requirements-document-map.md
5. tech-stack.md and docs/solution-architecture.svg (context only; do not design architecture in this task)

You MUST:

- Work exclusively within this repository and the assigned branch.
- Never modify the baseline files above. Record any proposed change and its rationale in the completion record instead.
- Never overwrite an existing file without explicit approval. In particular, do not overwrite README.md.
- Never access other repositories or copy content from other projects.
- Never invent client names, baselines, targets, regulations or monetary figures.
- Keep this task's documentation independent and traceable.

Before doing any work:

1. Inspect the current working directory.
2. Confirm its location and the current branch.
3. List the baseline files and check whether they are present and unmodified.
4. Check git status for uncommitted changes.
5. Confirm that this is the correct workspace for this project.

If the directory, branch, or baseline files are not as expected, STOP and explain the issue before making changes.

Do not delete, move or clean up existing files.

---

## 4. EXECUTION PROTOCOL

Execute this task in the following stages.

### Stage 1: Workspace verification

- Inspect the working directory and confirm the baseline files.
- Confirm that no baseline file will be modified.
- Establish the documentation structure under docs/business/, docs/diagrams/ and validation/.
- Create docs/business/README.md describing the status model, the ID conventions and the traceability chain (do not overwrite the root README.md).
- Create a task-level execution record.

Do not create a new Git repository or branch.

### Stage 2: Business discovery and analysis

Analyse the bulk guided activation domain using the baseline documents.

Investigate the following business areas:

- The bulk activation lifecycle, from batch initiation to first live payroll run.
- Batch setup and source data intake.
- Source data schemas and field mapping.
- Custom pay code mapping.
- Entity, parent-child and jurisdiction structure resolution.
- Baseline compensation framework configuration.
- Tax jurisdiction mapping and statutory withholding rules.
- Benefit plan assignment.
- Direct-deposit banking credential validation.
- Pre-activation validation and dry-run simulation against statutory engines.
- Asynchronous processing and partial batch activation.
- Exception isolation and remediation.
- Error reporting, audit logging and result review.
- Support and implementation specialist involvement.

Identify potential operational challenges, dependencies, information flows and business opportunities.

Distinguish clearly between:

- Confirmed project decisions (from the baseline documents).
- Business assumptions.
- Hypotheses requiring validation.
- Illustrative examples.
- Outstanding questions.

Do not present assumed payroll practices as universal facts.

### Stage 3: Business problem and intent definition

Create:

1. Business context.
2. Business problem statement.
3. Root-cause hypotheses.
4. Business consequences, mapped to the five impact dimensions in the problem statement (time to value, cost of delivery, first-payroll failure rate, regulatory and financial exposure, early churn and brand trust).
5. Business opportunity.
6. Business vision.
7. Business intent.
8. Value proposition.

Assign BN-01 to BN-05 to the five bottlenecks in the problem statement, and BP-001 and onward to business problems. Keep the exclusion of historical payroll migration visible.

The business problem must explain why the capability is required, not prescribe technology prematurely.

### Stage 4: Stakeholder and business objective modelling

Identify the relevant stakeholders, their responsibilities, business needs and decision authority. Start from the roles named in the baseline documents. Mark any role you infer beyond them as an assumption.

Develop measurable business objectives covering:

- Activation cycle time.
- Implementation and support effort.
- Data accuracy and completeness.
- First-time-right payroll processing.
- Exception management and remediation efficiency.
- Statutory and compliance control effectiveness.
- Error transparency and management visibility.
- Client experience and time to value.

Create a KPI catalogue with:

- KPI ID.
- KPI name.
- Definition.
- Calculation formula.
- Unit of measurement.
- Business objective.
- Potential data source.
- Baseline status.
- Target status.
- Measurement frequency.

The three program targets come from the problem statement: at least 65 percent faster end-to-end activation, 75 percent fewer professional support touchpoints per 1,000 employee activations, and a 99.8 percent first-time-right rate for newly activated cohorts. Record them as targets with baseline status PENDING.

Do not invent any other baseline or approved target.

### Stage 5: Activation journey (high level)

Model the high-level current-state and proposed future-state journeys for the payroll administrator and the implementation specialist. Detailed workflows, state models and decision tables belong to a later task.

Include the following potential stages and map each to its epic (EPIC-01 to EPIC-06):

1. Batch initiation and identification.
2. Source data upload and inspection.
3. Field mapping review.
4. Pay code mapping resolution.
5. Entity and jurisdiction assignment.
6. Pre-activation validation.
7. Dry-run simulation.
8. Asynchronous batch processing and progress tracking.
9. Partial activation of eligible records.
10. Exception triage and diagnostics.
11. Correction, bulk fix and revalidation.
12. Outcome review and history.
13. Hand-off to the first live payroll run.

Map the five bottlenecks (BN-01 to BN-05) to the journey stages where they occur.

Produce readable Mermaid diagrams.

Clearly label the current-state model as provisional where actual client processes are not available.

### Stage 6: AI opportunity and decision assessment

Evaluate each major activation activity and classify the appropriate approach:

- Deterministic business and statutory rules.
- Conventional analytics.
- AI/ML.
- Generative AI.
- Human judgement.
- Hybrid approach.

For each proposed AI opportunity, document:

- Business problem addressed.
- Proposed AI capability.
- Expected business value.
- Required data.
- Reliability requirements.
- Potential failure modes.
- Human oversight.
- Deterministic validation or control.
- Auditability requirements.

Apply these principles and record them as binding AI boundary rules (AIB-001 and onward):

- Do not introduce AI without a justified business benefit.
- AI only suggests. People approve. Deterministic rules and the statutory engines decide validity.
- Do not treat model confidence as proof of correctness.
- Do not allow AI to bypass statutory rules or business policies.
- Do not give AI components unrestricted access to payroll systems or personal data.
- Mask sensitive values (such as tax identifiers and bank details) before any model call.
- Keep approval and activation of records within controlled workflows.
- Treat high-impact decisions with appropriate human accountability and governance.

State clearly which problems need no AI and are solved by workflow and rules alone.

### Stage 7: Scope, assumptions, constraints and risks

Define the initial in-scope and out-of-scope capabilities.

Potential initial scope:

- Batch setup and identification.
- Bulk employee data intake and inspection.
- Source-to-payroll field mapping.
- Custom pay code mapping.
- Entity and jurisdiction context resolution.
- Pre-activation validation and dry-run simulation.
- Asynchronous batch processing and progress tracking.
- Partial activation with record-level error isolation.
- Exception remediation and bulk fixes.
- Outcome review, history and audit.
- Operational reporting against the target metrics.

Potential exclusions:

- Migration of historical payroll records, such as prior pay runs and year-to-date balances.
- Replacement of the payroll calculation or statutory engines.
- Replacement of the client's HR information system.
- Autonomous statutory or regulatory decisions.
- Unrestricted AI access to payroll data or systems.
- Full enterprise-wide compliance platform.

Create structured registers for:

- Assumptions.
- Constraints.
- Risks (each with a mitigation and an owner role).
- Dependencies.
- Open decisions.
- Open questions.

Assign IDs to each item and indicate its validation status.

### Stage 8: Business case consolidation

Create a consolidated Business Case and Value Model.

It must connect:

Business Problem → Business Opportunity → Business Objectives → Required Capabilities → AI Opportunities → Expected Benefits → KPIs → Business Value.

Include an option comparison: current state, workflow and rules without AI, and workflow and rules with governed AI. Measure the incremental value of AI as the difference between the last two.

Where financial data is unavailable, define a value calculation methodology (formulas and required inputs) rather than inventing monetary benefits.

---

## 5. REQUIRED PROJECT ARTIFACTS

Create the following files, creating directories as needed:

docs/
  business/
    README.md
    BIZ-001-business-context-and-problem-statement.md
    BIZ-002-business-case-and-value-model.md
    BIZ-003-stakeholder-register.yaml
    BIZ-004-business-objectives-and-kpi-catalogue.yaml
    BIZ-005-assumptions-constraints-and-risks.yaml
    BIZ-006-activation-journey.md
    BIZ-007-ai-opportunity-assessment.yaml
    BIZ-008-scope-and-boundaries.yaml
  diagrams/
    current-state-journey.mmd
    proposed-future-state-journey.mmd
validation/
  task-01-validation-report.md
  task-01-completion-record.md

Use Markdown for human-readable documentation.

Use YAML for structured, machine-readable business models.

Use Mermaid for process and journey diagrams.

Maintain consistent identifiers and cross-references across all artifacts.

---

## 6. MODEL QUALITY AND TRACEABILITY

Establish traceability across the business artifacts.

At minimum, ensure:

- Every bottleneck and business problem links to one or more objectives.
- Every objective has an associated KPI or measurement approach.
- Every proposed capability supports a business objective.
- Every AI opportunity addresses a defined business problem.
- Every material risk has an associated control or mitigation and an owner role.
- Every assumption requiring validation is recorded with a validation method.
- Every major scope decision is documented.
- Every journey stage maps to an epic and, where relevant, a bottleneck.

Use stable identifiers such as:

- BN-01: Bottleneck (from the problem statement).
- BP-001: Business Problem.
- BO-001: Business Objective.
- KPI-001: Performance Indicator.
- STK-001: Stakeholder.
- CAP-001: Business Capability (provisional reference only).
- AI-001: AI Opportunity.
- AIB-001: AI Boundary Rule.
- RSK-001: Risk.
- ASM-001: Assumption.
- DEC-001: Open Decision.
- OQ-001: Open Question.
- EPIC-01 to EPIC-06 and PA-01 onward: existing epics and stories.

Do not create detailed Task 02 capability models yet. Only introduce provisional capability references where necessary for traceability.

---

## 7. VALIDATION AND VERIFICATION

After generating the artifacts:

1. Validate YAML syntax using available local tools.
2. Validate Mermaid diagram structure as far as available tools permit.
3. Check Markdown files for completeness.
4. Check identifier consistency.
5. Check cross-document traceability, including two-way links.
6. Check that no unsupported statutory, legal or regulatory claims have been introduced.
7. Check that AI controls and human oversight are adequately documented.
8. Check that all outstanding assumptions and decisions are visible.
9. Check that no baseline file was modified.

Do not install additional software or packages without asking first.

Do not claim that a validation has passed unless it has actually been performed.

If a validation tool is unavailable, report that limitation explicitly.

---

## 8. HUMAN REVIEW AND APPROVAL GATE

Do not assume that generating an artifact means that it is approved.

Use the following statuses:

- DRAFT
- UNDER_REVIEW
- VALIDATED
- APPROVED
- PENDING_EXTERNAL_CONFIRMATION

Identify the items that require business-owner, payroll-domain, compliance or security confirmation.

Produce a list of unresolved questions that must be answered before final business-case approval.

Do not fabricate stakeholder approval or external confirmation.

---

## 9. TASK 01 ACCEPTANCE CRITERIA

Task 01 is ready for review only when:

- Business context is documented.
- Business problem is clearly articulated and mapped to BN-01 to BN-05.
- Business intent and value proposition are defined.
- Stakeholders are identified.
- Business objectives are documented.
- KPIs and measurement approaches are established, with baselines and targets marked pending.
- The activation journey is modelled at a high level.
- AI opportunities are assessed and AI boundary rules are defined.
- Initial scope and boundaries are documented.
- Assumptions, constraints, risks, dependencies and open decisions are registered.
- Structured artifacts are created.
- Validation checks are completed or limitations reported.
- Outstanding decisions are clearly identified.
- Readiness for Task 02 is assessed.

A successful execution does not mean that the business case has received formal approval.

---

## 10. FINAL EXECUTION REPORT

At completion, provide a concise report in the terminal covering:

1. Workspace verification.
2. Artifacts created.
3. Business analysis completed.
4. YAML and diagram validation results.
5. Traceability assessment.
6. Outstanding assumptions and decisions.
7. Issues and limitations.
8. Task 01 acceptance criteria status.
9. Readiness recommendation for Task 02.

Provide the actual file paths of all deliverables.

---

## 11. EXECUTION BOUNDARIES

IMPORTANT:

- Execute Task 01 only.
- Do not start Task 02.
- Do not create application source code.
- Do not build frontend or backend components.
- Do not implement APIs or database schemas.
- Do not implement AI agents or model gateways.
- Do not prematurely design detailed technical architecture or change the tech stack.
- Do not modify the baseline files.
- Do not push or open a pull request unless asked.
- Do not silently invent missing business information.

If a critical decision cannot be made safely, document it as an open decision rather than guessing.

Complete the task, present the artifacts and validation evidence, and STOP.

Wait for explicit human approval before proceeding to Task 02.
