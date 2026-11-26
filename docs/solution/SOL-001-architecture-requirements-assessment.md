# SOL-001: Architecture Requirements Assessment

## 1. Document control

| Field | Value |
| :-- | :-- |
| Artifact | SOL-001 |
| Task | Task 04, activity 4.1 (Architecture Requirements Assessment) |
| Version | 0.1 |
| Date | 2026-11-26 |
| Author | AI-generated draft (Claude Code) for review by the architecture team |
| Status | DRAFT. Ready for human review. Nothing has been approved. |
| Approval record | None. Approval must be recorded by an authorised person. |

## 2. Executive summary

The Task 01 to Task 03 Part 1 outputs give a strong, traceable picture of what the solution must do: 38 business capabilities, 16 backlog stories, nine business rules, twelve AI boundary rules and six operational processes. They give almost no picture of the enterprise systems the solution must work with. No existing system is named, no interface is described, and no performance, availability or data residency target is stated. The architecture can therefore be decomposed into logical components with confidence, but integration and technology design cannot be confirmed until the information gaps in section 11 are closed, starting with the statutory engine, the payroll system of record and the first-release jurisdiction.

Three points shape everything below.

- No source artifact is approved. Task 01 and Task 02 were authorised as working baselines, and Task 03 Part 1 is a draft awaiting review. In this document, "confirmed" means stated in a baseline document or a working-baseline artifact. It does not mean approved.
- Task 03 Part 2 (state model, rules, decisions, requirements and the consolidated operational blueprint) has not started (OPS-009). The requirements in section 8 are therefore drawn from backlog stories, business rules and process steps, not from a formal requirements specification.
- The Google Cloud stack in `tech-stack.md` is a proposal, not a constraint (DEC-022, decided in the Task 02 authorisation). Nothing in it is treated as an existing system or a requirement here.

## 3. Scope, sources and evidence classification

### Scope

This assessment covers bulk guided activation of employee profiles during enterprise onboarding, tenant provisioning or organisational restructuring (`Problem statement.md` section 1). Migration of historical payroll data, such as prior pay runs and year-to-date balances, is out of scope (CON-007, OOS-001). It does not design the architecture. Activities 4.2 to 4.7 do that.

### Sources reviewed

| Source | Status | Used for |
| :-- | :-- | :-- |
| `Problem statement.md` | Verified baseline | Problem, bottlenecks, targets |
| `Business Model Canvas to Business Architecture Blueprint.md` | Baseline | Key resources, partners, information handled, rules, AI boundaries |
| `product-backlog.md`, epic-01 to epic-06 | Baseline | Stories PA-01 to PA-16 and acceptance criteria |
| BIZ-001 to BIZ-008 (Task 01) | DRAFT, working baseline | Stakeholders, objectives, KPIs, assumptions, constraints, risks, decisions, AI rules, scope |
| ARC-001 to ARC-007 (Task 02) | DRAFT, working baseline | Capabilities, value stream, traceability, ownership, dependencies, business rules, proposed changes |
| OPS-002, OPS-003, OPS-009 (Task 03 Part 1) | DRAFT, review pending | Processes, exceptions, human-review pathways, questions Q-01 to Q-10, assumptions A-01 to A-07 |
| `tech-stack.md`, `docs/solution-architecture.svg` | Proposal (DEC-022) | Reference only; not evidence of existing systems |

### Evidence classification

Every material statement carries one of four labels.

| Label | Meaning in this document |
| :-- | :-- |
| Confirmed | Stated in a baseline document or a Task 01 to 03 artifact, with the source given. Not yet formally approved. |
| Assumption | Recorded as an assumption in a source artifact (ASM, A-), with its validation owner. This assessment adds no new assumptions. |
| Gap | Information needed for a sound architecture that the sources do not contain. |
| Decision | A choice with architectural impact that an authorised person must make. Existing DEC and Q items are reused; items prefixed AD are raised by this assessment. |

## 4. Business capabilities the solution must support

Status: Confirmed for CAP-001 to CAP-007 (blueprint section 3, ARC-001). CAP-008 and CAP-009 are proposed cross-cutting additions awaiting acceptance (PCR-010).

| Level 1 capability | Level 2 and 3 capabilities | Epic | Objectives | Notes |
| :-- | :-- | :-- | :-- | :-- |
| CAP-001 Guided batch intake and setup | CAP-010 batch identification and lifecycle tracking; CAP-011 batch input acceptance and structural inspection; CAP-012 activation context capture | EPIC-01 | BO-001, BO-008 | CAP-012 has no backlog story (PCR-011) |
| CAP-002 Data mapping and normalization | CAP-013 source-to-payroll field mapping; CAP-014 custom pay-code mapping; CAP-015 mapping review and approval | EPIC-02 | BO-002, BO-003 | AI may suggest mappings (AI-001, AI-002) |
| CAP-003 Entity and jurisdiction resolution | CAP-016 entity hierarchy resolution and inheritance; CAP-017 jurisdiction context assignment; CAP-018 ambiguity surfacing and resolution | EPIC-02 | BO-003, BO-006 | AI must not decide assignments (AI-005 rejected) |
| CAP-004 Pre-activation validation and simulation | CAP-019 data and configuration validation, with Level 3 CAP-035 compensation, CAP-036 tax and withholding, CAP-037 benefit plan, CAP-038 direct-deposit banking; CAP-020 issue severity classification; CAP-021 dry-run simulation | EPIC-03 | BO-003, BO-004, BO-006 | Depends on an unidentified statutory engine |
| CAP-005 Asynchronous batch activation and partial commit | CAP-022 asynchronous processing and progress visibility; CAP-023 eligible-record activation and record isolation; CAP-024 recovery without duplicate effects | EPIC-04 | BO-001, BO-005, BO-006 | Commits to the payroll system of record |
| CAP-006 Remediation and bulk fixes | CAP-025 record- and field-level diagnosis; CAP-026 record correction and revalidation; CAP-027 reviewed bulk correction | EPIC-05 | BO-002, BO-005, BO-007 | Corrected records return to validation alone (BR-005) |
| CAP-007 Activation diagnostics and audit | CAP-028 outcome reporting; CAP-029 history recording; CAP-030 outcome measurement | EPIC-06 | BO-007, BO-008 | CAP-030 has no story; DEC-023 open |
| CAP-008 Activation authorization and approval (proposed) | CAP-031 activation approval; CAP-032 sensitive change authorization | EPIC-04, EPIC-05 | BO-006 | CAP-031 has no story (PCR-012); model undefined (DEC-007) |
| CAP-009 Activation data protection (proposed) | CAP-033 role-based access to activation detail; CAP-034 retention control | EPIC-06 | None | Rests on constraint CON-004 only (PCR-009) |

Architectural implication: the six core capability groups map one to one to the six value-stream stages (ARC-002) and the six processes (OPS-002). CAP-008 and CAP-009 cut across all stages and will become shared services or controls rather than stage components. OPS-009 assumption A-07 uses the Level 1 groups as business domains because no domain model exists.

## 5. Existing enterprise systems and applications

The sources name existing systems only by role. None gives a product name, owner, hosting location, interface or data model. The table records exactly what is stated and nothing more.

| System or asset (as named in the source) | Known role | Source | Classification |
| :-- | :-- | :-- | :-- |
| Payroll management system, including the current guided activation wizard | Hosts the current semi-manual, step-by-step activation workflow that this work improves | Problem statement sections 1 and 2; blueprint key resources | Confirmed to exist; details are a gap |
| Payroll engine | Receives activated cohorts; the first live payroll runs on it | Problem statement section 2; blueprint section 3 | Confirmed to exist; out of scope for redesign (OOS-002) |
| Statutory engines | Apply statutory rules; expected to validate and to run a dry run against production-level rules | Problem statement sections 3 and 5; ASM-006; DEP-001, DEP-004 | Confirmed to exist; which engine is authoritative is open (DEC-015) |
| Payroll data model | Target data structure for activated profiles | Blueprint key resources; DEP-005 | Confirmed to exist; access not yet arranged (DEP-005) |
| Client source systems producing external payroll exports | Origin of employee data | Problem statement section 5; ASM-004 | Source format is an assumption (ASM-004); formats undecided (DEC-009) |
| Client HR information system | Named only as not to be replaced | OOS-003 (sourced from the Task 01 prompt only) | Gap: whether it is a source system at all is not stated |
| Pay-code catalogue | Authoritative list against which custom pay codes are mapped | PA-04; ASM-010; DEP-002 | Assumption; existence and owner unconfirmed |
| Entity hierarchy source | Authoritative parent-child entity structure | PA-05; ASM-005; DEP-003 | Assumption; existence and owner unconfirmed |
| Source-system, statutory-data or verification providers | Possible external dependencies of the payroll product | Blueprint key partners; DEC-004; DEP-006 | Gap: none identified |

Gap: the sources do not say whether the payroll management system is the provider's own product or a third-party platform, where it is hosted, or whether it exposes interfaces. `tech-stack.md` open decision 1 raises the same question about hosting. This is the single largest gap for activities 4.2 and 4.4.

## 6. Users, stakeholders and external actors

Source: BIZ-003. Roles with basis ASSUMPTION are inferred and unconfirmed.

| ID | Role | Type | Interaction with the solution | Basis |
| :-- | :-- | :-- | :-- | :-- |
| STK-001 | Client payroll administrator | Primary user | Prepares data, resolves issues, initiates or approves activation (authority undefined, DEC-007) | Confirmed |
| STK-002 | Implementation specialist | Primary user | Supports onboarding and complex exceptions | Confirmed |
| STK-003 | Payroll or compliance owner | Governance | Confirms validation rules and blocking conditions | Confirmed |
| STK-004 | Product or engineering owner | Delivery | Delivers and operates the capability and its diagnostics | Confirmed |
| STK-005 | Payroll operations user | Primary user | Recovers interrupted processing (PA-11; Q-05 open) | Confirmed |
| STK-006 | Authorized payroll or compliance reviewer | Governance | Investigates activation history | Confirmed |
| STK-007 | Client organization | External actor | Supplies employee data and organisational context | Derived |
| STK-008 | Payroll provider | Business | Offers and operates the payroll product | Derived |
| STK-009 | Employees whose profiles are activated | Affected party | No interaction; their data is processed | Derived |
| STK-010 | Business sponsor | Governance | Approves business case and targets; not named (OQ-001) | Assumption |
| STK-011 | Data protection or privacy owner | Governance | Approves access, masking and retention | Assumption |
| STK-012 | Information security owner | Governance | Approves security controls, including for AI | Assumption |
| STK-013 | Customer success or account owner | Business | Monitors client confidence after go-live | Assumption |

External system actors: the client source systems, the statutory engines, the payroll engine and any providers under DEC-004. Optional AI model services appear only if AI is adopted (DEC-014). Gap: the sources do not say whether the client payroll administrator signs in through the provider's identity system or a client identity provider.

## 7. Existing systems that must be integrated

Each integration below is required by a confirmed capability. The integration need is confirmed. The system, interface and pattern are not.

| # | Integration need | Purpose and information exchanged | Capabilities | Source | Status |
| :-- | :-- | :-- | :-- | :-- | :-- |
| I-1 | Statutory engine, validation | Send candidate profile data; receive statutory and configuration findings | CAP-019, CAP-035 to CAP-038 | Problem statement section 5; DEP-001; DEC-015 | Need confirmed; engine and interface are gaps |
| I-2 | Statutory engine, non-committing dry run | Simulate activation with production-equivalent rules and no live effect (BR-006) | CAP-021 | Problem statement section 3; ASM-006; DEP-004; DEC-016 | Need confirmed; engine support is an assumption (ASM-006) |
| I-3 | Payroll management system, activation commit | Activate eligible profiles one record at a time without duplicate effects (BR-008) | CAP-023, CAP-024 | Problem statement section 5; DEP-005; PA-10, PA-11 | Need confirmed; interface and idempotency support are gaps |
| I-4 | Client source data intake | Receive employee data as external payroll exports | CAP-011, CAP-013 | Problem statement section 5; ASM-004; DEC-009 | Need confirmed; formats, channels and file or API intake are open (OOS-013 deferred) |
| I-5 | Pay-code catalogue | Read authoritative pay codes for mapping | CAP-014 | PA-04; ASM-010; DEP-002 | Assumption |
| I-6 | Entity hierarchy source | Read parent-child entity structure for inheritance | CAP-016 | PA-05; ASM-005; DEP-003 | Assumption |
| I-7 | Verification or statutory-data providers | Possibly verify banking or statutory data | CAP-038 | Blueprint key partners; DEC-004; DEP-006 | Gap: may not exist |
| I-8 | Hand-off to the first live payroll run | Make the activated cohort payroll-ready | Boundary VSB-01 | JS-13; DEC-021 | Decision: whether this is in scope |
| I-9 | Measurement data sources | Cycle time, support touchpoints, first-payroll corrections | CAP-030 | ASM-011; DEP-007; DEC-005 | Assumption; data sources not identified |

Out of scope for integration: replacing the HR information system (OOS-003), a general-purpose data integration platform (OOS-014) and redesign of payment, tax filing or benefits administration (OOS-007).

## 8. Major data sources and data dependencies

### Data processed

Confirmed (blueprint section 3, information handled): employee identity, compensation, tax withholding, banking, benefit, pay-code and organisational entity data. Access and retention must be limited to what activation needs (CON-004).

### Data the solution creates

Confirmed through capabilities and stories, with no storage design implied: batch and its lifecycle status (CAP-010), activation context (CAP-012), field and pay-code mappings with review decisions (CAP-013 to CAP-015), entity and jurisdiction assignments (CAP-016, CAP-017), validation findings with severity (CAP-019, CAP-020), dry-run results and their stated limitations (CAP-021), per-record activation outcomes (CAP-023), remediation items and corrections (CAP-025 to CAP-027), approvals and authorisations (CAP-031, CAP-032), activation history (CAP-029), AI suggestions and the human decision on each (AIB-010), and outcome measures (CAP-030).

### Data dependencies

| ID | Dependency | Needed for | Status |
| :-- | :-- | :-- | :-- |
| DEP-001 | Authoritative validation rules and statutory engine | Validation, dry run | Open |
| DEP-002 | Pay-code catalogue and mapping rules | Pay-code mapping | Open |
| DEP-003 | Entity hierarchy source | Entity resolution | Open |
| DEP-004 | Non-committing statutory engine execution | Dry run | Open |
| DEP-005 | Access to the existing activation workflow and payroll data model | Intake, activation | Open |
| DEP-006 | Source-system, statutory-data or verification providers | Intake, validation | Open |
| DEP-007 | Support and implementation case data | KPI-002 baseline | Open |
| DEP-008 | Payroll or compliance owner to define blocking policy and rules | Validation, isolation | Open |
| DEP-009 | Approved privacy and security controls | Remediation, history | Open |

Gaps: no data owner is named for any data domain, no system of record is identified for each domain, and no required employee field list exists (DEC-009, DEC-012).

## 9. Functional and non-functional requirements

### 9.1 Functional requirements

Status: Confirmed as backlog stories and business rules. Priorities are recommendations, not commitments. Task 03 Part 2 has not yet turned these into formal requirements.

| Area | Requirement | Source | Priority |
| :-- | :-- | :-- | :-- |
| Prepare batch | Start, identify and return to an activation batch | PA-01 | P0 |
| Prepare batch | Upload and structurally inspect batch input, separating input problems from record problems | PA-02 | P0 |
| Prepare batch | Capture activation context before mapping | CAP-012; DEC-010 | No story (PCR-011) |
| Map and resolve | Review source-to-payroll field mappings | PA-03 | P0 |
| Map and resolve | Resolve custom pay-code mappings | PA-04 | P0 |
| Map and resolve | Review entity and jurisdiction assignments, with ambiguity surfaced (BR-004) | PA-05 | P0 |
| Map and resolve | Review optional AI mapping suggestions | PA-06 | P1 |
| Validate | Run pre-activation validation with record- and field-level findings | PA-07 | P0 |
| Validate | Run a dry run that creates no live payroll effect (BR-006) | PA-08 | P0 |
| Process | Track asynchronous batch progress | PA-09 | P0 |
| Process | Activate eligible records while isolating failures (BR-001, BR-002, BR-003) | PA-10 | P0 |
| Process | Retry interrupted processing without duplicate effects (BR-008) | PA-11 | P0 |
| Process | Approve activation before processing | CAP-031; A-05; DEC-007 | No story (PCR-012) |
| Remediate | Inspect actionable record-level errors | PA-12 | P0 |
| Remediate | Correct and revalidate one record without reprocessing the batch (BR-005) | PA-13 | P0 |
| Remediate | Apply a reviewed bulk fix with a preview of affected records and fields (BR-007) | PA-14 | P1 |
| Review | Review batch and per-record outcomes | PA-15 | P0 |
| Review | Review activation changes and decisions in context | PA-16 | P1 |
| Review | Measure outcomes against the target metrics | CAP-030; DEC-023 | No story; scope open |
| Cross-cutting | Route exceptions EXC-01 to EXC-23 to human review where OPS-003 defines a pathway | OPS-003 | 17 sourced, 6 proposed |

AI-related functional rules (BIZ-007, confirmed as rules): AI may only suggest (AIB-002, AIB-007); AI is optional and core activation must work without it (AIB-012, CON-006); every suggestion and its human decision is recorded (AIB-010). AI-005 to AI-009 are rejected uses.

### 9.2 Non-functional requirements

The sources state quality attributes but almost no measurable system targets. The three program targets are business outcomes, not system service levels, and they have no agreed baseline (DEC-005).

| Quality attribute | What the sources state | Source | Classification |
| :-- | :-- | :-- | :-- |
| Data integrity and compliance | Activation must preserve payroll data integrity and statutory compliance | CON-001, CON-002 | Confirmed |
| Fault isolation | A failing record never blocks the batch or hides other records' status | CON-003, BR-001, BR-002 | Confirmed |
| Reliability and recovery | Retries and interruptions create no duplicate effects | BR-008, PA-11, KPI-014 | Confirmed; semantics open (DEC-017) |
| Security and privacy | Protect identity, compensation, tax, benefit and banking data; least access and retention | CON-004, BR-009, CAP-033, CAP-034 | Confirmed as a need; controls undefined (DEP-009, DEC-008) |
| AI data protection | No unrestricted AI access; mask sensitive values before any model call | AIB-005, AIB-006 | Confirmed as rules; pending security owner confirmation (PCR-013) |
| Auditability and traceability | Record mappings, corrections, validation results, approvals and outcomes; record the deciding person | CAP-029, AIB-008, AIB-010, KPI-020 | Confirmed as a need; required events undefined (DEC-008) |
| Audit immutability | Must not be claimed without an agreed design and requirement | OOS-016 | Confirmed constraint |
| Explainability | Errors are actionable at record and field level; dry-run limitations are shown | BO-007, PA-12, RSK-002 | Confirmed |
| Scalability | Batches of hundreds or thousands of profiles | Problem statement section 1 | Confirmed qualitatively; volumes, batch sizes and frequency are a gap (OQ-004) |
| Performance | 65% reduction in end-to-end cycle time | Problem statement section 5; KPI-001 | Target only; no system response or throughput target exists |
| Availability and disaster recovery | Not stated | None | Gap |
| Data residency and regulatory regime | Not stated; depends on jurisdiction | DEC-001, OQ-002, CON-005 | Gap |
| Multi-tenancy | "Tenant provisioning" appears as a trigger; no isolation requirement is stated | Problem statement section 1 | Gap |
| Maintainability and operability | The product or engineering owner operates the capability; no targets stated | STK-004 | Gap |
| Retention | Limited to what activation needs; periods not to be invented | CON-004, OOS-017 | Gap (DEC-008) |

## 10. Architecture constraints and assumptions

### 10.1 Confirmed constraints

| ID | Constraint | Architectural effect |
| :-- | :-- | :-- |
| CON-001, CON-002 | Preserve integrity and compliance; validate and simulate before hard commit | Validation and dry run sit before the commit integration |
| CON-003 | Isolate invalid records without losing valid records' status | Per-record state and per-record commit |
| CON-004 | Protect sensitive employee data; limit access and retention | Access control and data minimisation in every component |
| CON-005 | Assume no jurisdiction or regulation until recorded from an authoritative source | No jurisdiction-specific rules, regions or frameworks in the design |
| CON-006, AIB-012 | AI is optional and must not block core activation | AI as a detachable, non-critical component |
| CON-007 | No historical payroll migration | No year-to-date or prior pay-run data flows |
| CON-008 | No fixed batch error-rate suspension threshold without approved policy | Batch-stop logic configurable and policy-driven |
| AIB-002, AIB-004, AIB-007, AIB-011 | AI never decides validity, approves, activates or calculates | Deterministic rules and statutory engines remain the authority |
| OOS-002 | Payroll calculation and statutory engines are not redesigned | They are integrated as external systems |
| OOS-010 | No event broker, cloud, service boundaries or provider selected before technical discovery | Technology choices stay proposals until approved |
| OOS-014, OOS-018 | No general-purpose integration platform or analytics product | Integration and reporting scoped to activation |
| DEC-022 (decided) | The proposed stack is a proposal, not a constraint | `tech-stack.md` may inform options in 4.2 to 4.6 but binds nothing |

### 10.2 Recorded assumptions with architectural impact

All are UNVALIDATED.

| ID | Assumption | Impact if false | Validate with |
| :-- | :-- | :-- | :-- |
| ASM-006 | The statutory engines can run a non-committing simulation with production-equivalent rules | Dry run (CAP-021) needs a different design or must state wider limitations | STK-004, statutory engine owner |
| ASM-008 | Record-level failures can be isolated without weakening controls | Partial commit (CAP-023) may not be permissible | STK-003 |
| ASM-009 | Corrected records can be revalidated individually | Remediation loop needs batch-level reprocessing | STK-004 |
| ASM-004 | Source data arrives as external exports with differing schemas | Intake and mapping components change shape | STK-002 |
| ASM-005 | An authoritative entity hierarchy source exists | Hierarchy must be captured inside the solution | STK-003 |
| ASM-010 | An authoritative pay-code catalogue exists | Pay-code mapping has no target reference | STK-003 |
| ASM-011 | KPI data can be measured from existing records | Measurement needs new instrumentation | STK-004 |
| A-03 | System steps in OPS-002 are deterministic business activities with no technology implied | Component mapping in 4.3 may need revision | Task 03 Part 2 |
| A-05 | Activation approval, if required, happens before processing | Approval position in the flow changes | Q-01, DEC-007 |
| A-06 | History is recorded throughout the batch | Audit component scope changes | DEC-008 |
| A-07 | Level 1 capability groups serve as business domains | Component boundaries in 4.3 may shift | STK-004 |

## 11. Information gaps

Ordered by impact on activities 4.2 to 4.4, highest first. "Blocks" means the dependent design cannot be confirmed until the gap closes.

| # | Gap | Blocks | Closes through |
| :-- | :-- | :-- | :-- |
| G-01 | Identity, hosting and interfaces of the payroll management system, including whether it can commit records one at a time and safely repeat a commit | Integration I-3; component boundaries | DEP-005; STK-004 |
| G-02 | Which statutory engine is authoritative, and whether it supports a non-committing dry run | Integrations I-1 and I-2; CAP-021 | DEC-015, DEC-016, ASM-006 |
| G-03 | First-release jurisdiction and regulatory obligations | Data residency, compliance frameworks, statutory rules | DEC-001, OQ-002 |
| G-04 | Activation volumes, batch sizes, frequency and peak concurrency | Scalability and processing design | OQ-004 |
| G-05 | Supported input methods, formats and required fields | Intake design (I-4) | DEC-009, DEC-012 |
| G-06 | Delivery surface: administrative UI, API, implementation workspace or a combination | Channel and front-end components | DEC-003 |
| G-07 | Authorization model and separation of duties | CAP-008 design; approval gates | DEC-007, Q-01 |
| G-08 | Blocking policy, severity classes and batch-stop conditions | Validation and isolation logic | DEC-006 |
| G-09 | Required audit events, viewing rights, retention and export | CAP-007 and CAP-009 design | DEC-008, OOS-017 |
| G-10 | Availability, recovery, performance and response-time targets | Non-functional design | No source; needs STK-004 |
| G-11 | Owners of the pay-code catalogue and entity hierarchy, and whether they exist | Integrations I-5 and I-6 | ASM-005, ASM-010 |
| G-12 | External providers, if any | Integration I-7 | DEC-004 |
| G-13 | Identity provider for client users | Access design | No source |
| G-14 | Multi-tenancy and tenant isolation requirements | Data and security design | No source |
| G-15 | Owners of data protection, information security and AI governance | Security sign-off | OQ-007, OQ-011 |
| G-16 | State model, formal requirements and controls | Precise component behaviour | Task 03 Part 2, not started |
| G-17 | Handling of fraud indicators and disputes | Exception routing EXC-22, EXC-23 | Q-09, Q-10 |

## 12. Architecture decisions requiring approval

Ordered by priority, highest first. Existing decisions are listed where they have architectural impact. AD items are raised by this assessment and are not yet in any register.

| # | Decision | Why it matters for architecture | Decide by | Source |
| :-- | :-- | :-- | :-- | :-- |
| 1 | DEC-015 and DEC-016: authoritative statutory engine and what the dry run reproduces | Defines the most critical integration and the trust boundary of the dry run | STK-003 | BIZ-005 |
| 2 | AD-01: whether the solution extends the existing activation workflow inside the payroll management system or runs as a separate service that integrates with it | Sets every component boundary and integration in 4.3 and 4.4; the blueprint describes an improvement to the existing workflow but does not settle this | STK-004 | Raised here; blueprint section 3 |
| 3 | DEC-006: blocking policy and batch-stop conditions | Determines validation, isolation and stop logic | STK-003 | BIZ-005 |
| 4 | DEC-007: authorization and approval model | Determines CAP-008 and the approval gates in PRC-04 and PRC-05 | STK-003 | BIZ-005 |
| 5 | DEC-001: first-release jurisdiction | Drives residency, compliance framework and statutory rule scope | STK-010 | BIZ-005 |
| 6 | AD-02: which component holds the working state of a batch (mappings, findings, remediation items) before commit, and which system remains the system of record for activated profiles | Prevents two systems of record for the same profile | STK-004 | Raised here |
| 7 | DEC-017: retry and recovery behaviour | Shapes the commit integration and idempotency design | STK-004 | BIZ-005 |
| 8 | DEC-008: audit events, visibility and retention, and whether an immutable record is required | Determines the audit store design; immutability must not be assumed (OOS-016) | STK-011 | BIZ-005 |
| 9 | PCR-010: acceptance of CAP-008 and CAP-009 as capabilities | Confirms whether authorization and data protection are architectural components | STK-004 | ARC-007 |
| 10 | DEC-014: deterministic, AI-assisted or combined mapping in the first release | Decides whether an AI component and its data controls exist at all | STK-004 | BIZ-005 |
| 11 | DEC-003 and DEC-009: delivery surface and input methods | Front-end and intake components | STK-004 | BIZ-005 |
| 12 | DEC-021: whether the hand-off to the first live payroll is in scope | Adds or removes integration I-8 | STK-004 | BIZ-005 |
| 13 | AD-03: whether any element of the proposed stack is adopted as the starting point for activity 4.2 onward | DEC-022 made the stack a proposal; adopting any part of it still needs a decision | STK-004 | Raised here; DEC-022 |
| 14 | DEC-023: whether outcome measurement against the targets is in scope | Adds or removes CAP-030 and its data flows | STK-004 | BIZ-005 |

## 13. Readiness for activity 4.2

The business and operational requirements are sufficient to start the Enterprise Architecture View and a logical component decomposition, provided both show unknown systems as unconfirmed. They are not sufficient to confirm integrations, data flows or technology choices.

Recommended actions before 4.4 (integration architecture), in priority order:

1. Identify the payroll management system and the authoritative statutory engine, with their owners and interfaces (G-01, G-02).
2. Decide AD-01, so component boundaries in 4.3 rest on an agreed position.
3. Decide the first-release jurisdiction (DEC-001) and obtain volume figures (OQ-004).
4. Decide, or explicitly leave open, DEC-006 and DEC-007, which Task 03 Part 1 already flagged.
5. Name the data protection and information security owners (OQ-007) and agree non-functional targets (G-10).
6. Add AD-01 to AD-03 to the decision register if the reviewer accepts them.

## 14. Validation

- Every confirmed statement names a source artifact. No system, interface, data source or technology is presented as existing unless a source states it.
- No assumption was added. Every assumption listed is already recorded in BIZ-005 or OPS-009.
- No jurisdiction, regulation or retention period is named (CON-005, OOS-017).
- No source file was changed.
- Limitation: this assessment was checked by reading, not by automated cross-reference. A reviewer should confirm the source references before approval.