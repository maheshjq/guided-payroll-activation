# Task 02 Completion Record

Task: Task 02, Business Architecture and Capability Modelling
Status: DRAFT. Ready for human review. Nothing has been approved.
Executed: 2026-11-19, by Claude Code, from `docs/prompts/task-02-business-architecture-prompt.md`, run as written
Repository: `guided-payroll-activation`, branch `claude/magical-mayer-itgbof`

This record also serves as the execution record that the prompt's Stage 1 asks for.

## 1. Summary

Task 02 structured the guided activation business architecture into 38 capabilities: 9 at Level 1, 25 at Level 2 and 4 at Level 3. It also produced a six-stage value stream with a revalidation loop and an open boundary, full traceability to Task 01, proposed ownership, 21 dependencies, a consolidated blueprint, and 13 proposed changes. No baseline file and no Task 01 artifact was modified.

Two gaps need a decision. CAP-009, data protection, supports no Task 01 objective (PCR-009). Three capabilities have no backlog story (PCR-011, PCR-012, and CAP-030 pending DEC-023).

## 2. Workspace verification

| Check | Result |
| :-- | :-- |
| Working directory | `C:\Lahiru\AI\git\guided-payroll-activation`, the repository root |
| Branch | `claude/magical-mayer-itgbof` |
| Git status before work | Clean working tree at commit b3c8770; 3 local commits ahead of the remote with no content difference, not pushed by instruction |
| Task 01 inputs | BIZ-001 to BIZ-008, `docs/business/README.md`, both journey diagrams and both Task 01 validation files present |
| Task 01 integrity before work | Task 01 validator re-run: 45 of 45 checks pass |
| Target paths before work | `docs/architecture/` did not exist |
| Isolation | Only this repository was read or written; `docs/learning/` was not read |

## 3. Deliverables

| Artifact | Path |
| :-- | :-- |
| ARC-001 Capability map | `docs/architecture/ARC-001-capability-map.yaml` |
| ARC-002 Value stream | `docs/architecture/ARC-002-value-stream.md` |
| ARC-003 Traceability matrix | `docs/architecture/ARC-003-traceability-matrix.yaml` |
| ARC-004 Capability ownership | `docs/architecture/ARC-004-capability-ownership.yaml` |
| ARC-005 Capability dependencies | `docs/architecture/ARC-005-capability-dependencies.yaml` |
| ARC-006 Business architecture blueprint | `docs/architecture/ARC-006-business-architecture-blueprint.md` |
| ARC-007 Proposed changes to baseline | `docs/architecture/ARC-007-proposed-changes-to-baseline.yaml` |
| Capability map diagram | `docs/diagrams/arc-001-capability-map.mmd` |
| Value stream diagram | `docs/diagrams/arc-002-value-stream.mmd` |
| Dependency diagram | `docs/diagrams/arc-005-capability-dependencies.mmd` |
| Validation report | `validation/task-02-validation-report.md` |
| This completion record | `validation/task-02-completion-record.md` |

## 4. Execution log

| Stage | Work performed |
| :-- | :-- |
| 1 Workspace verification | Verified repository, branch, clean tree and Task 01 integrity; confirmed no file would be modified |
| 2 Capability map | 9 Level 1 capabilities: CAP-001 to CAP-007 unchanged from the blueprint, plus 2 proposed cross-cutting additions. 25 Level 2 and 4 Level 3 capabilities, each with a definition, purpose, source and basis. One criticality note, where the problem statement supports it; maturity not assessed. |
| 3 Value stream | VS-01 to VS-06, following the blueprint's six steps one to one, each with entry and exit criteria from the epic acceptance criteria; exception path and revalidation loop; boundary VSB-01 |
| 4 Mappings | Every capability mapped to bottlenecks, problems, objectives, KPIs, epics, stories, stakeholders, value stream and journey stages, with reverse coverage sections |
| 5 Ownership | Owning, accountable and consulted roles, and a performing role where useful, for all 38 capabilities, from BIZ-003 roles only; all marked as assumptions |
| 6 Dependencies | 21 dependencies (16 at Level 1, 5 at Level 2), one intentional feedback loop, 5 shared capabilities, and links to Task 01 dependencies |
| 7 Blueprint | ARC-006 consolidating intent, value stream, capabilities, concept separation, ownership, 9 business rules, 8 decision points, information handled, governance, AI boundaries, dependencies and comparison with the existing blueprint |
| 8 Traceability | All objectives, bottlenecks, KPIs, epics and stories are supported by at least one capability; 46 automated checks |

## 5. How the prompt's gaps were handled

The prompt was run as written, as instructed. Four points it left open were resolved inside the outputs and are recorded here for review.

| Point | Handling |
| :-- | :-- |
| CAP numbering. The prompt says "CAP-001 and onward, starting from CAP-001 to CAP-007", but BIZ-008 already defines CAP-001 to CAP-007 | CAP-001 to CAP-007 keep their Task 01 names and objective links, which the validator checks. ARC-001 is the canonical definition, and new capabilities start at CAP-008. The temporary double definition with BIZ-008 is recorded as PCR-007 and is the only exception the validator allows. |
| PCR-001. The prompt says PCR-001 to PCR-005 remain unapplied, but commit 523844d already applied PCR-001 | Carried forward with status APPLIED_OUTSIDE_TASK_02 and the commit as evidence, with a note for you to confirm and close |
| Hand-off to the first live payroll. The prompt's Stage 3 runs the value stream to "reviewed results and hand-off" | Modelled as boundary VSB-01, with no capability assigned, because DEC-021 is open |
| Committing. The prompt is silent on committing | Nothing was committed or pushed |

## 6. Decisions and questions carried over

DEC-022 was decided in the Task 02 authorisation: the stack is a proposal, not a constraint. It is recorded as a proposed status update (PCR-006) because BIZ-005 still shows it as OPEN. Every other item remains OPEN.

### Decisions

| ID | Decision | Decide by | Effect on Task 02 |
| :-- | :-- | :-- | :-- |
| DEC-001 | Statutory jurisdiction | STK-010 | CAP-017 and CAP-036 carry no jurisdiction or rule set |
| DEC-002 | Customer segment scope | STK-010 | None on the capability structure |
| DEC-003 | Delivery surface | STK-004 | None; the architecture is surface-neutral |
| DEC-004 | Integration providers | STK-004 | None; no provider is named |
| DEC-005 | KPI baselines, cohorts and rules | STK-010 | CAP-030 cannot measure until decided |
| DEC-006 | Blocking, review and stop policy | STK-003 | CAP-020 and CAP-023; routing to VS-05 |
| DEC-007 | Permissions and approvals | STK-003 | CAP-031 and CAP-032; approval in VS-04 and VS-05 |
| DEC-008 | Recorded events, visibility and retention | STK-011 | CAP-029, CAP-033 and CAP-034 |
| DEC-009 | Input methods, formats and fields | STK-004 | CAP-011 |
| DEC-010 | Required activation context | STK-004 | CAP-012; exit from VS-01 |
| DEC-011 | Resume or abandon a batch | STK-004 | CAP-010 |
| DEC-012 | Required fields and pay-code mappings | STK-003 | CAP-013 and CAP-014 |
| DEC-013 | Inheritance and hierarchy source | STK-003 | CAP-016 |
| DEC-014 | Deterministic or AI-assisted mapping | STK-004 | AI-001 and AI-002 on CAP-013 and CAP-014 stay optional |
| DEC-015 | Authoritative rules and statutory engine | STK-003 | CAP-019 and CAP-035 to CAP-038 |
| DEC-016 | What the dry run reproduces | STK-003 | CAP-021 |
| DEC-017 | Retry and recovery behaviour | STK-004 | CAP-024 |
| DEC-018 | User controls during processing | STK-004 | CAP-022 |
| DEC-019 | Bulk-remediation eligibility | STK-003 | CAP-027 |
| DEC-020 | Errors with no safe recommendation | STK-004 | CAP-025 and CAP-026 |
| DEC-021 | Hand-off to the first live payroll | STK-004 | VSB-01 stays a boundary |
| DEC-022 | Stack proposed or selected | Decided in the Task 02 authorisation: a proposal | PCR-006 records the status update; Task 02 is technology-neutral |
| DEC-023 | Reporting against targets in scope | STK-004 | CAP-030 is provisional |

### Questions

| ID | Question | Answer by |
| :-- | :-- | :-- |
| OQ-001 | Business sponsor and approval authority | Product leadership |
| OQ-002 | Applicable statutory and regulatory obligations | STK-003 |
| OQ-003 | Evidence for the bottlenecks and root-cause hypotheses | STK-004 |
| OQ-004 | Activation volumes and batch sizes | STK-004 |
| OQ-005 | Current cycle time, touchpoints, effort and first-time-right rate | STK-004 |
| OQ-006 | Financial parameters | STK-010 |
| OQ-007 | Owner of data protection and security | Product leadership |
| OQ-008 | Definition of a support touchpoint | STK-002 |
| OQ-009 | Start and end of activation cycle time | STK-004 |
| OQ-010 | First-time-right definition and cohort boundary | STK-003 |
| OQ-011 | Existing AI governance framework | STK-012 |
| OQ-012 | Measuring early churn and brand trust | STK-013 |

### Assumptions carried over

ASM-001 to ASM-014 remain unvalidated. Task 02 adds one class of assumption: all 38 ownership assignments in ARC-004. Nine of them rely on the inferred roles STK-010 to STK-013, so they are doubly provisional. CAP-008, CAP-009 and CAP-030 are proposed or provisional capabilities, not baseline.

## 7. Items requiring confirmation

| Confirming party | Items |
| :-- | :-- |
| Product team | The capability map as a whole; PCR-007, PCR-008 and PCR-010; CAP-008 and CAP-009 as capabilities; ownership in ARC-004; PCR-001 closure |
| Payroll or compliance owner | BR-001 to BR-009 as business rules; CAP-020, CAP-031 and CAP-032 ownership; CAP-035 to CAP-038 as validation scope |
| Security and data protection | CAP-009, CAP-033 and CAP-034; PCR-009 and PCR-013 |
| Business sponsor | CAP-030 and DEC-023; PCR-006 for DEC-022 |

## 8. Issues and limitations

- The authorised validation tools did not run. Part A authorises `npx js-yaml` and `npx -p @mermaid-js/mermaid-cli mmdc`, but the session's permission system blocked the first npx call. I did not attempt a workaround. YAML was checked with the strict-subset parser from Task 01, and Mermaid for structure only. Allowing npx in your Claude Code permission settings would let both run.
- Four artifacts, the three diagrams and the generated tables were produced by a generator script from one data definition, to keep them consistent. The generator and the validator are in the session scratchpad, not the repository, so they cannot be re-run from the repository alone.
- The ownership assignments follow the role descriptions in the blueprint and BIZ-003, but no organization chart or responsibility matrix exists to confirm them.
- Criticality is noted for one capability only, and maturity is not assessed, because no source supports more.
- The technology-neutrality scan is keyword-based and cannot detect an implied technology choice.

## 9. Acceptance criteria status

| Criterion | Status |
| :-- | :-- |
| Capability map is hierarchical and sourced | Met; 3 levels, every capability sourced |
| Value stream is defined | Met; 6 stages, exception path, boundary |
| Capabilities mapped to objectives, problems, epics and stakeholders | Met; all objectives, bottlenecks, epics and stories covered |
| Ownership and dependencies documented | Met; every ownership assignment is an assumption |
| Blueprint consolidated | Met; ARC-006 |
| Proposed changes listed | Met; 13 in ARC-007 |
| Validation done or limitations reported | Met; authorised tools blocked, as reported in section 8 |
| Readiness for the next task assessed | Met; section 10 |

All criteria are met in draft form. Meeting them is not approval.

## 10. Readiness for the next task

The next task is the operational blueprint, requirements and decision modelling. It can start once the product team has done three things.

1. Accepted ARC-001 as the canonical capability map, including the decision on CAP-008 and CAP-009 (PCR-010).
2. Accepted ARC-002 as the value stream that the operational blueprint will detail.
3. Confirmed or replaced the ownership assignments for at least the rule-bearing capabilities CAP-020, CAP-023, CAP-031 and CAP-032, because the decision models will be built around them.

The next task is where DEC-006 and DEC-007 would normally be worked out, but they still need an accountable payroll or compliance owner to decide them. It should not invent the blocking or approval policy.

Execution stopped here. The next task has not been started. Nothing has been committed or pushed.
