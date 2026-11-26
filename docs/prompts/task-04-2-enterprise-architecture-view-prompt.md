# Task 04.2 Enterprise Architecture View prompt

This prompt is the Guided Payroll Activation version of the sample prompt in section 13 of the Task 4.2 learning guide (`docs/learning/Task4_part5_Enterprise Architecture View_Learning_Guide.docx.md`). The learning guide uses a bank customer onboarding case. This version uses the identifiers, constraints and gaps recorded in this repository.

Use it after Task 04.1 (`docs/solution/SOL-001-architecture-requirements-assessment.md`). Paste everything below the line into Claude Code.

Differences from the learning-guide prompt:

- The baseline is BIZ-001 to BIZ-008, ARC-001 to ARC-007, OPS-002, OPS-003 and OPS-009. This repository has no ARC-008, no OPS-001 and no OPS-004 to OPS-008.
- There is no AUTH-029 in this repository. The analysis-only and technology-selection boundaries come from DEC-022, OOS-010 and the rules in section 11 of the prompt.
- ARC-005 here holds capability dependencies. Information concepts come from the blueprint and SOL-001 section 8.
- The external capabilities are the systems and integration needs recorded in SOL-001 sections 5 and 7. They carry assessment-local references (XC-P01 to XC-P11), not repository IDs.
- The AI boundaries are AIB-001 to AIB-012, and the constraints are CON-001 to CON-008.

---

# Task 04.2: Enterprise Architecture View

Act as an Enterprise Architect with expertise in AI-native engineering, enterprise architecture, payroll and workforce-management architecture, and model-driven solution design.

## Context

Using the Task 04.1 Architecture Requirements Assessment (SOL-001) and the Task 01 to Task 03 Part 1 working baseline, develop an Enterprise Architecture View for the Guided Payroll Activation solution. The solution improves bulk guided activation of employee profiles in a payroll management system.

Read these sources:

- Problem statement.md (verified source for the problem, bottlenecks and the three target metrics).
- Business Model Canvas to Business Architecture Blueprint.md.
- Task 01: BIZ-001 to BIZ-008 in docs/business.
- Task 02: ARC-001 to ARC-007 in docs/architecture.
- Task 03 Part 1: OPS-002, OPS-003 and OPS-009 in docs/operations.
- Task 04.1: docs/solution/SOL-001-architecture-requirements-assessment.md.
- product-backlog.md and epic-01 to epic-06 for stories PA-01 to PA-16.
- tech-stack.md and docs/solution-architecture.svg, as a proposal only.

Status of the sources. No source artifact is approved. Task 01 and Task 02 are working baselines. Task 03 Part 1 is a draft awaiting review. SOL-001 is a draft working analysis. Do not describe any of them as formally approved. The Google Cloud stack in tech-stack.md is a proposal, not a constraint (DEC-022), and is not evidence of any existing system.

## Objective

Establish how the proposed guided activation solution fits into the enterprise environment. Identify and describe six architecture domains:

1. Business Architecture
2. Application Architecture
3. Data Architecture
4. Technology and Infrastructure Architecture
5. Integration Architecture
6. Security and Governance Architecture

## 1. Business Architecture

Identify and describe:

- Business capabilities supported by the solution.
- Business processes and value stream stages.
- Key business actors and stakeholder groups.
- Capability relationships and dependencies.
- Business ownership and accountability considerations.
- Boundaries between deterministic, AI-supported and human-controlled activities.

Use the capability baseline, particularly ARC-001 (CAP-001 to CAP-038), ARC-002 (VS-01 to VS-06 and the open boundary VSB-01), ARC-004 (ownership), ARC-006 (business rules BR-001 to BR-009) and ARC-007 (proposed changes PCR-001 to PCR-013). Use OPS-002 for the six processes and OPS-003 for the exception and human-review pathways. Use BIZ-003 for stakeholders.

Explain how the solution supports bulk guided activation across the six epics. CAP-008 and CAP-009 are proposed capabilities pending PCR-010, and CAP-030 is pending DEC-023. Show them with that status. Do not create new capabilities without labelling them as proposed additions requiring review. The inferred roles STK-010 to STK-013 are assumptions. Show them as assumptions.

## 2. Application Architecture

Identify and describe:

- Existing application capabilities relevant to activation.
- Proposed solution-level responsibilities.
- External applications and service capabilities.
- Application boundaries and interactions.
- Responsibilities that existing systems may fulfil.
- Capabilities that may need additional solution components, subject to later design decisions.

Consider these modelled external capabilities, taken from SOL-001 sections 5 and 7. The references are assessment-local, not repository IDs.

- XC-P01: Payroll management system, including the current guided activation wizard.
- XC-P02: Payroll engine, which receives activated cohorts and runs the first live payroll (OOS-002).
- XC-P03: Statutory engines, for validation and dry run (DEC-015, DEC-016, ASM-006).
- XC-P04: Payroll data model (DEP-005).
- XC-P05: Client source systems producing external payroll exports (ASM-004, DEC-009).
- XC-P06: Client HR information system, not to be replaced (OOS-003).
- XC-P07: Pay-code catalogue (ASM-010, DEP-002).
- XC-P08: Entity hierarchy source (ASM-005, DEP-003).
- XC-P09: Source-system, statutory-data or verification providers, which may not exist (DEC-004, DEP-006).
- XC-P10: Identity provider for client users (gap G-13).
- XC-P11: Enterprise data protection, information security and AI governance functions (gap G-15).

These are modelled external capabilities. Do not assume their actual systems, products, vendors, owners, hosting or interfaces are confirmed. Preserve the constraints that the payroll engine and statutory engines are not redesigned (OOS-002) and the client HR information system is not replaced (OOS-003). Raise decision AD-01 from SOL-001 (extend the existing activation workflow or run as a separate service) as an open decision. Do not resolve it.

## 3. Data Architecture

Identify and describe:

- Major business information concepts.
- Important data sources and information dependencies.
- Data ownership and stewardship considerations.
- Data movement across business and application boundaries.
- Data classification and sensitivity considerations.
- Data lineage, auditability and traceability requirements.
- Data retention and residency dependencies.
- Information exchanged with external systems.

Use the information handled in the blueprint (employee identity, compensation, tax withholding, banking, benefit, pay-code and organisational entity data) and the data the solution creates, as listed in SOL-001 section 8. Use DEP-001 to DEP-009 for dependencies. Explain how information supports capabilities, application responsibilities, operational decisions and governance.

Do not treat proposed sensitivity classifications as validated classifications. Do not name retention periods, jurisdictions or data residency rules (CON-005, OOS-017). Raise decision AD-02 from SOL-001 (which component holds batch working state, and which system remains the system of record for activated profiles). Do not resolve it. No historical payroll data flows are in scope (CON-007).

## 4. Technology and Infrastructure Architecture

Establish technology and infrastructure considerations without selecting technologies. Identify:

- Hosting and deployment considerations.
- Application execution and integration requirements.
- Infrastructure dependencies.
- Availability, resilience and scalability considerations, including processing of batches of hundreds or thousands of profiles.
- Asynchronous processing and recovery needs (CAP-022 to CAP-024, BR-008).
- AI service execution and access boundaries, if AI is adopted (DEC-014).
- Data residency and processing-location constraints.
- Operational monitoring and service continuity requirements.

Distinguish confirmed constraints from requirements that still need definition. Availability, recovery, performance and volume targets are gaps (G-04, G-10). Do not invent them.

Do not select or recommend specific cloud providers, infrastructure platforms, databases, programming frameworks, LLM providers or models, AI orchestration frameworks, middleware or integration products, event brokers, or container or deployment platforms. Technology selection is excluded under OOS-010, and DEC-022 makes the proposed stack a proposal. Do not adopt any element of the proposed stack. Raise adoption as decision AD-03 from SOL-001.

## 5. Integration Architecture

Identify and describe:

- Internal and external integration relationships.
- Systems or capabilities exchanging information.
- Integration purposes and business triggers.
- Major information exchanged.
- Dependencies between integration points.
- Criticality and operational implications.
- Integration risks and unresolved interface requirements.

Use the integration needs I-1 to I-9 in SOL-001 section 7 and the capability relationships in ARC-005. Pay particular attention to:

- Statutory validation requests and findings (I-1).
- Non-committing dry-run execution (I-2).
- Per-record activation commit without duplicate effects (I-3).
- Client source data intake (I-4).
- Pay-code catalogue and entity hierarchy reads (I-5, I-6).
- Verification or statutory-data providers (I-7).
- Hand-off to the first live payroll run, which remains a boundary (I-8, VSB-01, DEC-021).
- Measurement data sources (I-9, DEC-023).
- Approval authority and access (CAP-031, CAP-032, DEC-007).
- Activation history and evidence retention (CAP-029, DEC-008).

Do not invent APIs, endpoints, protocols, interface specifications or integration products. Where an interface is unknown, identify the dependency and record the information gap. A general-purpose integration platform is out of scope (OOS-014).

## 6. Security and Governance Architecture

Describe the security and governance principles that shape the architecture. Cover:

- Identity and access management for client users and internal roles.
- Least-privilege access, including role-based access to activation detail (CAP-033, BR-009).
- Human approval and accountability (CAP-031, CAP-032, AIB-008).
- AI governance and oversight.
- Data protection and privacy, including masking before any model call (AIB-005, AIB-006).
- Auditability and traceability, without claiming immutability (OOS-016).
- Untrusted input: uploaded batch files and AI suggestions are untrusted until validated by deterministic rules.
- AI contribution records (AIB-010).
- Resilience and manual fallback, so core activation works without AI (AIB-012, CON-006).
- Policy and business-rule precedence.
- Retention (CAP-034, DEC-008).
- Governance of any external providers (DEC-004).

Preserve the binding AI boundaries AIB-001 to AIB-012 and show their status as binding on approval. In particular:

- AI only suggests. People approve. Deterministic rules and the statutory engines decide validity (AIB-002).
- AI must not approve, activate or commit (AIB-007), and must not bypass validation, authorization or activation gates (AIB-004).
- AI must not determine statutory rules or calculate payroll results (AIB-011).
- AI must not decide entity or jurisdiction assignments (AI-005 is rejected).
- Model confidence is never proof of correctness (AIB-003).
- AI access is limited to what each suggestion needs (AIB-005).
- Every AI suggestion and the human decision on it is recorded (AIB-010).
- Ambiguity is surfaced, never silently resolved (AIB-009, BR-004).

Preserve the validation rule that an error isolates to the failing record. A bad record never blocks the whole batch, and corrected records are revalidated on their own (CON-003, BR-001, BR-002, BR-005).

Do not claim regulatory compliance. No statutory jurisdiction or regulation has been identified (DEC-001, OQ-002, CON-005). AIB-005 and AIB-006 remain pending security confirmation (PCR-013). Show that status.

## 7. Architecture Relationships and Dependencies

Explain how the six domains relate to one another. For each domain, document:

- Purpose.
- Major elements.
- Relationships with the other domains.
- Dependencies.
- Relevant constraints.
- Open decisions.
- Information gaps.
- Architecture risks.

Show traceability from capabilities to application responsibilities, data requirements, integrations, technology considerations and governance controls. Every significant architectural element needs a traceable business or operational justification. Use the epics and stories (PA-01 to PA-16), the capabilities (CAP-xxx), the objectives (BO-xxx) and the KPIs where they apply.

## 8. Required outputs

Produce the following:

1. Executive Architecture Overview.
2. Business Architecture View.
3. Application Architecture View.
4. Data Architecture View.
5. Technology and Infrastructure Architecture View.
6. Integration Architecture View.
7. Security and Governance Architecture View.
8. Cross-Domain Architecture Relationship Matrix.
9. Architecture Dependencies and Constraints Register.
10. Architecture Decisions and Information Gaps Register.

Where useful, include a high-level enterprise architecture diagram that shows how the guided activation solution fits into the payroll enterprise environment. Use Mermaid, and make it Mermaid 8.8.0 compatible. Keep the diagram at enterprise level. Show the solution boundary separately from external capabilities. Label assumed and unknown systems and interfaces as such. Make sure no assumed capability, product or interface looks confirmed. Keep names consistent with the written architecture and with docs/solution-architecture.svg and the Mermaid diagrams in tech-stack.md, which remain proposals.

## 9. Evidence and status classification

Preserve the evidence status of every significant statement:

- C, Confirmed: a recorded human decision or binding constraint, for example DEC-022 as decided, or an explicit scope exclusion.
- W, Working baseline: content in the Task 01 to Task 03 Part 1 artifacts or SOL-001. It is accepted for progression but is a proposal, not an approved or validated fact.
- A, Assumption: unvalidated, such as ASM-001 to ASM-014, or the assumptions A-01 to A-07 in OPS-009.
- G, Information gap: no supporting information exists in the baseline, such as G-01 to G-17 in SOL-001.
- D, Decision requiring approval: an open decision for an accountable human, such as the DEC items, Q-01 to Q-10, and AD-01 to AD-03.

Do not upgrade assumptions or working-baseline content to confirmed facts. Preserve existing identifiers. Any new local reference must be marked assessment-local and must not be presented as a repository ID. This includes XC-P01 to XC-P11.

## 10. Architecture constraints and safeguards

The architecture view must:

1. Respect the confirmed constraints CON-001 to CON-008 and the scope exclusions in BIZ-008, including no migration of historical payroll data (CON-007, OOS-001).
2. Keep confirmed, working, assumed, missing and approval-pending information distinct.
3. Avoid inventing enterprise systems, products, vendors, interfaces or technologies.
4. Avoid assuming that every capability needs a new application or service.
5. Avoid decomposing the architecture into detailed technical components. That belongs to Task 04.3.
6. Avoid resolving business, policy or governance decisions for accountable stakeholders. Present options where a decision is needed. Do not choose one. This applies in particular to DEC-006 (blocking policy), DEC-007 (permissions and approvals), DEC-001 (jurisdiction) and OQ-001 (sponsor and approval authority). Do not invent approval authority or escalation destinations.
7. Preserve the layer separation and traceability principles of Tasks 01 to 03.
8. Keep the architecture option-preserving where decisions remain open.
9. State the three target metrics (65 percent faster activation, 75 percent fewer support touchpoints per 1,000 activations, 99.8 percent first-time-right) as targets. Baselines are not agreed (DEC-005). Do not invent figures, client names or proprietary data.

## 11. Working status and execution boundaries

This is an architecture analysis and modelling activity only.

- Work read-only from the repository sources listed above.
- Do not modify any existing file. This includes Problem statement.md, the baseline artifacts BIZ, ARC and OPS, SOL-001, tech-stack.md, the epics, the backlog and the SVG.
- Do not apply any proposed change PCR-001 to PCR-013.
- Do not create repository identifiers other than the output artifact named below. Record any needed baseline change as a proposed change with a rationale, in the output document only.
- Do not generate application code.
- Do not write infrastructure, deployment or integration configuration.
- Do not select vendors, platforms, products or technology components.
- Do not claim formal human approval of any artifact.
- Do not open a pull request.

Write the output to one new file: docs/solution/SOL-002-enterprise-architecture-view.md. If the Mermaid CLI is available, you may render the diagram to check it. Keep rendered images and helper scripts in the session scratchpad, and install nothing. If a tool is blocked, report the limitation and do not work around it.

Use this document control block at the top of the file:

- Artifact: SOL-002
- Task: Task 04, activity 4.2 (Enterprise Architecture View)
- Version: 0.1
- Status: DRAFT. Working analysis. Ready for human review. Nothing has been approved.
- Approval record: None.

Title the output: Task 04.2, Enterprise Architecture View: Working Analysis.

Follow the repository writing style. Use professional, concise, active voice, with no emojis. Use plain prose and simple headings, and avoid bold and italics. Open with a short summary of one or two sentences, and order recommendations by priority, highest first.

Conclude with:

1. Key architectural findings.
2. Unresolved dependencies and decisions.
3. Information required from the client, the payroll provider and the statutory engine owners.
4. Risks that could affect the Solution Architecture Blueprint.
5. Recommendations for proceeding to Task 04.3, Solution Architecture Blueprint.
6. Validation notes: what you checked, what you did not check, and any limitation.

The final output must be evidence-based, traceable, internally consistent and suitable for human architecture review.
