# Task 04.4: Integration Architecture

## Complete Working Analysis Prompt

### 1. Role and Context

Act as a Senior Enterprise Integration Architect with expertise in:

- Enterprise and solution architecture
- Solution integration and information exchange
- Payroll and workforce-management systems
- Batch orchestration and per-record commit coordination
- Human-in-the-loop decision systems
- Security, data protection and AI governance
- Architecture traceability and design governance

Your task is to develop Task 04.4, Integration Architecture, for the Guided Payroll Activation solution. The solution improves bulk guided activation of employee profiles in a payroll management system during enterprise onboarding, tenant provisioning or organisational restructuring.

The Task 4 learning guide defines activity 4.4 as: identify source and destination systems, information exchanged, triggers, communication patterns and failure-handling needs, and distinguish confirmed integration facts from proposed design choices. Expected output: an Integration Architecture View and integration inventory.

This activity refines the integration dimension of the Task 04.3 Solution Architecture Blueprint (SOL-003). It must not silently redesign SOL-003. Work strictly from the Task 01 to Task 03 Part 1 working baseline and the Task 04.1 to Task 04.3 working analyses. Do not treat any working analysis as formally approved.

### 2. Governance and Authorisation Boundary

Current status: Task 04 architecture learning and analysis activity. There is no separate authorisation record in this repository. The governing rules are CLAUDE.md, DEC-022 (the technology stack is a proposal, not a constraint), the scope exclusions in BIZ-008, and the boundaries in this prompt.

Before starting:

1. Read CLAUDE.md and README.md and follow them.
2. Confirm the repository, branch and git status.
3. Identify the permitted working scope below.
4. Inspect the baseline artifacts listed in section 3 and their provenance.
5. Report any conflict between the repository instructions and this prompt. Where they conflict, follow the higher-priority repository instruction.

Permitted scope: read the repository, and write one new file, docs/solution/SOL-004-integration-architecture.md. Everything else is read-only.

Unless separate explicit authorisation is provided:

- Do not modify any existing file, including Problem statement.md, the BIZ, ARC and OPS artifacts, SOL-001 to SOL-003, tech-stack.md, the backlog, the epics and the SVG.
- Do not create repository identifiers other than the output artifact SOL-004.
- Do not apply any proposed change (PCR-001 to PCR-016, EPC-01 to EPC-05, SPC-01 to SPC-06). Record any needed change as a proposed change, with a rationale, in the output document only.
- Do not write YAML, catalogues, decision records, interface specifications, configuration or code.
- Do not select technologies, vendors, products, platforms, protocols, API styles, message brokers, middleware, gateways, workflow products, databases, hosting or deployment patterns.
- Do not convert logical integration responsibilities into physical interfaces or implementation designs.
- Do not claim that the analysis, or any input, has been formally approved.
- Do not commit, push or open a pull request.

### 3. Authoritative Inputs

Use these sources, in order of authority:

1. Repository governance: CLAUDE.md, README.md and DEC-022.
2. Problem and business framing: Problem statement.md (verified source for BN-01 to BN-05 and the three target metrics), the Business Model Canvas blueprint, product-backlog.md and epic-01 to epic-06 (PA-01 to PA-16).
3. Task 01 working baseline: BIZ-001 to BIZ-008, including CON-001 to CON-008, OOS items, RSK-001 to RSK-013, DEC-001 to DEC-023, DEP-001 to DEP-009, ASM-001 to ASM-014, OQ-001 to OQ-012, AI-001 to AI-009 and AIB-001 to AIB-012.
4. Task 02 working baseline: ARC-001 to ARC-007, including CAP-001 to CAP-038, VS-01 to VS-06 with VSB-01, CD-001 to CD-021, BR-001 to BR-009 and PCR-001 to PCR-013.
5. Task 03 Part 1 (draft, review pending): OPS-002 (PRC-01 to PRC-06, steps and decision points), OPS-003 (EXC-01 to EXC-23) and OPS-009 (Q-01 to Q-10, A-01 to A-07, PCR-014 to PCR-016). Task 03 Part 2 has not been run, so there is no state model, decision model, requirements catalogue or controls catalogue (G-16). Do not invent them.
6. Task 04.1: SOL-001, including I-1 to I-9, G-01 to G-17 and AD-01 to AD-03.
7. Task 04.2: SOL-002, including AR-01 to AR-11, XC-P01 to XC-P11, IC-01 to IC-16, IX-01 to IX-03, SG-01 to SG-12, EAR-01 to EAR-08 and EPC-01 to EPC-05.
8. Task 04.3: SOL-003 as the immediate input, in full. Use its LBB-01 to LBB-16 catalogue, section 9.2 information flow matrix, section 10 integration table, section 11 control table, section 12 failure scenarios FS-01 to FS-14, Diagram 6, section 16 variation points VP-01 to VP-12, SAF-01 to SAF-12, SPC-01 to SPC-06 and the section 20 handover.

Context only: tech-stack.md and docs/solution-architecture.svg describe a proposed physical stack (DEC-022). Do not use them as a constraint or as evidence of any interface, protocol or pattern.

Where a source artifact and a working analysis differ, report the discrepancy and preserve provenance. Do not silently reconcile differences.

### 4. Status Classification

| Code | Meaning |
| :-- | :-- |
| C | Confirmed: a recorded human decision or binding constraint, such as DEC-022 as decided or an explicit scope exclusion (OOS, CON) |
| W | Working baseline: content in the Task 01 to Task 03 Part 1 artifacts or SOL-001 to SOL-003, accepted for progression but proposed |
| A | Assumption: unvalidated, such as ASM-001 to ASM-014 or A-01 to A-07 |
| G | Information gap: no supporting information, such as G-01 to G-17 |
| D | Decision requiring approval: DEC items, Q-01 to Q-10, AD-01 to AD-03 |
| P | Proposed interpretation introduced in this analysis; local only and never promoted to W or C |

Classify every material integration statement and cite the source identifier. If no source supports a detail, label it G or P and say why. Never promote A, G, D or P to W or C. Show AIB-001 to AIB-012 as "W, binding on approval"; AIB-005 and AIB-006 remain pending security confirmation (PCR-013).

The references from SOL-001 to SOL-003 (I, IX, XC-P, AR, IC, SG, EAR, EPC, G, AD, LBB, LL, VP, FS, SAF, SPC) are assessment-local, not repository IDs. Any new reference introduced here must be labelled assessment-local.

### 5. Integration Scope: Preserve Exact Identifiers

Analyse these twelve relationships from SOL-003 section 10. Do not renumber, merge or redefine them. All pass through LBB-16 Integration coordination.

| Ref | Source → destination | Purpose | Information | Status cautions |
| :-- | :-- | :-- | :-- | :-- |
| I-1 | LBB-05 → XC-P03 | Statutory and configuration validation | Candidate data out; findings back (IC-01 to IC-05, IC-11) | Critical (CON-002); XC-P03 not replaced C; engine identity and authority G-02, DEC-015 |
| I-2 | LBB-05 → XC-P03 | Non-committing dry run | Candidates out; results and limitations back (IC-11) | No live effect BR-006; dry-run support A (ASM-006); scope D (DEC-016) |
| I-3 | LBB-07 → XC-P01 or XC-P04 | Per-record activation commit | Eligible profile out; outcome back (IC-12) | Only write to system of record; safe repeat G-01; system of record D (AD-02) |
| I-4 | XC-P05 → LBB-02 | Source data intake | External payroll exports (IC-01 to IC-07) | Untrusted input SG-08; source A (ASM-004); input methods D (DEC-009), G-05 |
| I-5 | XC-P07 → LBB-03 | Pay-code catalogue | Pay-code reference (IC-06) | A (ASM-010), G-11 |
| I-6 | XC-P08 → LBB-03 | Entity hierarchy | Parent-child structure (IC-07) | A (ASM-005), DEC-013, G-11 |
| I-7 | LBB-05 → XC-P09 | Verification or statutory-data providers | Banking or statutory data (IC-04) | Provider may not exist G-12; governance D (DEC-004) |
| I-8 | XC-P01 → XC-P02 | Hand-off to first live payroll | Activated cohort | Boundary only; XC-P02 not redesigned OOS-002; in scope D (DEC-021, Q-04) |
| I-9 | Measurement sources → LBB-15 | Outcome measurement | Operational and support data (IC-16) | Only if DEC-023 includes it; baselines not agreed DEC-005 |
| IX-01 | LBB-09 → approval authority | Approval authority | Decision and deciding person (IC-14) | Authority model D (DEC-007, Q-01); G-07 |
| IX-02 | XC-P10 → LBB-10 | Identity provider | Identity and role attributes | G-13 |
| IX-03 | LBB-14 → record-keeping facility | Record-keeping or audit | IC-15 | Facility may not exist; scope and retention D (DEC-008), G-09 |

External capability status: XC-P01 to XC-P11 are modelled capabilities, not verified systems. Existence and interfaces remain A or G unless a source confirms otherwise. Preserve the non-replacement and non-redesign constraints for XC-P02, XC-P03 and XC-P06 (OOS-002, OOS-003). Do not invent system names, owners, endpoints, providers, APIs, payloads or protocols.

Also examine, without creating new relationship IDs:

- The unmodelled routes in SAF-12: user notification when a batch needs attention, suspected fraud or risk indicators (EXC-22, Q-09), disputes (EXC-23, Q-10) and unresolved tax-finding escalation (Q-03). Record each as a gap.
- Whether XC-P06 Client HRIS is a direct source.
- Whether XC-P11 (data protection, security and AI governance) needs an integration relationship for masking policy and AI governance (SG-12, G-15).
- Whether the optional AI suggestion function (LBB-12, reached only through LBB-11) depends on an external model provider, and what governance that requires (SG-12, DEC-014). No relationship from LBB-12 to any XC-P may be introduced.

### 6. Binding Rules to Preserve

- AI only suggests. It never validates, approves, activates or commits (AIB-002, AIB-004, AIB-007, AIB-011). There is no AI path to XC-P01, XC-P02, XC-P03 or XC-P04.
- Activation happens only through LBB-07, one record at a time, after LBB-04 eligibility and LBB-09 approval (BR-001, BR-003, BR-008).
- A failing record is isolated; other records continue (CON-003, BR-002). Corrected records are revalidated on their own (BR-005).
- Source data and AI output are untrusted until deterministic checks pass (SG-08).
- A check that cannot be evaluated is a visible limitation, never a pass (EXC-09).
- An unavailable external capability pauses or holds the affected work. Controls are never skipped to keep throughput.
- AI unavailability triggers the manual path; no stage waits on AI (CON-006, AIB-012).
- Activation history in LBB-14 is not described as immutable (OOS-016). Retention periods are not invented (OOS-017, DEC-008).
- No historical payroll data moves in any direction (CON-007, OOS-001).
- No jurisdiction or regulatory compliance is assumed or claimed (CON-005, DEC-001, OQ-002).
- No fixed error-rate threshold is set without policy (CON-008).
- Both AD-01 placement options stay open. Show where an integration differs between option A (extend XC-P01) and option B (separate service).

### 7. Required Analysis

A. Integration context

- Define the solution boundary (LBB-01 to LBB-16), the payroll provider environment, enterprise functions, client sources and external providers, as in SOL-003 section 4.2.
- Identify each LBB integration point and the corresponding XC-P capability.
- State that a logical relationship does not prove a deployed interface exists.

B. Integration inventory. For each of the twelve relationships record:

1. Reference and status.
2. Business purpose, with CAP and VS context.
3. Source and destination, with direction as supported.
4. Trigger: PRC step or decision point that initiates it; otherwise G.
5. Information exchanged, using IC identifiers; distinguish named concepts from unnamed ones.
6. Logical interaction: request and result, read of reference data, commit and outcome, authority check, identity assertion, evidence recording, measurement intake or boundary hand-off.
7. Expected outcome and downstream consumer.
8. Controls: BR, SG, AIB, CON and OOS references, access and human approval.
9. Security, privacy, access and audit considerations.
10. Supported failure behaviour, citing FS and EXC.
11. Missing failure details and non-functional needs, listed as gaps.
12. Dependencies, assumptions, decisions and validation actions.
13. Difference between AD-01 option A and option B, if any.

Do not fabricate payload fields, endpoints, protocol, timing, frequency, volume, retry, timeout, ordering or idempotency mechanisms.

C. Relationship-specific review. At minimum address:

- I-1: findings per record and field; engine unavailable or rule not evaluable produces a limitation and the record is not eligible (FS-01, EXC-09). Engine identity G-02.
- I-2: no live effect (BR-006); partial or unavailable dry run shows limitations; whether activation may proceed is D (FS-02, DEC-006, DEC-016, Q-06, Q-07). Note SAF-09.
- I-3: once per eligible record; one record fails, isolate (FS-05, EXC-12); unavailable, pause (FS-03); unknown outcome, hold for safe-retry check (FS-04, EXC-14, PRC-04 D3). Safe repeat and recovery owner are gaps (G-01, DEC-017, Q-05). Interrupted processing (FS-12) and resume or abandon (DEC-011, Q-02).
- I-4: treat as untrusted; unreadable input gives a file-level reason (FS-06, EXC-01).
- I-5 and I-6: authoritative reads; unavailable source leaves mappings and assignments unresolved and visible, never guessed (FS-07, EXC-03, EXC-04, BR-004). AI-005 inference of hierarchy stays rejected.
- I-7: used only if a provider exists and is governed (SG-12, DEC-004); otherwise a limitation.
- I-8: boundary only; not designed (OOS-002, DEC-021).
- I-9: optional; unavailability does not affect activation (DEC-023).
- IX-01: no default approval; decision waits when authority is unavailable or undefined (FS-11, EXC-18, EXC-19). Do not assume an approval matrix, delegation or separation-of-duties rule (DEC-007, Q-01).
- IX-02: no access without authentication; no anonymous path. Do not assume the identity source or role model (G-13, G-14).
- IX-03: evidence recording; FS-14 and SAF-08 propose holding an action whose evidence cannot be recorded, which the baseline does not confirm (SPC-05). Keep LBB-14 activation history separate from any enterprise record-keeping and retention capability.

D. Logical communication patterns

Describe only the interaction category the baseline supports. Do not select synchronous or asynchronous, API, event, batch, queue, file transfer or any other technical style. Where the course task asks for a communication pattern that the baseline does not specify, record it as a gap or decision and state what evidence is needed and from whom. Note that "asynchronous processing" in CAP-022 and epic-04 describes the user experience of batch processing, not an integration protocol.

E. Failure and operational handling

Cover each case below and distinguish C or W behaviour from P behaviour and unknowns: statutory engine unavailable; dry run partial or unavailable; commit unavailable; commit outcome unknown or partial; single-record commit failure; processing interrupted; source unreadable; reference source unavailable; provider absent or unavailable; approval authority unavailable; identity provider unavailable; record-keeping or audit recording failure; measurement source unavailable; AI service unavailable (through LBB-11, not an integration of LBB-12). Do not invent retries, timeouts, compensation, rollback, recovery time, recovery point, availability or service-level targets (G-04, G-10).

F. Security, privacy and governance

Map SG, AIB, BR, CON and OOS controls to each relationship. Address least privilege, no AI writes to systems of record, masking before any model call (SG-06, AIB-006), tenant isolation (G-14), data residency and AI processing location (G-03, DEC-001), retention (DEC-008, OOS-017), audit scope (DEC-008, G-09) and human accountability (SG-03, AIB-008). Data classifications are unvalidated. Do not claim regulatory compliance.

G. Diagrams

Provide Mermaid source, compatible with Mermaid 8.8.0 (graph or sequenceDiagram, quoted labels, classDef and class statements, no `:::` shorthand, no bidirectional edges), for:

1. Integration context: solution boundary, LBB-16, the LBB integration points, XC-P01 to XC-P11, approval authority, record-keeping facility, measurement sources and all twelve references. Use dashed borders for assumed or unverified capabilities, consistent with SOL-003 Diagram 6.
2. Logical interaction views for the critical relationships I-1, I-2, I-3 and IX-01, showing request, result, limitation, hold and human decision steps without protocols.
3. Failure and governance enforcement: pause, hold, limitation, human review and manual-path behaviour, with unresolved gaps labelled.

Do not show APIs, brokers, protocols, queues, endpoints or products. Keep diagrams consistent with the inventory and with SOL-003. Report whether the diagrams were rendered or checked by reading only.

H. Decisions, assumptions and gaps

Carry forward at minimum: AD-01, AD-02, DEC-001, DEC-004, DEC-006, DEC-007, DEC-008, DEC-009, DEC-011, DEC-013, DEC-014, DEC-015, DEC-016, DEC-017, DEC-021, DEC-023, DEC-005, Q-01 to Q-10, ASM-004, ASM-005, ASM-006, ASM-010, ASM-011, DEP-001 to DEP-009, G-01 to G-05, G-07, G-09 to G-17, PCR-013, SAF-08, SAF-09 and SAF-12. Add no invented repository IDs. Label any new local reference as assessment-local.

I. Traceability

Provide a matrix covering all twelve relationships:

Reference → source → destination → purpose → CAP / VS / PRC → IC → controls (BR, SG, AIB) → failure behaviour (FS, EXC) → evidence status → open decision or gap.

J. Quality review

Check that:

- All twelve relationships are present with exact references and directions matching SOL-003.
- Every source and destination traces to a named LBB or XC-P, or is an explicit gap.
- Triggers and information are stated only where supported.
- Communication patterns are logical, not technical.
- XC-P status remains A or G where appropriate; non-replacement constraints are intact.
- Human decisions, deterministic eligibility and per-record activation remain intact.
- No AI integration path reaches a system of record.
- A limitation is never converted into a pass, and no control is skipped on failure.
- Activation history and enterprise record retention are not conflated.
- All missing payload, endpoint, ownership, service-level, retry, timeout and recovery details are listed as gaps.
- Diagrams and inventory use consistent identifiers.
- Only SOL-004 was created and nothing was committed.

### 8. Required Deliverable Structure

Write the output to docs/solution/SOL-004-integration-architecture.md, titled "Task 04.4, Integration Architecture: Working Analysis", with this document control block:

- Artifact: SOL-004
- Task: Task 04, activity 4.4 (Integration Architecture)
- Version: 0.1
- Status: DRAFT. Working analysis. Ready for human review. Nothing has been approved.
- Approval record: None.

Present the analysis in this order:

1. Executive Summary.
2. Scope, Governance and Sources.
3. Integration Context and Boundaries.
4. Integration Principles and Evidence Rules.
5. Integration Inventory (all twelve relationships).
6. Relationship-Specific Analysis.
7. Logical Communication and Interaction Patterns.
8. Information Exchanged and Data Dependencies.
9. Security, Privacy and Governance Controls.
10. Failure Handling and Operational Resilience.
11. Integration Architecture Diagrams (Mermaid source included).
12. Traceability Matrix.
13. Decisions, Assumptions, Dependencies and Gaps.
14. Quality and Consistency Review.
15. Recommendations for Human Review.
16. Handover to Task 04.5.
17. Validation Notes.

Follow the repository writing style: professional, concise, active voice, no emojis, plain prose with simple headings, no bold or italics. Open with a summary of one or two sentences, and order recommendations by priority, highest first. State the target metrics (65 percent faster activation, 75 percent fewer support touchpoints per 1,000 activations, 99.8 percent first-time-right) only as targets; baselines are not agreed (DEC-005). Do not invent figures, client names or proprietary data.

### 9. Handover to Task 04.5

The Task 4 learning guide names activity 4.5 Data Flows: trace important information flows, identifying origin, destination, purpose, transformation or validation needs, dependencies and relevant security considerations. Expected output: Logical Data Flow Models. Use only that wording.

Carry forward the integration inventory and the relationship-level IC concepts. Do not assume Task 04.4 resolves payload content, data ownership, classification, residency or retention. These remain explicit gaps for Task 04.5.

### 10. Final Output and Governance Statement

End the analysis with:

Task 04.4, Integration Architecture

- Status: Working integration architecture analysis.
- Authorisation: Task 04 working analysis under CLAUDE.md and DEC-022; no separate authorisation record exists.
- Formal human approval: Not obtained.
- Technology, vendor and protocol selection: None.
- Physical interface and deployment design: Not defined.
- Implementation: Not performed.
- Repository modifications: One new file, SOL-004. No existing file changed.
- Outstanding decisions and information gaps: Explicitly identified.

The central design principle is:

Business Capability → Logical Building Block → Integration Relationship → Information Exchanged → Control Enforcement → Failure Handling → Evidence Status

Do not make the integration architecture appear more complete than the evidence permits. Preserve source provenance, exact identifiers and every unresolved matter.

Complete the analysis, present SOL-004 and the validation evidence, and STOP. Wait for explicit human approval before Task 04.5.
