# Prompt: Task 01, Business Problem, Intent and Value Model

Status: DRAFT for your review. Paste everything below the line into Claude Code, run from the repository root. Run this before Task 02 and before the operational blueprint prompt.

Purpose: turn the existing prose documents into structured, ID-based, traceable business artifacts without inventing facts.

---

# CLAUDE CODE EXECUTION PROMPT
# TASK 01 (GUIDED PAYROLL ACTIVATION): BUSINESS PROBLEM, INTENT AND VALUE MODEL

## 1. Your role

Act as a Senior Enterprise Business Analyst, Payroll Domain Analyst, and AI-Native Engineering Architect. Do the work, create the artifacts, validate them, and report the results. Do not only describe what should be done.

## 2. Context and source of truth

This is the existing repository guided-payroll-activation. Read CLAUDE.md and README.md first and follow them. Formalize, do not rewrite. These files are the baseline, in order of authority:

1. Problem statement.md (verified source; never change it)
2. Business Model Canvas to Business Architecture Blueprint.md
3. product-backlog.md and epic-01 to epic-06 files
4. requirements-document-map.md
5. tech-stack.md (context only; do not design architecture in this task)

Do not invent client names, baselines, targets, regulations, or money figures. Where information is missing, record an assumption, open question, or open decision.

## 3. Execution protocol

Stage 1, workspace verification: confirm the repository, branch, and baseline files. Report anything unexpected. Do not create a new repository or branch.

Stage 2, problem definition: from the problem statement, create the business context, the problem statement, the root-cause hypotheses, and the business consequences. Assign BN-01 to BN-05 to the five bottlenecks in the problem statement, and BP-001 and onward to business problems. Map the five impact dimensions (time to value, cost of delivery, first-payroll failure rate, regulatory exposure, early churn) to consequences. Keep the exclusion of historical payroll migration visible.

Stage 3, intent, vision and value proposition: define the business vision, intent, and value proposition from the existing blueprint. Explain why the capability is needed without prescribing technology.

Stage 4, stakeholders: build a stakeholder register from the existing documents (payroll administrators, implementation specialists, and any other roles named). For each stakeholder, record responsibilities, needs, and decision rights. Mark any role you infer beyond the source documents as an assumption.

Stage 5, objectives and KPIs: define measurable business objectives (BO-001 and onward) and a KPI catalogue (KPI-001 and onward). Each KPI needs: ID, name, definition, calculation formula, unit, objective, potential data source, baseline status, target status, and measurement frequency. The three program targets (65 percent faster activation, 75 percent fewer support touchpoints per 1,000 activations, 99.8 percent first-time-right) come from the problem statement. Record them as targets with baseline status PENDING. Do not invent any other baseline or target.

Stage 6, AI opportunity assessment: classify each major activity as deterministic rules, conventional analytics, AI assistance, human judgement, or hybrid. For each AI opportunity (AI-001 and onward) record the problem addressed, expected value, required data, failure modes, human oversight, deterministic control, and audit need. State which problems need no AI. Define binding AI boundary rules (AIB-001 and onward), including: AI only suggests; people approve; deterministic rules and statutory engines decide validity; model confidence is never proof of correctness; AI never activates a record; sensitive values are masked before model calls.

Stage 7, scope, assumptions, constraints, risks: define in-scope and out-of-scope items, and create registers for assumptions (ASM-001), constraints, risks (RSK-001, each with a mitigation and an owner role), dependencies, open decisions (DEC-001), and open questions (OQ-001). Give each a validation status.

Stage 8, business case: consolidate the chain Business Problem to Opportunity to Objectives to Required Capabilities (provisional CAP references only) to AI Opportunities to Expected Benefits to KPIs to Business Value. Where financial data is unavailable, define a value calculation methodology with formulas and required inputs. Do not state money benefits.

## 4. Required artifacts

- docs/business/BIZ-001-business-context-and-problem-statement.md
- docs/business/BIZ-002-business-case-and-value-model.md
- docs/business/BIZ-003-stakeholder-register.yaml
- docs/business/BIZ-004-objectives-and-kpi-catalogue.yaml
- docs/business/BIZ-005-assumptions-constraints-and-risks.yaml
- docs/business/BIZ-006-ai-opportunity-assessment.yaml
- docs/business/BIZ-007-scope-and-boundaries.yaml
- validation/task-01-validation-report.md
- validation/task-01-completion-record.md

Markdown for readable documents, YAML for structured models. Use consistent IDs and cross-references. Do not create detailed Task 02 capability models; provisional CAP references for traceability only.

## 5. Traceability and validation

Ensure: every problem links to an objective; every objective has a KPI or measurement approach; every AI opportunity addresses a defined problem; every risk has a mitigation and an owner role; every assumption has a validation method; every scope decision is documented.

Validate: parse all YAML with local tools; check ID consistency and two-way links; check Markdown completeness; scan for unsupported regulatory or legal claims; confirm AI controls and human oversight are documented; confirm open items are visible. Do not install software without asking. Do not claim a check passed unless you ran it, and report any limitation.

## 6. Status and approval gate

Mark every artifact DRAFT. Use only these statuses: DRAFT, UNDER_REVIEW, VALIDATED, APPROVED, PENDING_EXTERNAL_CONFIRMATION. Do not fabricate approval or external confirmation. List what needs confirmation from the business owner, payroll domain experts, compliance, or security, and list the unresolved questions that block final business-case approval.

## 7. Acceptance criteria and final report

Ready for review when: context and problem are documented; intent and value proposition are defined; stakeholders and objectives are documented; KPIs are defined with baselines and targets marked pending; AI opportunities and boundary rules are assessed; scope, assumptions, constraints, risks, dependencies, and decisions are registered; validation is done or limitations reported; readiness for Task 02 is assessed.

End with a concise report: workspace verification, files created (paths), analysis completed, validation results, traceability assessment, open assumptions and decisions, limitations, acceptance status, and a readiness recommendation for Task 02.

## 8. Boundaries

Execute Task 01 only. Do not start Task 02. Do not write application code, schemas, or APIs. Do not design detailed architecture or change the tech stack. Do not modify baseline files; record proposed changes and rationale in the completion record. Do not push or open a pull request unless asked. If a critical decision cannot be made safely, record it as an open decision.

Complete the task, present the artifacts and validation evidence, and STOP. Wait for explicit human approval before Task 02.
