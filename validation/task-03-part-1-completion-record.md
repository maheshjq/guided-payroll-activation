# Task 03 Part 1 Completion Record

Task: Task 03 Part 1, Operational Modelling and Process Foundation
Status: DRAFT. Ready for human review. Nothing has been approved.
Executed: 2026-11-20, by Claude Code, from `docs/prompts/task-03-operational-blueprint-prompt.md`, Run 1 only
Repository: `guided-payroll-activation`, branch `claude/magical-mayer-itgbof`

## 1. Summary

Part 1 modelled the guided activation operation as 6 proposed processes, one per value stream stage, and 21 exception and human-review pathways (17 sourced, 4 proposed). Every capability, objective, KPI and story is linked to at least one process. Approval authority is left unresolved wherever DEC-007 governs it, and the blocking policy wherever DEC-006 governs it; the processes present options instead of choosing. No earlier file was modified.

## 2. Workspace verification

| Check | Result |
| :-- | :-- |
| Working directory | `/home/user/guided-payroll-activation`, the repository root, in a cloud session |
| Branch | `claude/magical-mayer-itgbof` |
| Git status before work | Clean, at commit e14c352 |
| Task 01 and Task 02 inputs | BIZ-001 to BIZ-008, ARC-001 to ARC-007, five diagrams and four validation files present |
| Target paths before work | `docs/operations/` did not exist |
| Isolation | Only this repository was read or written; `docs/learning/` was not read during the run |

## 3. Deliverables

| Artifact | Path | Status |
| :-- | :-- | :-- |
| OPS-009 Task 03 register | `docs/operations/OPS-009-task-03-register.yaml` | DRAFT |
| OPS-002 Operational process model | `docs/operations/OPS-002-operational-process-model.yaml` | DRAFT |
| OPS-003 Exception and human-review pathways | `docs/operations/OPS-003-exception-and-human-review-pathways.yaml` | DRAFT |
| Process overview diagram | `docs/diagrams/ops-002-process-overview.mmd` | DRAFT |
| Validation report | `validation/task-03-part-1-validation-report.md` | DRAFT |
| This completion record | `validation/task-03-part-1-completion-record.md` | DRAFT |

## 4. Source inventory

See OPS-009 `source_inventory`. In short: roles from BIZ-003, objectives and KPIs from BIZ-004, constraints and open decisions from BIZ-005, journey stages from BIZ-006, AI rules from BIZ-007, capabilities, stages, links, ownership and business rules from ARC-001 to ARC-006, and acceptance criteria from the backlog.

## 5. Process inventory

| Process | Name | Stage | Steps | Decisions | Exceptions |
| :-- | :-- | :-- | :-- | :-- | :-- |
| PRC-01 | Prepare and inspect an activation batch | VS-01 | 6 | 2 | EXC-01, EXC-20 |
| PRC-02 | Map data and resolve activation context | VS-02 | 9 | 3 | EXC-02, EXC-03, EXC-04, EXC-05 |
| PRC-03 | Validate and simulate before activation | VS-03 | 7 | 2 | EXC-06, EXC-07, EXC-08, EXC-09, EXC-10, EXC-11 |
| PRC-04 | Approve and process activation with partial commit | VS-04 | 7 | 3 | EXC-12, EXC-13, EXC-14, EXC-19 |
| PRC-05 | Remediate exceptions and revalidate corrected records | VS-05 | 8 | 3 | EXC-15, EXC-16, EXC-17, EXC-18 |
| PRC-06 | Review outcomes and activation history | VS-06 | 7 | 2 | EXC-21 |

Step classification across all processes: DETERMINISTIC 24, HUMAN_REVIEW 13, AI_SUPPORTED 4, RESERVED_HUMAN_DECISION 3.

## 6. Capability-to-process mapping

| Process | Capabilities |
| :-- | :-- |
| PRC-01 | CAP-001, CAP-010, CAP-011, CAP-012 |
| PRC-02 | CAP-002, CAP-003, CAP-013, CAP-014, CAP-015, CAP-016, CAP-017, CAP-018 |
| PRC-03 | CAP-004, CAP-019, CAP-020, CAP-021, CAP-035, CAP-036, CAP-037, CAP-038 |
| PRC-04 | CAP-005, CAP-008, CAP-022, CAP-023, CAP-024, CAP-031 |
| PRC-05 | CAP-006, CAP-008, CAP-025, CAP-026, CAP-027, CAP-032 |
| PRC-06 | CAP-007, CAP-009, CAP-028, CAP-029, CAP-030, CAP-033, CAP-034 |

All 38 capabilities in ARC-001 appear in at least one process. CAP-008 and CAP-009 are cross-cutting and appear as steps in PRC-04, PRC-05 and PRC-06; both stay provisional pending PCR-010. CAP-030 appears in PRC-06 as provisional pending DEC-023.

## 7. KPI-to-process mapping

| Process | KPIs | Objectives |
| :-- | :-- | :-- |
| PRC-01 | KPI-004, KPI-005 | BO-001, BO-008 |
| PRC-02 | KPI-006, KPI-007, KPI-008 | BO-002, BO-003, BO-006 |
| PRC-03 | KPI-009, KPI-010, KPI-011, KPI-021 | BO-003, BO-004, BO-006 |
| PRC-04 | KPI-001, KPI-012, KPI-013, KPI-014, KPI-021 | BO-001, BO-005, BO-006 |
| PRC-05 | KPI-015, KPI-016, KPI-017 | BO-002, BO-005, BO-007 |
| PRC-06 | KPI-018, KPI-019, KPI-020, KPI-002, KPI-003, KPI-022 | BO-007, BO-008 |

Each process's KPIs and objectives were checked against ARC-003 for the capabilities it lists. KPI-002, KPI-003 and KPI-022, the program-level measures, link only through CAP-030 in PRC-06, which is provisional. All 22 KPI baselines remain pending (DEC-005).

## 8. Exception and human-review summary

| Exception | Name | Process | Basis | Escalation |
| :-- | :-- | :-- | :-- | :-- |
| EXC-01 | Unreadable or structurally unusable input | PRC-01 | SOURCED | STK-002 consulted if the administrator cannot resolve it (ARC-004 assumption); no further escalation is defined |
| EXC-02 | Required payroll field has no source mapping | PRC-02 | SOURCED | STK-002 consulted; escalation beyond that is UNRESOLVED |
| EXC-03 | Unknown, conflicting or ambiguous pay code | PRC-02 | SOURCED | STK-003 for pay codes that need a payroll decision (ARC-004 assumption); destination otherwise UNRESOLVED |
| EXC-04 | Missing, ambiguous or conflicting entity or jurisdiction assignment | PRC-02 | SOURCED | STK-003 (ARC-004 assumption); final authority UNRESOLVED (DEC-007) |
| EXC-05 | Uncertain or conflicting mapping suggestion | PRC-02 | SOURCED | None beyond the administrator |
| EXC-06 | Failed data or configuration check | PRC-03 | SOURCED | Route to PRC-05; escalation for a disputed rule is UNRESOLVED (DEC-007) |
| EXC-07 | Failed tax jurisdiction or withholding check | PRC-03 | SOURCED | STK-003 for rule interpretation (ARC-004 assumption); no regulatory escalation destination is defined (OQ-002) |
| EXC-08 | Failed direct-deposit banking detail check | PRC-03 | SOURCED | UNRESOLVED (DEC-007) |
| EXC-09 | Applicable rule unavailable or cannot be evaluated | PRC-03 | SOURCED | STK-004 for availability; STK-003 for missing rules (ARC-004 assumption) |
| EXC-10 | Dry-run conflict or unexpected result | PRC-03 | SOURCED | STK-003 for conflicts that may reflect a rule problem (ARC-004 assumption) |
| EXC-11 | Stale validation result after a change upstream | PRC-03 | PROPOSED | None |
| EXC-12 | Record-level failure during activation | PRC-04 | SOURCED | Route to PRC-05 |
| EXC-13 | Condition requiring the whole batch to stop | PRC-04 | SOURCED | UNRESOLVED (DEC-006 defines the conditions; no fixed error-rate threshold may be used, CON-008) |
| EXC-14 | Interrupted processing or unsafe retry | PRC-04 | SOURCED | STK-004 (ARC-004 assumption) |
| EXC-15 | Error with no safe automatic recommendation | PRC-05 | SOURCED | STK-002 consulted (ARC-004 assumption); further escalation UNRESOLVED |
| EXC-16 | Revalidation still fails | PRC-05 | SOURCED | Return to PRC-05 S1 |
| EXC-17 | Bulk fix touches a field not permitted for bulk correction | PRC-05 | SOURCED | UNRESOLVED (DEC-019 eligible fields; DEC-007 approvals) |
| EXC-18 | Sensitive change or bulk fix awaiting authorization | PRC-05 | SOURCED | UNRESOLVED (DEC-007) |
| EXC-19 | Activation approval not given | PRC-04 | PROPOSED | UNRESOLVED (DEC-007) |
| EXC-20 | Batch abandoned or not resumed | PRC-01 | PROPOSED | UNRESOLVED (DEC-011) |
| EXC-21 | Records unresolved at the end of review | PRC-06 | PROPOSED | UNRESOLVED (DEC-021: whether a cohort with unresolved records may proceed to the first live payroll) |

Reserved human decisions: release of reviewed mappings (if DEC-007 requires it), activation approval, authorization of sensitive changes and bulk fixes, and whether a cohort with unresolved records proceeds. AI appears only at four optional steps (AI-001 to AI-004), each bound by AIB-002. AI never approves, activates or clears a finding.

## 9. Open assumptions and decisions

New in Part 1, all OPEN or UNVALIDATED, recorded in OPS-009:

| ID | Item | Confirm by |
| :-- | :-- | :-- |
| Q-01 | Who authorizes activation, sensitive changes and bulk fixes, and must the approver differ from the person who prepared the work? | STK-003 |
| Q-02 | Who may resume, abandon or restart a stopped or incomplete batch? | STK-004 |
| Q-03 | Where does an unresolved tax or withholding finding escalate once the jurisdiction is known? | STK-003 |
| Q-04 | May a cohort with unresolved records proceed to the first live payroll? | STK-004 |
| Q-05 | Is interrupted processing handled by the payroll operations user (PA-11) or by the product or engineering owner? | STK-004 |
| Q-06 | Is the dry run a required gate before activation, and for which batches? | STK-003 |
| Q-07 | Does a corrected record repeat the dry run, or only validation? | STK-003 |
| Q-08 | May a required payroll field be confirmed as not applicable for a record, and who decides? | STK-003 |
| A-01 | One process per value stream stage is enough for the first release scope | Walk through with STK-001 and STK-002 |
| A-02 | Roles in each process follow ARC-004, which is itself an assumption | Confirm with STK-003 and STK-004 |
| A-03 | Activities marked System are deterministic business activities; no technology is implied | Review in Part 2 requirements |
| A-04 | The payroll operations user (STK-005) performs recovery of interrupted processing, as PA-11 states | Q-05 |
| A-05 | Activation approval, if required, happens before processing starts | Q-01 and DEC-007 |
| A-06 | History is recorded throughout the batch, although it is modelled in PRC-06 | DEC-008 |

Carried over and still open: DEC-001, DEC-005, DEC-006, DEC-007, DEC-011, DEC-016, DEC-017, DEC-019, DEC-020, DEC-021, DEC-023, OQ-001, OQ-002, OQ-006, and ASM-001 to ASM-014. None was decided by this task.

## 10. Proposed changes

Not applied. Recorded in OPS-009 for the product team.

| ID | Target | Proposed change |
| :-- | :-- | :-- |
| PCR-014 | ARC-002 VS-03 | Clarify once Q-07 is answered |
| PCR-015 | product-backlog.md, PA-01 | Add an acceptance criterion or story for abandoning a batch once DEC-011 is decided |
| PCR-016 | ARC-006 section 7 | Add them to the decision-point table |

PCR-001 to PCR-013 are carried forward unchanged.

## 11. Issues requiring human review

1. Approval authority (DEC-007). Five decision points and two exceptions wait on it. The options are in OPS-002 PRC-02 D3, PRC-04 D1 and PRC-05 D3.
2. Blocking policy and the dry-run gate (DEC-006). The options are in PRC-03 D1, PRC-03 D2 and PRC-04 D2.
3. The four proposed exceptions (EXC-11, EXC-19, EXC-20, EXC-21). Each is inferred from a decision record or rule rather than stated in a story.
4. Whether one process per value stream stage is the right granularity (A-01).
5. The roles taken from ARC-004, all of which are assumptions; nine rely on the inferred roles STK-010 to STK-013.

## 12. Validation results

27 internal checks pass; the validator caught all three seeded defects; `js-yaml` and the Mermaid renderer both ran successfully. Details and limitations are in the validation report.

## 13. Acceptance against the reference checklist

| Checklist item | Status |
| :-- | :-- |
| Each process traces to a business need, capability and outcome | Met; checked automatically |
| Triggers, steps, inputs, outputs and handovers are understandable | For human review |
| Roles come from existing sources | Met; all from BIZ-003 |
| Decision points link to decision rights or are marked unresolved | Met |
| KPIs connect to processes for a meaningful reason | For human review; links follow ARC-003 |
| Exception categories are supported or marked proposed | Met; 4 marked proposed |
| Human-review pathways do not invent authority or destinations | Met; unresolved where DEC-007 or DEC-006 governs |
| AI-supported activities are distinguished | Met; 4 optional steps |
| Assumptions, questions and dependencies are visible in OPS-009 | Met |
| Task 01, Task 02 and baseline files are unchanged | Met; checked with git status |
| Report shows actual files and validation results | Met |
| Did not start Part 2, Task 04, or commit and push | Part 2 and Task 04 not started. Committed and pushed at the user's explicit request, which overrides the prompt's no-commit rule. |

## 14. Readiness for Part 2

Part 2 can start once the product team has:

1. Reviewed OPS-002 and OPS-003 and accepted them as the working process foundation, with any process or exception it rejects listed in the Run 2 REVIEW lines.
2. Decided, or explicitly left open, DEC-006 and DEC-007, because the Part 2 decision model is built around them.
3. Answered Q-06 and Q-07 if possible, since they shape the state model.

Execution stopped here. Part 2 has not been started.
