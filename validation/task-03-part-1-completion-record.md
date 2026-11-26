# Task 03 Part 1 Completion Record

Task: Task 03 Part 1, Operational Modelling and Process Foundation
Version: 0.2
Status: DRAFT. Ready for human review. Nothing has been approved.
Executed: 2026-11-26, by Claude Code, from `docs/prompts/task-03-operational-blueprint-prompt.md` (revised)
Repository: `guided-payroll-activation`, branch `claude/magical-mayer-itgbof`

## 1. Summary

This run replaces version 0.1. It answers the review finding that capabilities were not elaborated: OPS-002 now has a capability operations view with one entry for each of the 38 capabilities, and each of the 29 Level 2 and Level 3 capabilities is exercised by steps of its own. The model has 6 processes with 50 steps and 23 exceptions (17 sourced, 6 proposed). Approval authority (DEC-007) and the blocking policy (DEC-006) remain unresolved; the processes present options. No Task 01, Task 02 or baseline file was modified.

## 2. What changed from version 0.1

| Area | Version 0.1 | Version 0.2 |
| :-- | :-- | :-- |
| Capabilities | Listed by ID on processes and steps; one name appeared in the whole model | Capability operations view with a plain description, steps, roles, decisions, exceptions, rules, AI use and open decisions for every capability |
| Steps per capability | 13 capabilities had one step; the four validation checks shared one step, as did entity and jurisdiction, and access and retention | Every Level 2 and Level 3 capability has its own steps; no step is shared |
| Step capabilities | IDs only | ID and name |
| Business domain | Not recorded | Each process names its domain, using the Level 1 capability groups (assumption A-07) |
| Exceptions | 21, linked to process and step | 23, each also naming its capability; adds EXC-22 suspected fraud or risk indicator and EXC-23 stakeholder dispute, both proposed |
| Steps | 44 | 50 (PRC-02, PRC-03 and PRC-06 split) |
| Checks | 27 | 39 |

## 3. Workspace verification

| Check | Result |
| :-- | :-- |
| Working directory | `/home/user/guided-payroll-activation`, the repository root, in a cloud session |
| Branch | `claude/magical-mayer-itgbof` |
| Starting point | Version 0.1 of the Part 1 outputs at commit 2a9f916, and the revised prompt |
| Task 01 and Task 02 inputs | Present and unchanged |

## 4. Deliverables

| Artifact | Path | Version | Status |
| :-- | :-- | :-- | :-- |
| OPS-009 Task 03 register | `docs/operations/OPS-009-task-03-register.yaml` | 0.2 | DRAFT |
| OPS-002 Operational process model, with the capability operations view | `docs/operations/OPS-002-operational-process-model.yaml` | 0.2 | DRAFT |
| OPS-003 Exception and human-review pathways | `docs/operations/OPS-003-exception-and-human-review-pathways.yaml` | 0.2 | DRAFT |
| Process overview diagram | `docs/diagrams/ops-002-process-overview.mmd` | unchanged | DRAFT |
| Validation report | `validation/task-03-part-1-validation-report.md` | 0.2 | DRAFT |
| This completion record | `validation/task-03-part-1-completion-record.md` | 0.2 | DRAFT |

## 5. Source inventory

See OPS-009 `source_inventory`. Roles come from BIZ-003, objectives and KPIs from BIZ-004, constraints and open decisions from BIZ-005, journey stages from BIZ-006, AI rules from BIZ-007; capabilities, stages, links, ownership and business rules from ARC-001 to ARC-006; acceptance criteria from the backlog.

## 6. Process inventory

| Process | Name | Domain | Stage | Steps | Decisions | Exceptions |
| :-- | :-- | :-- | :-- | :-- | :-- | :-- |
| PRC-01 | Prepare and inspect an activation batch | CAP-001 | VS-01 | 6 | 2 | EXC-01, EXC-20 |
| PRC-02 | Map data and resolve activation context | CAP-002, CAP-003 | VS-02 | 10 | 3 | EXC-02, EXC-03, EXC-04, EXC-05, EXC-23 |
| PRC-03 | Validate and simulate before activation | CAP-004 | VS-03 | 11 | 2 | EXC-06, EXC-07, EXC-08, EXC-09, EXC-10, EXC-11, EXC-22, EXC-23 |
| PRC-04 | Approve and process activation with partial commit | CAP-005, CAP-008 | VS-04 | 7 | 3 | EXC-12, EXC-13, EXC-14, EXC-19 |
| PRC-05 | Remediate exceptions and revalidate corrected records | CAP-006, CAP-008 | VS-05 | 8 | 3 | EXC-15, EXC-16, EXC-17, EXC-18 |
| PRC-06 | Review outcomes and activation history | CAP-007, CAP-009 | VS-06 | 8 | 2 | EXC-21, EXC-23 |

Step classification: DETERMINISTIC 30, HUMAN_REVIEW 13, AI_SUPPORTED 4, RESERVED_HUMAN_DECISION 3.

## 7. Capability operations summary

Every capability has an entry in the `capability_operations` section of OPS-002. This table is the short version.

| Capability | Name | Steps | Coverage |
| :-- | :-- | :-- | :-- |
| CAP-001 | Guided batch intake and setup (Level 1 group) | through PRC-01 | Group of 3 |
| CAP-002 | Data mapping and normalization (Level 1 group) | through PRC-02 | Group of 3 |
| CAP-003 | Entity and jurisdiction resolution (Level 1 group) | through PRC-02 | Group of 3 |
| CAP-004 | Pre-activation validation and simulation (Level 1 group) | through PRC-03 | Group of 3 |
| CAP-005 | Asynchronous batch activation and partial commit (Level 1 group) | through PRC-04 | Group of 3 |
| CAP-006 | Remediation and bulk fixes (Level 1 group) | through PRC-05 | Group of 3 |
| CAP-007 | Activation diagnostics and audit (Level 1 group) | through PRC-06 | Group of 3 |
| CAP-008 | Activation authorization and approval (Level 1 group) | through PRC-04, PRC-05 | Group of 2 |
| CAP-009 | Activation data protection (Level 1 group) | through PRC-06 | Group of 2 |
| CAP-010 | Batch identification and lifecycle tracking | PRC-01 S1, PRC-01 S6 | OWN_STEPS |
| CAP-011 | Batch input acceptance and structural inspection | PRC-01 S3, PRC-01 S4, PRC-01 S5 | OWN_STEPS |
| CAP-012 | Activation context capture | PRC-01 S2 | OWN_STEPS |
| CAP-013 | Source-to-payroll field mapping | PRC-02 S1, PRC-02 S2 | OWN_STEPS |
| CAP-014 | Custom pay-code mapping | PRC-02 S4, PRC-02 S5 | OWN_STEPS |
| CAP-015 | Mapping review and approval | PRC-02 S3, PRC-02 S6, PRC-02 S10 | OWN_STEPS |
| CAP-016 | Entity hierarchy resolution and inheritance | PRC-02 S7 | OWN_STEPS |
| CAP-017 | Jurisdiction context assignment | PRC-02 S8 | OWN_STEPS |
| CAP-018 | Ambiguity surfacing and resolution | PRC-02 S9 | OWN_STEPS |
| CAP-019 | Pre-activation data and configuration validation | PRC-03 S1, PRC-03 S2, PRC-03 S8 | OWN_STEPS |
| CAP-020 | Issue severity classification | PRC-03 S7, PRC-03 S11 | OWN_STEPS |
| CAP-021 | Activation dry-run simulation | PRC-03 S9, PRC-03 S10 | OWN_STEPS |
| CAP-022 | Asynchronous batch processing and progress visibility | PRC-04 S1, PRC-04 S3, PRC-04 S6 | OWN_STEPS |
| CAP-023 | Eligible-record activation and record isolation | PRC-04 S4, PRC-04 S5 | OWN_STEPS |
| CAP-024 | Processing recovery without duplicate effects | PRC-04 S7 | OWN_STEPS |
| CAP-025 | Record- and field-level error diagnosis | PRC-05 S1, PRC-05 S2 | OWN_STEPS |
| CAP-026 | Record correction and revalidation | PRC-05 S3, PRC-05 S4, PRC-05 S8 | OWN_STEPS |
| CAP-027 | Reviewed bulk correction | PRC-05 S5, PRC-05 S7 | OWN_STEPS |
| CAP-028 | Batch and record outcome reporting | PRC-06 S1, PRC-06 S2, PRC-06 S8 | OWN_STEPS |
| CAP-029 | Activation history recording | PRC-06 S3, PRC-06 S4 | OWN_STEPS |
| CAP-030 | Activation outcome measurement | PRC-06 S7 | OWN_STEPS |
| CAP-031 | Activation approval | PRC-04 S2 | OWN_STEPS |
| CAP-032 | Sensitive change authorization | PRC-05 S6 | OWN_STEPS |
| CAP-033 | Role-based access to activation detail | PRC-06 S5 | OWN_STEPS |
| CAP-034 | Activation data retention control | PRC-06 S6 | OWN_STEPS |
| CAP-035 | Compensation framework validation | PRC-03 S3 | OWN_STEPS |
| CAP-036 | Tax jurisdiction and withholding validation | PRC-03 S4 | OWN_STEPS |
| CAP-037 | Benefit plan assignment validation | PRC-03 S5 | OWN_STEPS |
| CAP-038 | Direct-deposit banking detail validation | PRC-03 S6 | OWN_STEPS |

Thin coverage: 14 capabilities are exercised by a single step. They now have that step to themselves, but are worth checking in review: CAP-012, CAP-016, CAP-017, CAP-018, CAP-024, CAP-030, CAP-031, CAP-032, CAP-033, CAP-034, CAP-035, CAP-036, CAP-037, CAP-038. CAP-012, CAP-030 and CAP-031 have no backlog story (PCR-011, PCR-012, DEC-023), so their steps rest on the capability definitions only.

## 8. KPI-to-process mapping

| Process | KPIs | Objectives |
| :-- | :-- | :-- |
| PRC-01 | KPI-004, KPI-005 | BO-001, BO-008 |
| PRC-02 | KPI-006, KPI-007, KPI-008 | BO-002, BO-003, BO-006 |
| PRC-03 | KPI-009, KPI-010, KPI-011, KPI-021 | BO-003, BO-004, BO-006 |
| PRC-04 | KPI-001, KPI-012, KPI-013, KPI-014, KPI-021 | BO-001, BO-005, BO-006 |
| PRC-05 | KPI-015, KPI-016, KPI-017 | BO-002, BO-005, BO-007 |
| PRC-06 | KPI-018, KPI-019, KPI-020, KPI-002, KPI-003, KPI-022 | BO-007, BO-008 |

KPI and objective links follow ARC-003 for each process's capabilities. KPI-002, KPI-003 and KPI-022 link only through CAP-030, which is provisional. All baselines remain pending (DEC-005).

## 9. Exception and human-review summary

| Exception | Name | Process | Capabilities | Basis | Escalation |
| :-- | :-- | :-- | :-- | :-- | :-- |
| EXC-01 | Unreadable or structurally unusable input | PRC-01 | CAP-011 | SOURCED | STK-002 consulted if the administrator cannot resolve it (ARC-004 assumption); no further escalation is defined |
| EXC-02 | Required payroll field has no source mapping | PRC-02 | CAP-013, CAP-015 | SOURCED | STK-002 consulted; escalation beyond that is UNRESOLVED |
| EXC-03 | Unknown, conflicting or ambiguous pay code | PRC-02 | CAP-014, CAP-015 | SOURCED | STK-003 for pay codes that need a payroll decision (ARC-004 assumption); destination otherwise UNRESOLVED |
| EXC-04 | Missing, ambiguous or conflicting entity or jurisdiction assignment | PRC-02 | CAP-016, CAP-017, CAP-018 | SOURCED | STK-003 (ARC-004 assumption); final authority UNRESOLVED (DEC-007) |
| EXC-05 | Uncertain or conflicting mapping suggestion | PRC-02 | CAP-013, CAP-014, CAP-015 | SOURCED | None beyond the administrator |
| EXC-06 | Failed data or configuration check | PRC-03 | CAP-019, CAP-035, CAP-037, CAP-020 | SOURCED | Route to PRC-05; escalation for a disputed rule is UNRESOLVED (DEC-007) |
| EXC-07 | Failed tax jurisdiction or withholding check | PRC-03 | CAP-036, CAP-020 | SOURCED | STK-003 for rule interpretation (ARC-004 assumption); no regulatory escalation destination is defined (OQ-002) |
| EXC-08 | Failed direct-deposit banking detail check | PRC-03 | CAP-038, CAP-020 | SOURCED | UNRESOLVED (DEC-007) |
| EXC-09 | Applicable rule unavailable or cannot be evaluated | PRC-03 | CAP-019 | SOURCED | STK-004 for availability; STK-003 for missing rules (ARC-004 assumption) |
| EXC-10 | Dry-run conflict or unexpected result | PRC-03 | CAP-021 | SOURCED | STK-003 for conflicts that may reflect a rule problem (ARC-004 assumption) |
| EXC-11 | Stale validation result after a change upstream | PRC-03 | CAP-019, CAP-026 | PROPOSED | None |
| EXC-12 | Record-level failure during activation | PRC-04 | CAP-023 | SOURCED | Route to PRC-05 |
| EXC-13 | Condition requiring the whole batch to stop | PRC-04 | CAP-023, CAP-022 | SOURCED | UNRESOLVED (DEC-006 defines the conditions; no fixed error-rate threshold may be used, CON-008) |
| EXC-14 | Interrupted processing or unsafe retry | PRC-04 | CAP-024, CAP-022 | SOURCED | STK-004 (ARC-004 assumption) |
| EXC-15 | Error with no safe automatic recommendation | PRC-05 | CAP-025, CAP-026 | SOURCED | STK-002 consulted (ARC-004 assumption); further escalation UNRESOLVED |
| EXC-16 | Revalidation still fails | PRC-05 | CAP-026 | SOURCED | Return to PRC-05 S1 |
| EXC-17 | Bulk fix touches a field not permitted for bulk correction | PRC-05 | CAP-027 | SOURCED | UNRESOLVED (DEC-019 eligible fields; DEC-007 approvals) |
| EXC-18 | Sensitive change or bulk fix awaiting authorization | PRC-05 | CAP-032 | SOURCED | UNRESOLVED (DEC-007) |
| EXC-19 | Activation approval not given | PRC-04 | CAP-031 | PROPOSED | UNRESOLVED (DEC-007) |
| EXC-20 | Batch abandoned or not resumed | PRC-01 | CAP-010 | PROPOSED | UNRESOLVED (DEC-011) |
| EXC-21 | Records unresolved at the end of review | PRC-06 | CAP-028 | PROPOSED | UNRESOLVED (DEC-021: whether a cohort with unresolved records may proceed to the first live payroll) |
| EXC-22 | Suspected fraud or risk indicator in banking details | PRC-03 | CAP-038, CAP-032 | PROPOSED | UNRESOLVED (no investigation procedure or destination is defined; see Q-09) |
| EXC-23 | Stakeholder dispute of a mapping, assignment, finding or outcome | PRC-03 | CAP-018, CAP-020, CAP-028 | PROPOSED | UNRESOLVED (no dispute owner or escalation path is defined; see Q-10) |

Reserved human decisions: release of reviewed mappings (if DEC-007 requires it), activation approval, authorization of sensitive changes and bulk fixes, clearing a suspected risk indicator, and whether a cohort with unresolved records proceeds. AI appears only at four optional steps (AI-001 to AI-004), each bound by AIB-002; it never approves, activates or clears a finding.

## 10. Open assumptions and decisions

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
| Q-09 | What counts as a fraud or risk indicator during activation, for example an unexpected change to banking details, and who investigates it? | STK-012 |
| Q-10 | Who owns a dispute raised by a client or employee about a mapping, assignment, finding or outcome, and how is it escalated? | STK-003 |
| A-01 | One process per value stream stage is enough for the first release scope | Walk through with STK-001 and STK-002 |
| A-02 | Roles in each process follow ARC-004, which is itself an assumption | Confirm with STK-003 and STK-004 |
| A-03 | Activities marked System are deterministic business activities; no technology is implied | Review in Part 2 requirements |
| A-04 | The payroll operations user (STK-005) performs recovery of interrupted processing, as PA-11 states | Q-05 |
| A-05 | Activation approval, if required, happens before processing starts | Q-01 and DEC-007 |
| A-06 | History is recorded throughout the batch, although it is modelled in PRC-06 | DEC-008 |
| A-07 | The Level 1 capability groups in ARC-001 serve as business domains, because the project has no separate domain model | Confirm with STK-004 |

Carried over and still open: DEC-001, DEC-005, DEC-006, DEC-007, DEC-008, DEC-011, DEC-016, DEC-017, DEC-019, DEC-020, DEC-021, DEC-023, OQ-001, OQ-002, OQ-006, and ASM-001 to ASM-014.

## 11. Proposed changes

| ID | Target | Proposed change |
| :-- | :-- | :-- |
| PCR-014 | ARC-002 VS-03 | Clarify once Q-07 is answered |
| PCR-015 | product-backlog.md, PA-01 | Add an acceptance criterion or story for abandoning a batch once DEC-011 is decided |
| PCR-016 | ARC-006 section 7 | Add them to the decision-point table |

Not applied. PCR-001 to PCR-013 are carried forward unchanged.

## 12. Issues requiring human review

1. The capability descriptions in OPS-002 `capability_operations`. They are the main new content; check that each one describes how the work really happens.
2. Approval authority (DEC-007): five decision points and three exceptions wait on it.
3. Blocking policy and the dry-run gate (DEC-006): options are in PRC-03 D1, PRC-03 D2 and PRC-04 D2.
4. The six proposed exceptions (EXC-11, EXC-19, EXC-20, EXC-21, EXC-22, EXC-23), in particular who investigates a risk indicator (Q-09) and who owns a dispute (Q-10).
5. Using Level 1 capabilities as business domains (A-07).
6. Roles taken from ARC-004, which are all assumptions.

## 13. Validation results

39 internal checks pass; all seeded defects were caught; `js-yaml` and the Mermaid renderer both succeeded. Details are in the validation report.

## 14. Self-assessment against the human review checklist

| Checklist item | Self-assessment |
| :-- | :-- |
| Each process traces to a real need, capability or outcome | Met; justification, domain, capabilities and objectives on every process, checked automatically |
| Triggers, steps, inputs, outputs and handovers are understandable | For human review |
| Roles come from existing sources | Met; all roles are from BIZ-003 |
| Decision points link to decision rights or are marked unresolved | Met |
| KPIs connect to processes for a meaningful reason | Partly; links follow ARC-003, but whether each reason is meaningful needs review |
| Exception categories are supported or marked proposed | Met; 6 marked proposed |
| Human-review pathways do not invent authority or destinations | Met; unresolved where DEC-006, DEC-007, Q-09 or Q-10 governs |
| AI-supported activities are distinguished | Met; 4 optional steps |
| Assumptions, questions and dependencies are visible in OPS-009 | Met |
| Earlier artifacts are unchanged | Met; checked with git status |
| Stopped without starting Part 2 or Task 04 | Met. The outputs were committed and pushed at the user's explicit request, which overrides the prompt's no-commit rule. |

## 15. Readiness for Part 2

Part 2 can start once the product team has:

1. Reviewed OPS-002, including the capability operations view, and OPS-003, and accepted them as the working process foundation.
2. Decided, or explicitly left open, DEC-006 and DEC-007.
3. Answered Q-06 and Q-07 if possible, since they shape the Part 2 state model.

The Task 03 Part 2 prompt has not been written; it waits for its learning guide. Execution stopped here.
