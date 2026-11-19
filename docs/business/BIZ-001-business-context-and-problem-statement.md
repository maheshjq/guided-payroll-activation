# BIZ-001: Business Context and Problem Statement

Artifact: BIZ-001
Status: DRAFT
Task: Task 01, Business Problem, Intent and Value Model
Sources: `Problem statement.md` (authoritative), `Business Model Canvas to Business Architecture Blueprint.md`, `product-backlog.md`, `epic-01` to `epic-06`, `requirements-document-map.md`

## 1. Purpose and authority

This artifact formalizes the problem statement and the business framing of the blueprint into stable IDs. It does not rewrite either document. `Problem statement.md` remains the verified source; where this artifact summarizes it, the summary is a pointer, and the original wording governs.

Industry context for this task: payroll management and human capital management software and services. This classification comes from the Task 01 prompt and is recorded as ASM-012 because no baseline document states it. No payroll vendor, client, country or statutory jurisdiction is assumed (DEC-001).

## 2. Business context

During enterprise onboarding, tenant provisioning or organizational restructuring, a payroll management system must activate hundreds or thousands of employee profiles at once. Bulk guided activation is the process in which administrative teams configure baseline compensation frameworks, map tax jurisdictions, assign benefit plans, validate direct-deposit banking credentials and establish statutory withholding rules before live payroll runs. Source: `Problem statement.md` section 1.

Because payroll leaves no margin for calculation discrepancies or payment delays, activation is the gatekeeper for data integrity and statutory compliance. The current workflow is a rigid, semi-manual wizard without intelligent validation, asynchronous batch processing or granular error isolation. Source: `Problem statement.md` section 2.

Out of scope and kept visible throughout: migration of historical payroll records, such as prior pay runs and year-to-date balances (OOS-001).

## 3. Business discovery across the activation domain

Each area is classified by what the baseline confirms, what is assumed or hypothesized, and what remains open. Nothing in the "Confirmed" column goes beyond the baseline documents.

| Area | Confirmed in baseline | Assumption or hypothesis | Open item |
| :-- | :-- | :-- | :-- |
| Activation lifecycle, initiation to first live payroll | Six-step value stream from prepare batch to review outcome (blueprint section 3); six epics in journey order | The first live payroll run is where latent activation errors surface (HYP-005) | Whether the hand-off to the first live payroll is in scope (DEC-021) |
| Batch setup and source data intake | Start and identify a batch; report unreadable input with a reason (EPIC-01, PA-01, PA-02) | Source data arrives as external payroll exports (ASM-004) | Supported input methods and formats (DEC-009); required context (DEC-010); resume or abandon (DEC-011) |
| Source data schemas and field mapping | Schemas are reconciled manually today (BN-02); mappings must be reviewable (EPIC-02, PA-03) | No structured mapping model exists today (HYP-003) | Required source fields (DEC-012) |
| Custom pay code mapping | Custom pay codes are mapped by hand (BN-02, PA-04) | An authoritative pay-code catalogue exists (ASM-010) | Required pay-code mappings (DEC-012) |
| Entity, parent-child and jurisdiction resolution | Parent-child structures are not inherited or resolved (BN-03); ambiguity must be surfaced (EPIC-02, PA-05) | An authoritative hierarchy source exists (ASM-005); hierarchies are not modelled for inheritance (HYP-004) | Which settings inherit (DEC-013); which jurisdictions apply (DEC-001) |
| Baseline compensation framework configuration | Configured during activation (`Problem statement.md` section 1) | None beyond the baseline | Which compensation fields are required (DEC-012) |
| Tax jurisdiction mapping and statutory withholding | Mapped during activation; must preserve statutory compliance (`Problem statement.md` section 1, blueprint section 1) | None. No jurisdiction or rule set is assumed. | Jurisdiction (DEC-001); authoritative rules and engine (DEC-015); applicable obligations (OQ-002) |
| Benefit plan assignment | Assigned during activation (`Problem statement.md` section 1) | None beyond the baseline | Not covered by a dedicated story; flagged in the completion record |
| Direct-deposit banking credential validation | Validated during activation; banking data requires protection (`Problem statement.md` section 1, blueprint section 3) | Not covered by a dedicated story; treated as part of pre-activation validation | What validation means for banking credentials (DEC-015) |
| Pre-activation validation and dry-run simulation | Validation and a dry run must precede commit; a dry run must not activate (EPIC-03, PA-07, PA-08) | Statutory engines can run a non-committing simulation (ASM-006) | What the dry run reproduces (DEC-016); blocking policy (DEC-006) |
| Asynchronous processing and partial activation | Large batches process asynchronously; record failures are isolated (EPIC-04, PA-09, PA-10, PA-11) | Isolation can occur without weakening controls (ASM-008) | Batch-stop conditions (DEC-006); retry behaviour (DEC-017); user controls (DEC-018) |
| Exception isolation and remediation | Errors point to record and field; corrections are revalidated (EPIC-05, PA-12, PA-13, PA-14) | Corrected records revalidate individually (ASM-009) | Bulk-fix eligibility (DEC-019); authorization (DEC-007); unrecoverable errors (DEC-020) |
| Error reporting, audit logging and result review | Generic failure notices today (BN-05); outcomes and changes recorded (EPIC-06, PA-15, PA-16) | Error reporting aggregates failures (HYP-006) | Required audit events and retention (DEC-008) |
| Support and implementation specialist involvement | Specialists hand-hold clients today; touchpoints are a reduction target, not role removal (`Problem statement.md` section 4, blueprint section 3) | Repeated confirmation screens add effort without control (HYP-007) | What counts as a support touchpoint (OQ-008) |

## 4. Bottlenecks

The five primary bottlenecks and failure modes in `Problem statement.md` section 3, with stable IDs. Meanings are unchanged.

| ID | Bottleneck | Summary of the problem statement | Journey stages | Objectives |
| :-- | :-- | :-- | :-- | :-- |
| BN-01 | Cascading validation failures | Validation applied sequentially or at final submission; one bad record can abort or lock the whole batch and force a wizard restart | JS-06, JS-08, JS-09, JS-11 | BO-001, BO-005, BO-008 |
| BN-02 | Heavy reliance on manual intervention | Specialists and administrators manually reconcile schemas, map custom pay codes and resolve missing-field flags across confirmation screens | JS-03, JS-04, JS-05 | BO-001, BO-002, BO-003 |
| BN-03 | Complex cross-entity dependency mapping | Rules differ across the organization; parent-child structures are not inherited or resolved, forcing repetitive manual assignment per sub-entity | JS-05 | BO-001, BO-003, BO-006 |
| BN-04 | Lack of pre-ingestion sandboxing | No trial or dry-run activation against production-level statutory engines before hard commit | JS-06, JS-07, JS-13 | BO-003, BO-004, BO-006 |
| BN-05 | Opaque error reporting | Generic or aggregated failure notices instead of cell-level error coordinates and corrective recommendations | JS-02, JS-10, JS-11, JS-12 | BO-002, BO-005, BO-007, BO-008 |

## 5. Business problem statement

This is a structured restatement for traceability. `Problem statement.md` section 2 is the authoritative wording.

Bulk guided activation of large employee cohorts relies on a rigid, semi-manual wizard that validates late, cannot isolate individual record failures, requires manual reconciliation of data, pay codes and entity structures, offers no pre-commit simulation, and reports errors generically. As a result, activation is slow, expensive to deliver and prone to data discrepancies that cause failures in the first live payroll. The capability is required because activation is the gatekeeper for payroll accuracy and statutory compliance, and the present workflow fails at that role at enterprise scale.

## 6. Business problems

One business problem per impact dimension in `Problem statement.md` section 4. Each links to the bottlenecks that cause it and the objectives that address it.

| ID | Business problem | Impact dimension | Consequence | Bottlenecks | Objectives |
| :-- | :-- | :-- | :-- | :-- | :-- |
| BP-001 | Large-cohort activation takes too long | Time to value | Implementation timelines extend from days into months, delaying go-live and contract-based revenue recognition | BN-01, BN-02, BN-03 | BO-001, BO-005, BO-008 |
| BP-002 | Activation consumes excessive implementation and support effort | Cost of delivery | High onboarding overhead from engineering and implementation hours spent hand-holding clients | BN-02, BN-05 | BO-002, BO-005, BO-007 |
| BP-003 | Latent configuration errors pass activation | First-payroll failure rate | Incorrect wage disbursements, missing deductions and inaccurate tax filings in the first live pay cycle | BN-02, BN-03, BN-04 | BO-003, BO-004 |
| BP-004 | Statutory profiles can be activated incorrectly | Regulatory and financial exposure | Compliance penalties, late-filing interest and retrospective tax adjustments for provider and client | BN-03, BN-04 | BO-004, BO-006 |
| BP-005 | Early operational friction erodes client confidence | Early churn and brand trust | Degraded confidence in the first 30 to 60 days and higher risk of contract termination | BN-01, BN-05 | BO-007, BO-008 |

## 7. Root-cause hypotheses

The problem statement describes symptoms. These hypotheses describe possible causes. All are UNVALIDATED and require evidence from product behaviour and operational data (OQ-003, ASM-014).

| ID | Root-cause hypothesis | Bottleneck | Basis | Status |
| :-- | :-- | :-- | :-- | :-- |
| HYP-001 | Validation rules run sequentially or only at final submission | BN-01 | Stated in `Problem statement.md` section 3; not yet evidenced with data | UNVALIDATED |
| HYP-002 | The wizard treats a batch as a single all-or-nothing transaction with no record-level isolation | BN-01 | Inferred from the abort-or-lock behaviour described in section 3 | UNVALIDATED |
| HYP-003 | No structured source-to-target mapping model exists, so reconciliation depends on specialist knowledge | BN-02 | Inferred from manual reconciliation described in section 3 | UNVALIDATED |
| HYP-004 | Parent-child entity structures are not modelled for inheritance of activation settings | BN-03 | Stated in section 3 as a failure to inherit or resolve | UNVALIDATED |
| HYP-005 | No non-committing execution path exists against the statutory engines | BN-04 | Stated in section 3 as the absence of a dry run | UNVALIDATED |
| HYP-006 | Error reporting aggregates failures instead of retaining record and field coordinates | BN-05 | Stated in section 3 with the generic notice example | UNVALIDATED |
| HYP-007 | Repeated confirmation screens add effort without adding control | BN-02 | Inferred; the problem statement mentions multiple confirmation screens but not their value | UNVALIDATED |

## 8. Business consequences by impact dimension

| Impact dimension | Business problem | Measured through |
| :-- | :-- | :-- |
| Time to value | BP-001 | KPI-001, KPI-022 |
| Cost of delivery | BP-002 | KPI-002 |
| First-payroll failure rate | BP-003 | KPI-003, KPI-010 |
| Regulatory and financial exposure | BP-004 | KPI-021, KPI-010 |
| Early churn and brand trust | BP-005 | No KPI is defined in the baseline; see OQ-012 |

## 9. Business opportunity

Replace the monolithic, step-by-step wizard with an automated, asynchronous and self-remediating activation capability: smart data mapping, a pre-activation dry run, partial batch commit with error isolation, and record-and-field diagnostics with bulk fixes. Source: `Problem statement.md` section 5. The opportunity is a change to the guided activation process, not a new payroll engine (OOS-002).

## 10. Business vision

Proposed wording, derived from `Problem statement.md` section 5 and not yet reviewed:

Large employee cohorts become payroll-ready quickly and correctly. Issues are found before commit, isolated to the record that has them, explained precisely, and corrected without restarting the batch, while every payroll and statutory control continues to apply.

## 11. Business intent

The blueprint section 1 states the intended outcome: improve the guided activation journey so that large employee batches can be prepared, checked, simulated, activated and remediated with less manual effort and fewer errors, without compromising payroll accuracy or statutory compliance. This artifact adopts that statement unchanged.

## 12. Value proposition

| Stakeholder | Value |
| :-- | :-- |
| Client payroll administrator (STK-001) | Fewer manual reconciliation loops; issues visible before commit; correction without restarting the batch |
| Implementation specialist (STK-002) | Fewer hands-on activation touchpoints; effort concentrated on genuine exceptions |
| Payroll or compliance owner (STK-003) | Validation and authorization controls preserved under partial commit; clear blocking conditions |
| Product or engineering owner (STK-004) | A measurable, diagnosable activation capability |
| Client organization (STK-007) | Earlier and more reliable go-live; fewer first-payroll errors |
| Payroll provider (STK-008) | Lower onboarding cost; reduced regulatory exposure; lower early churn risk |

Source: blueprint section 2, value propositions, mapped to stakeholders in BIZ-003.

## 13. Classification summary

| Category | Items |
| :-- | :-- |
| Confirmed project decisions, from the baseline | Six epics in journey order; historical migration out of scope; three program targets as stated targets; AI is optional and only suggests; record-level isolation; revalidation of corrections |
| Business assumptions | ASM-001 to ASM-014 in BIZ-005 |
| Hypotheses requiring validation | HYP-001 to HYP-007 above; the three program targets until baselines exist (DEC-005) |
| Illustrative examples | The current-state journey in BIZ-006, labelled provisional; the generic failure notice quoted in `Problem statement.md` section 3 |
| Outstanding questions | OQ-001 to OQ-012 and DEC-001 to DEC-023 in BIZ-005 |
