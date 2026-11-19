# BIZ-002: Business Case and Value Model

Artifact: BIZ-002
Status: DRAFT
Task: Task 01, Business Problem, Intent and Value Model
Sources: `Problem statement.md` sections 4 and 5, `Business Model Canvas to Business Architecture Blueprint.md` sections 1, 2 and 4, BIZ-001, BIZ-004, BIZ-007

## 1. Summary

The case for change rests on five business problems (BP-001 to BP-005) caused by five bottlenecks (BN-01 to BN-05). Workflow and deterministic rules address four of the five bottlenecks without AI. Governed AI is an optional increment, mainly for mapping in EPIC-02, and must earn its own governance cost. No monetary figure is stated anywhere in this artifact, because no baseline, volume or cost data exists in the repository. Section 6 defines how value will be calculated once those inputs exist.

This business case has not been approved. Formal approval requires the items listed in section 8.

## 2. Problem-to-value chain

| Link | Content | Defined in |
| :-- | :-- | :-- |
| Business problem | BP-001 to BP-005, one per impact dimension | BIZ-001 |
| Business opportunity | Automated, asynchronous, self-remediating activation capability | BIZ-001 section 9 |
| Business objectives | BO-001 to BO-008 | BIZ-004 |
| Required capabilities | CAP-001 to CAP-007, provisional references to the blueprint | BIZ-008 |
| AI opportunities | AI-001 to AI-004 as candidates or deferred; AI-005 to AI-009 rejected | BIZ-007 |
| Expected benefits | BEN-001 to BEN-008 | Section 4 below |
| KPIs | KPI-001 to KPI-022, three of them program targets | BIZ-004 |
| Business value | Value calculation methodology, no figures | Section 6 below |

## 3. Option comparison

| ID | Option | Description | Expected effect |
| :-- | :-- | :-- | :-- |
| OPT-0 | Current state | Rigid semi-manual wizard, late validation, all-or-nothing submission, generic errors | Reference point for every baseline measurement. Baselines are PENDING (DEC-005). |
| OPT-1 | Workflow and rules without AI | Asynchronous processing, record-level isolation, deterministic mapping and validation, dry-run simulation, record-and-field diagnostics, reviewed bulk fixes | Addresses BN-01, BN-03, BN-04 and BN-05 fully, and BN-02 partly through deterministic mapping |
| OPT-2 | Workflow and rules with governed AI | OPT-1 plus optional AI mapping suggestions and validation-message explanations, under AIB-001 to AIB-012 | Further reduction of manual reconciliation (BN-02) and faster comprehension of errors (BN-05), if evaluation supports it |

The incremental value of AI is measured as OPT-2 minus OPT-1, never as OPT-2 minus OPT-0. Attributing the whole improvement to AI would overstate its contribution, because most of the improvement comes from workflow and rules.

Problems solved without AI: cascading failures (BN-01) by asynchronous processing and isolation; cross-entity mapping (BN-03) by an authoritative hierarchy and inheritance rules; lack of sandboxing (BN-04) by a deterministic dry run against the statutory engines; and the core of opaque reporting (BN-05) by retaining record and field coordinates. Only BN-02 has a candidate AI role, and even there a deterministic option is evaluated first (DEC-014).

## 4. Expected benefits

| ID | Benefit | Options delivering it | KPIs | Problems |
| :-- | :-- | :-- | :-- | :-- |
| BEN-001 | Shorter end-to-end activation cycle time | OPT-1, OPT-2 | KPI-001, KPI-004, KPI-011 | BP-001 |
| BEN-002 | Lower implementation and support effort | OPT-1, OPT-2 | KPI-002, KPI-005, KPI-017, KPI-019 | BP-002 |
| BEN-003 | Fewer errors reaching the first live payroll | OPT-1, OPT-2 | KPI-003, KPI-010 | BP-003 |
| BEN-004 | Fewer full-batch restarts | OPT-1, OPT-2 | KPI-012, KPI-013 | BP-001 |
| BEN-005 | Faster exception resolution | OPT-1, OPT-2 | KPI-015, KPI-016 | BP-002 |
| BEN-006 | Less manual reconciliation of fields and pay codes | OPT-1 partly, OPT-2 incrementally | KPI-006, KPI-007 | BP-002 |
| BEN-007 | Lower regulatory exposure from misconfigured statutory profiles | OPT-1, OPT-2 | KPI-021, KPI-010 | BP-004 |
| BEN-008 | Earlier client go-live and reduced early friction | OPT-1, OPT-2 | KPI-022, KPI-018 | BP-001, BP-005 |

BEN-006 is the benefit where the AI increment is expected to appear. BEN-007 and BEN-008 are partly qualitative; their monetary value depends on inputs the repository does not hold.

## 5. Program targets

The problem statement sets three targets. They are recorded as stated targets with baseline status PENDING, not as approved commitments.

| Target as stated in `Problem statement.md` section 5 | KPI | Baseline | Open definition |
| :-- | :-- | :-- | :-- |
| At least 65 percent reduction in end-to-end activation cycle time | KPI-001 | PENDING | End point of "end-to-end" (OQ-009) |
| 75 percent fewer professional implementation support touchpoints per 1,000 employee activations | KPI-002 | PENDING | What counts as a touchpoint (OQ-008) |
| 99.8 percent first-time-right payroll run rate for newly activated cohorts | KPI-003 | PENDING | Cohort and correction definition (OQ-010) |

The KPI definitions, formulas and data sources are defined once, in BIZ-004.

## 6. Value calculation methodology

All inputs are unavailable today. Each formula names the input it needs and the open item that will supply it.

| Value component | Formula | Required inputs | Open item |
| :-- | :-- | :-- | :-- |
| V1 Effort saving per period | Sum over batches of (baseline specialist and administrator hours per batch minus option hours per batch) | Batch count per period; hours per batch by role, before and after | OQ-004, OQ-005 |
| V2 Delivery cost saving | V1 multiplied by the loaded hourly cost per role | Loaded cost per role | OQ-006 |
| V3 Support touchpoint reduction | (Activations divided by 1,000) multiplied by (baseline touchpoints per 1,000 minus option touchpoints per 1,000) | Activation volume; touchpoint counts | OQ-004, OQ-008 |
| V4 First-payroll error cost avoided | Newly activated employees multiplied by (baseline first-payroll error rate minus option rate) multiplied by average correction cost | Error rates; correction cost, including any penalties or adjustments | OQ-005, OQ-006 |
| V5 Time-to-value gain | Clients activated multiplied by days of earlier go-live multiplied by value per client-day of earlier revenue recognition | Go-live dates; recognition terms | OQ-006 |
| V6 Retention effect | Change in early churn rate multiplied by clients in cohort multiplied by contract value | Churn data with attribution to activation | OQ-006, OQ-012 |
| Incremental AI value | (V1 to V6 under OPT-2 minus V1 to V6 under OPT-1) minus the incremental AI cost of evaluation data, model usage, monitoring, human review effort and governance | Paired measurements for OPT-1 and OPT-2; AI cost lines | DEC-014, OQ-011 |
| Total delivery cost | Cost to build and operate the option, by option | Engineering and operating estimates | Out of Task 01; requires solution architecture approval |

Rules for using this methodology: never present an output as a forecast without stating its inputs; never compute V1 to V6 against assumed baselines; and report the incremental AI value separately from the OPT-1 value.

## 7. Business Model Canvas reference

The canvas in the blueprint section 2 is authoritative and is not duplicated here. Two canvas assumptions affect this business case directly: value is realised through the existing payroll offering rather than a new revenue stream (ASM-002), and the reduction in implementation effort and operating cost can be quantified (ASM-003). Neither is validated.

## 8. Approval readiness

Blocking business-case approval:

- DEC-001 primary statutory jurisdiction.
- DEC-002 customer segment scope.
- DEC-005 KPI baselines, cohorts, windows and calculation rules.
- DEC-006 blocking, warning and batch-stop policy.
- DEC-007 authorization and approval model.
- OQ-001 business sponsor and approval authority.
- OQ-004, OQ-005 and OQ-006 volumes, baselines and financial parameters.

Not blocking approval of the business case, but blocking implementation: DEC-008, DEC-009, DEC-013, DEC-015 and DEC-016.
