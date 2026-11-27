# Task 04.3: Solution Architecture Blueprint

## Complete Working Analysis Prompt

### 1. Role and Context

Act as a Senior Enterprise and Solution Architect with expertise in:

- Enterprise and solution architecture
- AI-native application architecture
- Payroll and workforce-management systems
- Business process and batch orchestration
- Human-in-the-loop decision systems
- Data and integration architecture
- AI governance, security and operational resilience
- Architecture traceability and design governance

Your task is to develop Task 04.3, Solution Architecture Blueprint, for the Guided Payroll Activation solution. The solution improves bulk guided activation of employee profiles in a payroll management system during enterprise onboarding, tenant provisioning or organisational restructuring.

The blueprint must translate the Task 04.2 Enterprise Architecture View (SOL-002) into a coherent, technology-neutral logical solution architecture.

Work strictly from the existing Task 01 to Task 03 Part 1 working baseline and the Task 04.1 and Task 04.2 working analyses. Do not treat any working analysis as a formally approved architecture artifact.

### 2. Governance and Authorisation Boundary

Current status: Task 04 architecture learning and analysis activity. There is no separate authorisation record in this repository. The governing rules are CLAUDE.md, DEC-022 (the technology stack is a proposal, not a constraint), the scope exclusions in BIZ-008, and the boundaries in this prompt.

Before starting:

1. Read CLAUDE.md and README.md and follow them.
2. Confirm the repository, branch and git status.
3. Identify the permitted working scope below.
4. Inspect the baseline artifacts listed in section 3 and their provenance.
5. Identify any restriction that affects this activity, and report any conflict between the repository instructions and this prompt. Where they conflict, follow the higher-priority repository instruction.

Permitted scope: read the repository, and write one new file, docs/solution/SOL-003-solution-architecture-blueprint.md. Everything else is read-only.

Unless separate explicit authorisation is provided:

- Do not modify any existing file, including Problem statement.md, the BIZ, ARC and OPS artifacts, SOL-001, SOL-002, tech-stack.md, the backlog, the epics and the SVG.
- Do not create repository identifiers other than the output artifact SOL-003.
- Do not apply any proposed change (PCR-001 to PCR-016, EPC-01 to EPC-05). Record any needed baseline change as a proposed change, with a rationale, in the output document only.
- Do not write YAML specifications, architecture catalogues, decision records, configuration or code.
- Do not implement the architecture.
- Do not select technologies, vendors or products, or configure infrastructure.
- Do not claim that the blueprint, or any input, has been formally approved.
- Do not commit, push or open a pull request.

### 3. Authoritative Inputs

Use these sources as the architecture baseline.

Problem and business framing:

- Problem statement.md (the verified source for the problem, the five bottlenecks BN-01 to BN-05 and the three target metrics).
- Business Model Canvas to Business Architecture Blueprint.md.
- product-backlog.md and epic-01 to epic-06 (stories PA-01 to PA-16).

Task 01, business foundation (working baseline):

- BIZ-001 to BIZ-008 in docs/business, including constraints CON-001 to CON-008, risks RSK-001 to RSK-013, decisions DEC-001 to DEC-023, questions OQ-001 to OQ-012, AI opportunities AI-001 to AI-009 and AI boundary rules AIB-001 to AIB-012.

Task 02, business architecture (working baseline):

- ARC-001 to ARC-007 in docs/architecture: 38 capabilities, the value stream VS-01 to VS-06 with boundary VSB-01, traceability, proposed ownership, capability dependencies CD-001 to CD-021, business rules BR-001 to BR-009, and proposed changes PCR-001 to PCR-013.

Task 03 Part 1, operational model (draft, review pending):

- OPS-002 (processes PRC-01 to PRC-06, their steps and decision points, and the capability operations view), OPS-003 (exceptions EXC-01 to EXC-23) and OPS-009 (register, Q-01 to Q-10, A-01 to A-07, PCR-014 to PCR-016) in docs/operations.
- Task 03 Part 2 has not been run. There is no OPS-001 and no OPS-004 to OPS-008, so there is no approved state model, decision model, requirements catalogue or controls catalogue. Do not invent them. Where the blueprint needs them, record an information gap.

Task 04.1, Architecture Requirements Assessment (draft working analysis):

- docs/solution/SOL-001-architecture-requirements-assessment.md. Use it as the requirements and constraints analysis, including integrations I-1 to I-9, information gaps G-01 to G-17 and architecture decisions AD-01 to AD-03.

Task 04.2, Enterprise Architecture View (draft working analysis):

- docs/solution/SOL-002-enterprise-architecture-view.md. Use the complete document as the immediate input. It covers the executive overview; the business, application, data, technology and infrastructure, integration, and security and governance views; the cross-domain relationship matrix; the dependencies and constraints register; the decisions and information gaps register; findings, information required, risks and recommendations for Task 04.3.
- Do not rely only on its summary. Examine the detailed views, relationships, registers and conclusions, including its assessment-local references: application responsibilities AR-01 to AR-11, external capabilities XC-P01 to XC-P11, information concepts IC-01 to IC-16, technology considerations TC-01 to TC-10, integration relationships IX-01 to IX-03, security and governance principles SG-01 to SG-12, risks EAR-01 to EAR-08 and proposed changes EPC-01 to EPC-05.

Context only:

- tech-stack.md and docs/solution-architecture.svg describe a proposed physical stack. They are a proposal (DEC-022) and must not be used as a constraint or as a source of logical building blocks.

Where a source artifact and a working analysis differ, identify the discrepancy and preserve the source provenance. Do not silently reconcile differences.

### 4. Status Classification

Preserve the existing evidence classification throughout the blueprint.

| Code | Meaning |
| :-- | :-- |
| C | Confirmed: a recorded human decision or binding constraint, such as DEC-022 as decided or an explicit scope exclusion (OOS, CON) |
| W | Working baseline: content in the Task 01 to Task 03 Part 1 artifacts, SOL-001 or SOL-002, accepted for progression but proposed |
| A | Assumption: unvalidated, such as ASM-001 to ASM-014 or A-01 to A-07 |
| G | Information gap: no supporting information in the baseline, such as G-01 to G-17 |
| D | Decision requiring approval: DEC items, Q-01 to Q-10, AD-01 to AD-03 |

Apply these classifications to architecture statements, building blocks, relationships, integration points, security controls and design recommendations. The AI boundary rules AIB-001 to AIB-012 are working-baseline rules that are binding on approval; show them as "W, binding on approval". AIB-005 and AIB-006 remain pending security confirmation (PCR-013).

Do not promote W, A, G or D content to C.

Clearly distinguish:

- Existing baseline facts.
- Confirmed constraints.
- Proposed logical architecture.
- Assumptions.
- Unresolved decisions.
- Information gaps.
- Recommendations requiring human review.

The references from SOL-001 and SOL-002 (AR, XC-P, IC, TC, I, IX, SG, EAR, EPC, G, AD) are assessment-local, not repository IDs. Any new reference introduced in this analysis, for example LBB for logical building blocks, must be labelled assessment-local and must not be represented as a repository ID.

## 5. Task 04.3 Objectives

Develop a Solution Architecture Blueprint that answers the following questions:

1. How should the proposed guided activation solution be logically organised?
2. What are the major logical building blocks required to realise the application responsibilities AR-01 to AR-11?
3. What responsibilities belong to each logical building block?
4. How do the building blocks interact to support the value stream VS-01 to VS-06 and the revalidation loop?
5. How are business rules, AI assistance and human decision-making separated?
6. How does the solution coordinate with the external capabilities XC-P01 to XC-P11?
7. How does information flow between the logical building blocks?
8. Where are security, governance, audit and operational controls enforced?
9. How does the architecture handle an unavailable statutory engine, payroll management system, reference source or AI service?
10. Which architecture decisions and information gaps prevent the blueprint from being finalised?

The blueprint must provide enough logical detail for the next architecture activities without prematurely defining implementation components.

## 6. Required Architecture Design

### 6.1 Overall Logical Solution Architecture

Develop an overall logical architecture showing:

- The client user and source data boundary (payroll administrators, implementation specialists, client source systems XC-P05).
- The guided activation solution boundary.
- Logical application and orchestration responsibilities.
- Deterministic business rule and validation responsibilities.
- Optional AI-assisted responsibilities.
- Human review, approval and remediation responsibilities.
- Information, history and evidence management.
- The integration and external enterprise capability boundary.
- Security and governance controls.
- Audit and monitoring responsibilities.

Show how the solution sits between the client source data and the payroll environment.

Preserve the non-replacement constraints:

- XC-P02 payroll engine: not replaced; it calculates payroll (OOS-002).
- XC-P03 statutory engines: not replaced; AI must not determine statutory rules or calculate payroll results (AIB-011).
- XC-P06 client HR information system: not replaced (OOS-003).
- No migration of historical payroll data (CON-007, OOS-001).

The relationship with XC-P01, the payroll management system and its current activation wizard, depends on AD-01: the solution either extends the existing activation workflow inside XC-P01 or runs as a separate service that integrates with it. AD-01 is open. Model both options at logical level, show where they differ, and do not choose one.

Do not invent actual enterprise systems or claim that a modelled external capability is a confirmed implementation.

### 6.2 Logical Building Block Identification

Identify the logical building blocks required to realise AR-01 to AR-11. Use AR-01 to AR-11 as the primary traceability anchors, and trace through them to the capabilities in ARC-001 and the processes and steps in OPS-002.

For each proposed building block, provide:

| Attribute | Required description |
| :-- | :-- |
| Logical building block ID | Assessment-local reference |
| Building block name | Clear architecture-level name |
| Purpose | Why it exists |
| Responsibilities | What it does |
| Related AR IDs | AR-01 to AR-11 |
| Related business capabilities | CAP identifiers from ARC-001 |
| Related processes | PRC identifiers and steps from OPS-002 |
| Information handled | IC identifiers from SOL-002 |
| Interactions | Other logical building blocks and external capabilities (XC-P) |
| Controls | Relevant BR, AIB, SG and CON identifiers |
| Evidence status | C, W, A, G or D |
| Open decisions | Relevant DEC, Q, AD and G references |

Logical building blocks are architecture abstractions. Do not assume that:

- Every AR must become a separate application.
- Every logical building block requires a separate service.
- Every responsibility requires a separate microservice.
- A logical building block maps to a separate container.
- A logical building block maps to a particular database or technology product.

Where several AR responsibilities could reasonably be grouped, explain the rationale and preserve traceability to each AR. Where a responsibility may be supplied by an existing enterprise service or by XC-P01 (AD-01), record an unresolved placement decision rather than making the selection.

### 6.3 Logical Architecture Layers

Organise the solution into logical layers where useful. Treat the following as candidate groupings, not predetermined implementation layers:

1. Experience and interaction.
2. Batch intake and data preparation.
3. Mapping and context resolution.
4. Validation, rules and simulation coordination.
5. Optional AI-assisted suggestion and explanation.
6. Workflow and batch orchestration.
7. Human review, approval and remediation.
8. Information, history and evidence management.
9. Integration and external coordination.
10. Audit, monitoring and governance.

For each layer:

- Define its architectural purpose.
- Identify its logical responsibilities.
- Map the relevant AR responsibilities.
- Identify information dependencies.
- Identify interactions with other layers.
- Identify applicable security and governance controls.
- Explain whether the layer is a distinct responsibility or only a logical grouping.

Do not force all AR responsibilities into these layers if the evidence supports a different arrangement.

### 6.4 Business Workflow and Orchestration Architecture

Develop the logical workflow architecture using the existing value stream and processes:

VS-01 Prepare batch (PRC-01)
→ VS-02 Map and resolve (PRC-02)
→ VS-03 Validate and simulate (PRC-03)
→ VS-04 Process activation (PRC-04)
→ VS-05 Remediate exceptions (PRC-05), with corrected records returning to VS-03 on their own
→ VS-06 Review outcome (PRC-06)
→ VSB-01 Hand-off to the first live payroll, a boundary only (DEC-021)

Include the alternative outcomes:

- Record isolated and routed to remediation (EXC-12).
- Record left unresolved and visible (EXC-16, EXC-21).
- Batch stopped for a condition that requires it (EXC-13).
- Batch abandoned or not resumed (EXC-20, DEC-011).
- Activation not approved (EXC-19).

Explain:

- How the workflow coordinates the logical building blocks.
- How batch and record state and status are maintained, noting that no approved state model exists yet (Task 03 Part 2).
- How work is routed to administrators, specialists and reviewers.
- How exceptions are managed (OPS-003).
- How approvals and authority checks are enforced at the reserved human decisions in OPS-002.
- How integration dependencies affect workflow progression.
- How the solution prevents activation of a record before the required checks and approvals (BR-001, BR-003, CON-002), and keeps one failing record from blocking the batch (CON-003, BR-002).

Explicitly preserve the unresolved decisions:

- DEC-006: blocking, review and informational issue policy, and batch-stop conditions.
- DEC-007: approval authority for mappings, activation, sensitive changes and bulk fixes (Q-01).
- DEC-016 and Q-06: what the dry run reproduces, and whether it is a required gate.
- DEC-017: retry and recovery behaviour.
- DEC-011 and Q-02: resuming or abandoning a batch.
- DEC-021 and Q-04: the hand-off to the first live payroll.

Do not invent workflow branches or final authority assignments where the baseline is unresolved.

### 6.5 Deterministic Rules and AI-Assisted Architecture

Define the separation between deterministic processing and AI-assisted functions.

Deterministic responsibilities, using the relevant baseline capabilities and steps:

- Input inspection and structural checks.
- Deterministic field and pay-code mapping of recognised values.
- Entity hierarchy resolution and jurisdiction assignment from authoritative sources.
- Validation of data, configuration, compensation, tax and withholding, benefits and banking details.
- Issue severity classification and record eligibility.
- Dry-run coordination.
- Approval authority enforcement.
- Per-record activation, isolation and recovery without duplicate effects.
- Revalidation of corrected records only.
- Access, retention and audit recording.
- Status management.

AI-assisted responsibilities. Use only the accepted AI opportunities:

- AI-001: field-mapping suggestions.
- AI-002: pay-code mapping suggestions.
- AI-003: plain-language explanation of validation messages.
- AI-004: drafting corrective suggestions for exceptions.

The rejected AI uses AI-005 to AI-009 (entity or jurisdiction determination, validity or blocking decisions, payroll simulation or calculation, approval or activation, autonomous bulk fixes) must not appear as AI responsibilities.

For each AI-assisted responsibility, define:

1. Purpose.
2. Input information, with sensitive values masked (AIB-006).
3. Expected advisory output.
4. Receiving logical building block.
5. Human review requirement.
6. Relevant AI governance controls.
7. Audit information required (AIB-010).
8. Fallback behaviour when AI is unavailable (AIB-012).

Preserve the binding AI constraints AIB-001 to AIB-012, in particular:

- AIB-002: AI only suggests; people approve; deterministic rules and the statutory engines decide validity.
- AIB-003: model confidence is never proof of correctness; it may only order or route items for review.
- AIB-004: AI output must not bypass statutory rules, policies, validation, authorization or activation gates.
- AIB-005: AI receives no unrestricted access to payroll systems or personal data.
- AIB-006: sensitive values are masked before any model call.
- AIB-007: approval and activation stay within controlled workflows; AI cannot approve, activate or commit.
- AIB-010: every AI suggestion and the human decision on it are recorded.
- AIB-011: AI must not determine statutory rules or calculate payroll results.
- AIB-012: core guided activation works without AI.

Whether AI is used at all in the first release is open (DEC-014). Do not introduce additional AI autonomy or decision-making authority.

### 6.6 Information and Data Architecture

Use IC-01 to IC-16 from SOL-002 section 4, and the information handled in the blueprint, as the information baseline.

Explain:

- Which logical building blocks create information.
- Which building blocks consume information.
- Where batch working state (mappings, findings, remediation items) is provisionally held before commit, and which system remains the system of record for activated profiles. This depends on AD-02, which is open; show the options.
- How mapped and corrected values retain their source linkage and effective-value source.
- How findings and evidence are assembled for human review.
- How decisions, approvals and AI contributions are recorded.
- How information is exchanged with external capabilities.
- How information is made available for outcome measurement (CAP-030, provisional pending DEC-023) and governance.

Include a logical information flow matrix:

| Information ID | Information concept | Producing responsibility | Consuming responsibility | External relationship | Relevant controls | Status |

Treat data classifications as unvalidated.

Do not invent physical database structures, table definitions, schemas, storage products, retention periods, residency decisions, encryption implementations or data ownership assignments.

Explicitly carry forward:

- DEC-008: recorded events, visibility, retention and export.
- DEC-001: jurisdiction, which drives residency and statutory scope.
- AD-02: working state and system of record.
- The relevant data gaps in SOL-001 section 11 and SOL-002 section 10.

### 6.7 Integration and External Coordination Architecture

Use the integration relationships in SOL-001 section 7 and SOL-002 section 6.

The blueprint must cover:

1. I-1: validation with the statutory engines (XC-P03).
2. I-2: non-committing dry run with the statutory engines (XC-P03).
3. I-3: per-record activation commit with the payroll management system or payroll data model (XC-P01, XC-P04).
4. I-4: client source data intake (XC-P05).
5. I-5: pay-code catalogue (XC-P07).
6. I-6: entity hierarchy source (XC-P08).
7. I-7: verification or statutory-data providers (XC-P09), which may not exist (DEC-004).
8. I-8: hand-off to the first live payroll (XC-P01, XC-P02), a boundary pending DEC-021.
9. I-9: measurement data sources, pending DEC-023.
10. IX-01: approval authority.
11. IX-02: identity provider for client users (XC-P10).
12. IX-03: enterprise record-keeping or audit facility.

For each relationship, describe:

- Business purpose.
- Triggering process, step or event.
- Information exchanged.
- Sending logical responsibility.
- Receiving external capability.
- Criticality.
- Required response behaviour.
- Failure and unavailability handling.
- Relevant security and governance controls.
- Unresolved dependencies and decisions.

Do not invent APIs, endpoints, message brokers, protocols, interface formats, authentication products or vendor-specific integration patterns. Treat every external capability as modelled, with its actual implementation and interfaces A or G unless verified by an authoritative source.

Explicitly address:

- Statutory engine unavailable or a rule cannot be evaluated: report a limitation, never a pass (EXC-09).
- Dry run partial or unavailable: show its limitations; whether activation may proceed depends on DEC-006 and DEC-016.
- Activation commit: once per eligible record, with no duplicate effects (BR-008), and only through the deterministic, approved workflow.
- Commit failure for one record: isolate it, do not block others (EXC-12).
- External system writes: no direct AI write path to XC-P01, XC-P02, XC-P03 or XC-P04 (AIB-005, AIB-007).
- Source data and AI output: untrusted until deterministic checks pass (SG-08).

Also identify integration gaps not modelled in SOL-001 or SOL-002, such as user notifications when a batch needs attention, the route for a suspected fraud or risk indicator (EXC-22, Q-09), the dispute route (EXC-23, Q-10) and exception escalation routes. Do not add them as confirmed integrations.

### 6.8 Security, Governance and Audit Architecture

Translate SG-01 to SG-12 and the relevant baseline rules into logical enforcement points.

For each control, explain:

- The logical building block responsible for enforcement.
- The interaction or workflow point where it applies.
- The evidence or audit record produced.
- The related baseline rule or constraint (BR, AIB, CON, SG).
- The evidence status.

Cover:

- Identity and access management (SG-01, IX-02).
- Least-privilege access to activation detail (SG-02, BR-009, CAP-033).
- AI execution boundaries (SG-04, SG-05, AIB-002 to AIB-005, AIB-011).
- Human decision accountability (SG-03, AIB-008).
- Deterministic, approved activation (AIB-007, BR-001, BR-003).
- Rule and policy precedence over AI output (AIB-004).
- AI unavailability and manual fallback (SG-11, AIB-012).
- Untrusted input (SG-08).
- Masking of sensitive values before model calls (SG-06, AIB-006, pending confirmation).
- Ambiguity surfaced, never guessed (SG-07, BR-004).
- Record isolation as a governance control (CON-003, BR-002).
- Decision and change auditability (SG-10, CAP-029).
- AI contribution traceability (SG-09, AIB-010).
- Records retention (SG-12, CAP-034, DEC-008).
- External provider governance (SG-12).

Distinguish:

1. Confirmed governance constraints.
2. Proposed logical enforcement mechanisms.
3. Existing enterprise services that are not yet verified (XC-P10, XC-P11).
4. Decisions and information gaps requiring resolution.

Do not claim regulatory or statutory compliance. The jurisdiction and applicable obligations remain unresolved (DEC-001, OQ-002, CON-005).

### 6.9 Operational Resilience and Failure Handling

Develop a logical failure-handling model. At a minimum, consider:

- Statutory engine unavailable, or a rule cannot be evaluated.
- Dry run unavailable or only partially representative.
- Payroll management system commit unavailable, or a commit partly completes.
- Client source input unreadable or structurally unusable.
- Pay-code catalogue or entity hierarchy source unavailable.
- AI service unavailable.
- AI output invalid, uncertain or conflicting.
- Business rule evaluation failure.
- Approval authority unavailable or undefined.
- Processing interrupted part-way through a batch (PA-11).
- A condition requiring the whole batch to stop.
- Audit or history recording failure.

For each scenario, specify:

| Scenario | Affected capability | Required solution behaviour | Human involvement | Batch and record status | Recovery consideration | Baseline reference |

Preserve the binding principle that controls must never be skipped to maintain throughput.

Do not invent availability percentages, recovery time objectives, retry policies, error-rate thresholds (CON-008) or service-level targets. Carry forward DEC-017 and the volume and service gaps in SOL-001.

## 7. Required Visual Architecture Views

Produce the following diagrams using Mermaid, compatible with Mermaid 8.8.0. All diagrams must be consistent with the text.

Diagram 1, Overall Logical Solution Architecture. Show actors, the experience boundary, logical layers, workflow and orchestration, deterministic rules, optional AI assistance, human decision responsibilities, information and audit responsibilities, the integration boundary, the external capabilities XC-P01 to XC-P11, and cross-cutting security and governance. Show both AD-01 options, or mark the XC-P01 boundary as open.

Diagram 2, Logical Building Block Architecture. Show the proposed logical building blocks and their relationships, each mapped to its AR identifiers. Do not show each AR as a separate technical component unless the evidence supports it.

Diagram 3, Business Workflow and Decision Architecture. Show VS-01 to VS-06, the revalidation loop, the alternative outcomes and the VSB-01 boundary. Distinguish deterministic processing, optional AI advice, human review and approval, statutory engine dependencies and controlled per-record activation.

Diagram 4, AI and Deterministic Processing Boundary. Show untrusted source data, input checks, masking, optional AI suggestion, advisory output, deterministic rules and statutory validation, human review, workflow progression, audit recording and manual fallback. Make it visually impossible to read AI as having final decision, validation or activation authority.

Diagram 5, Information and Data Flow Architecture. Show the principal information concepts (IC identifiers) and their movement across logical building blocks. Show no physical data stores or database products.

Diagram 6, Enterprise Integration Architecture. Show I-1 to I-9 and IX-01 to IX-03 with their references. Distinguish confirmed constraints from assumed or unverified external capabilities.

Diagram 7, Security and Governance Enforcement Architecture. Show the cross-cutting controls and the logical points where they are enforced, with the relevant AIB and SG references.

Diagram 8, Operational Resilience and Failure Handling. Show how the solution responds to statutory engine and commit failures, AI unavailability, invalid results, interruption, batch-stop conditions and other material failures.

Keep diagrams readable. If one becomes too complex, split it into logical views rather than omitting important relationships. If the Mermaid CLI is available, render the diagrams to check them; keep rendered images and helper scripts in the session scratchpad, and install nothing beyond what npx fetches for that check.

## 8. Architecture Traceability

Provide a consolidated traceability matrix, at a minimum:

| Business capability (CAP) | Process and step (PRC) | Application responsibility (AR) | Logical building block | Information (IC) | Integration (I, IX) | Governance control | Status |

Ensure that AR-01 to AR-11 and every Level 2 and Level 3 capability in ARC-001 are covered.

Also provide an AI constraint enforcement matrix:

| AIB ID | Binding constraint | Architecture enforcement point | Logical building block | Evidence or audit record | Status |

Cover AIB-001 to AIB-012. The purpose is to show that the logical architecture is grounded in the baseline rather than invented independently. Where a relationship cannot be established from the sources, mark it as an information gap.

## 9. Architecture Decisions and Design Variations

Carry forward the open decisions. At a minimum:

- AD-01: extend the activation workflow inside XC-P01, or run as a separate service.
- AD-02: where batch working state is held, and the system of record for activated profiles.
- AD-03: whether any element of the proposed stack is adopted as a starting point.
- DEC-001: first-release jurisdiction.
- DEC-003 and DEC-009: delivery surface and input methods.
- DEC-006: blocking policy and batch-stop conditions.
- DEC-007: authorization and approval model.
- DEC-008: audit events, visibility and retention.
- DEC-011: resuming or abandoning a batch.
- DEC-014: deterministic, AI-assisted or combined mapping.
- DEC-015 and DEC-016: authoritative statutory engine, and what the dry run reproduces.
- DEC-017: retry and recovery behaviour.
- DEC-021: hand-off to the first live payroll.
- DEC-023: outcome measurement against the targets.
- PCR-010: acceptance of CAP-008 and CAP-009 as capabilities.
- Q-01 to Q-10 from OPS-009.

For each decision, explain:

1. What architectural aspect it affects.
2. Which logical building blocks are affected.
3. Which design alternatives must remain open.
4. What information is required to resolve it.
5. Whether it blocks further logical design or only final implementation.

Do not make the decisions on behalf of the payroll provider, the client or the architecture authority. Identify architecture variation points so that the blueprint can accommodate future decisions without unnecessary redesign.

## 10. Technology-Neutrality Requirements

DEC-022 makes the technology stack a proposal, and AD-03 is open. The blueprint must remain logical and technology-neutral. The Google Cloud stack in tech-stack.md and docs/solution-architecture.svg must not be used as the basis of the blueprint.

Do not select or recommend specific:

- Cloud providers or hosting platforms.
- Databases or query languages.
- Programming languages or application frameworks.
- Large language models or AI model providers.
- AI agent frameworks.
- API gateways, message brokers or integration middleware.
- Workflow or orchestration products.
- Container platforms or Kubernetes distributions.
- CI/CD, monitoring or security products.
- Vendor-specific architecture patterns.

You may describe technology capabilities generically where necessary to explain the architecture, for example a logical integration responsibility rather than a gateway or broker. Do not turn logical building blocks into microservices, containers, agents or deployable units.

## 11. Quality and Consistency Review

Before presenting the blueprint, perform a structured architecture review.

Business alignment:

- Does the architecture realise the capabilities in ARC-001?
- Does it support VS-01 to VS-06, the revalidation loop and the VSB-01 boundary?
- Are human responsibilities and reserved decisions preserved?
- Are the scope exclusions respected?

Application architecture:

- Are AR-01 to AR-11 all represented?
- Are logical responsibilities clear?
- Are placement decisions (AD-01, shared services) still open?
- Have unnecessary components been introduced?

Data architecture:

- Are IC-01 to IC-16 traceable?
- Are source linkage and AI contribution records preserved?
- Are data ownership, classification, retention and residency gaps visible?

Integration architecture:

- Are I-1 to I-9 and IX-01 to IX-03 all covered, with correct references?
- Are external capability assumptions visible?
- Are failure and unavailability behaviours addressed?

Security and governance:

- Are AIB-001 to AIB-012 enforced?
- Is there any accidental AI decision, validation or write authority?
- Are human approval and accountability preserved?
- Are audit gaps identified?

Operational architecture:

- Are the failure scenarios addressed?
- Is manual operation without AI preserved?
- Have unsupported service-level targets been avoided?

Architecture governance:

- Are the C, W, A, G and D statuses maintained?
- Are open decisions preserved?
- Is the architecture technology-neutral?
- Has any file other than SOL-003 been changed?

Report inconsistencies, unsupported relationships and unresolved issues. Do not silently correct them.

## 12. Required Deliverable Structure

Write the output to docs/solution/SOL-003-solution-architecture-blueprint.md, titled "Task 04.3, Solution Architecture Blueprint: Working Analysis", with this document control block at the top:

- Artifact: SOL-003
- Task: Task 04, activity 4.3 (Solution Architecture Blueprint)
- Version: 0.1
- Status: DRAFT. Working analysis. Ready for human review. Nothing has been approved.
- Approval record: None.

Present the analysis in this order:

1. Executive Summary.
2. Architecture Scope, Inputs and Governance Status.
3. Architecture Principles and Binding Constraints.
4. Overall Logical Solution Architecture.
5. Logical Building Block Catalogue.
6. Logical Architecture Layer View.
7. Business Workflow and Orchestration Architecture.
8. Deterministic Rules and AI-Assisted Architecture.
9. Information and Data Flow Architecture.
10. Enterprise Integration and Coordination Architecture.
11. Security, Governance and Audit Architecture.
12. Operational Resilience and Failure Handling.
13. Architecture Diagrams.
14. Business-to-Solution Traceability Matrix.
15. AI Constraint Enforcement Matrix.
16. Architecture Decisions and Variation Points.
17. Dependencies, Assumptions and Information Gaps.
18. Architecture Quality and Consistency Review.
19. Key Findings and Recommendations.
20. Handover to Task 04.4.

For each section, distinguish existing baseline evidence from proposed architecture interpretation.

Follow the repository writing style: professional, concise, active voice, no emojis, plain prose with simple headings, no bold or italics. Open with a summary of one or two sentences, and order recommendations by priority, highest first. State the three target metrics (65 percent faster activation, 75 percent fewer support touchpoints per 1,000 activations, 99.8 percent first-time-right) only as targets; baselines are not agreed (DEC-005). Do not invent figures, client names or proprietary data.

## 13. Handover to Task 04.4

Conclude with a structured handover identifying:

- What Task 04.3 has established.
- What remains unresolved.
- Which logical building blocks require further refinement.
- Which information gaps block progression.
- Which decisions require human approval.
- Which architecture relationships require validation.
- What should be carried forward into Task 04.4.

The Task 4 learning guide (docs/learning/Task4_part4_Enterprise_and_Solution_Architecture_Learning_Guide.docx.md, section 6) names activity 4.4 Integration Architecture, with the expected output of an Integration Architecture View and integration inventory. Use only what that guide states about it, and do not invent its scope or activities beyond that.

## 14. Final Output and Governance Statement

End the analysis with:

Task 04.3, Solution Architecture Blueprint

- Status: Working architecture analysis.
- Authorisation: Task 04 working analysis under CLAUDE.md and DEC-022; no separate authorisation record exists.
- Formal human approval: Not obtained.
- Technology selection: None.
- Vendor selection: None.
- Physical deployment architecture: Not defined.
- Implementation: Not performed.
- Repository modifications: One new file, SOL-003. No existing file changed.
- Outstanding decisions and information gaps: Explicitly identified.

The final output must be a coherent, traceable and technology-neutral logical solution architecture.

The central design principle is:

Business Capability → Application Responsibility → Logical Building Block → Information Flow → Integration Relationship → Governance Enforcement → Operational Assurance

Preserve the working baseline, maintain evidence integrity, and keep every unresolved decision visible. Do not sacrifice governance, traceability or accuracy to make the architecture appear more complete than the evidence permits.

Complete the analysis, present SOL-003 and the validation evidence, and STOP. Wait for explicit human approval before Task 04.4.
