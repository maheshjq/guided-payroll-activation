# Product Backlog: Bulk Guided Activation

## Purpose and scope

This is a proposed, ordered product backlog for improving **bulk guided activation of employee profiles** during enterprise onboarding, tenant provisioning, or organizational restructuring. It is derived from the verified [Problem statement](./Problem%20statement.md) and the [Business Model Canvas and Business Architecture Blueprint](./Business%20Model%20Canvas%20to%20Business%20Architecture%20Blueprint.md).

The stories cover preparing and mapping activation data, resolving activation context, pre-activation checks, asynchronous processing, exception remediation, and reviewing outcomes. They do **not** cover migration of historical payroll records, such as prior pay runs or year-to-date balances.

Priorities below are initial recommendations for refinement, not commitments. **P0** means foundational for a usable first release; **P1** means important follow-on scope; **P2** means optional discovery or experiment. Dependencies show likely product flow, not a prescribed technical architecture.

## Product-level outcomes

- Reduce end-to-end activation cycle time by at least 65%.
- Reduce professional implementation support touchpoints per 1,000 employee activations by 75%.
- Achieve a 99.8% first-time-right payroll run rate for newly activated cohorts.

These are targets from the problem statement. Baselines, cohort definitions, and measurement windows need to be agreed before evaluating success.

## Backlog

### Epic 1 — Prepare a Guided Activation Batch

#### P0 — PA-01: Start and identify an activation batch

**User story:** As a payroll administrator, I want to start and identify a bulk activation batch so that I can prepare a specific group of employee profiles for guided activation.

**Acceptance criteria**

- Given I start a batch, when it is created, then the workflow identifies the batch and makes its current state visible.
- Given I have multiple batches, when I view them, then I can distinguish the batch I need to continue.
- Given a batch has not completed, when I return to it, then I can see whether it is awaiting input, ready for mapping, processing, or needs attention.

**Dependencies:** None.

#### P0 — PA-02: Upload and inspect batch input

**User story:** As a payroll administrator, I want to provide employee data for a batch and learn whether the input can be read so that I can resolve file-level problems before record processing.

**Acceptance criteria**

- Given an input in a supported format, when I provide it to the batch, then the workflow reports whether its structure can be read.
- Given the input is unreadable or structurally unusable, when inspection finishes, then I receive a specific, actionable explanation rather than a generic upload failure.
- Given the input is structurally usable, when inspection finishes, then I can proceed to mapping and record-level validation.
- Given an input problem occurs, when it is reported, then it is distinguishable from an individual employee-record validation error.

**Dependencies:** PA-01. Supported formats are a product decision to resolve before implementation.

### Epic 2 — Map Data and Resolve Activation Context

#### P0 — PA-03: Review source-to-payroll field mappings

**User story:** As a payroll administrator, I want to review how source columns map to payroll fields so that I can correct mismatches before employee profiles are activated.

**Acceptance criteria**

- Given the batch input is readable, when mapping is presented, then each relevant source field is shown as mapped, unmapped, or requiring review.
- Given a required payroll field has no source mapping, when I review the mapping, then the missing mapping is clearly identified.
- Given I change a mapping, when I save it, then the corrected mapping is used by subsequent validation and simulation.

**Dependencies:** PA-02. Required target fields are a payroll/product decision.

#### P0 — PA-04: Resolve custom pay-code mappings

**User story:** As a payroll administrator, I want to review how source pay codes correspond to supported payroll pay codes so that pay-code mismatches are caught during activation setup.

**Acceptance criteria**

- Given a source pay code has a recognized mapping, when I review the batch, then the proposed corresponding payroll pay code is visible.
- Given a pay code is unknown, conflicting, or ambiguous, when mapping is presented, then it is marked for review and is not silently treated as resolved.
- Given I correct a pay-code mapping, when I continue, then validation uses the reviewed mapping.

**Dependencies:** PA-03. The authoritative pay-code catalogue and mapping rules must be identified.

#### P0 — PA-05: Review entity and jurisdiction assignments

**User story:** As a payroll administrator, I want to review the entity and jurisdiction associated with each applicable employee profile so that the right activation context is used.

**Acceptance criteria**

- Given the batch includes multi-entity or distributed-workforce data, when assignments are resolved, then the applicable entity and jurisdiction are visible for review.
- Given an assignment is missing, ambiguous, or conflicting, when I review results, then the record is flagged for resolution before proceeding.
- Given a setting is inherited or overridden, when I review it, then its effective value and source are identifiable.

**Dependencies:** PA-03. Which settings inherit from parent entities and the authoritative hierarchy source require business decisions.

#### P1 — PA-06: Review optional mapping suggestions

**User story:** As a payroll administrator, I want optional rule- or AI-assisted mapping suggestions so that I can reduce manual reconciliation while retaining control over the final mapping.

**Acceptance criteria**

- Given a suggestion is available, when it is presented, then it is clearly identified as a suggestion and can be accepted, edited, or rejected.
- Given a suggestion is uncertain or conflicting, when it is presented, then the uncertainty is visible and manual review is required.
- Given I have not reviewed a suggestion, when the batch proceeds, then the suggestion alone does not count as an approved mapping.

**Dependencies:** PA-03 and PA-04. This is optional; evaluate against deterministic mapping first and define privacy and accuracy requirements before implementation.

### Epic 3 — Validate and Simulate Guided Activation

#### P0 — PA-07: Run pre-activation validation

**User story:** As a payroll administrator, I want the batch checked before activation so that data and configuration issues can be identified before profiles are committed.

**Acceptance criteria**

- Given mappings and activation context are available, when I run validation, then the batch is checked against the approved applicable rules.
- Given validation finds an issue, when results are shown, then the affected employee record and field are identified when available.
- Given a check fails, when activation eligibility is determined, then the failed check cannot be silently bypassed.
- Given the applicable rule is unavailable or cannot be evaluated, when validation completes, then that limitation is reported rather than shown as a successful check.

**Dependencies:** PA-03, PA-04, and PA-05. Authoritative validation rules and the blocking policy require payroll/compliance decisions.

#### P0 — PA-08: Run a pre-activation dry-run

**User story:** As a payroll administrator, I want to simulate activation before live commit so that I can detect calculation or configuration conflicts without activating employee profiles.

**Acceptance criteria**

- Given the batch has completed the required setup checks, when I run a dry-run, then the workflow reports simulation results before live activation.
- Given a dry-run runs, when it completes, then it has not activated employee profiles or created live payroll effects.
- Given the simulation has limitations, when results are presented, then those limitations are visible to the user.
- Given a simulation identifies a conflict, when results are reviewed, then the affected record and issue are available for remediation.

**Dependencies:** PA-07. The production-equivalent rules and data available to the simulation must be confirmed.

### Epic 4 — Process Batches Asynchronously and Partially Activate

#### P0 — PA-09: Track asynchronous batch progress

**User story:** As a payroll administrator, I want to see batch processing progress after starting activation so that I know whether it is queued, underway, completed, or needs attention.

**Acceptance criteria**

- Given an eligible batch is submitted, when processing takes longer than the initiating interaction, then the batch can continue without requiring the user to keep the wizard open.
- Given processing is underway, when I view the batch, then its current state is visible.
- Given processing finishes or needs intervention, when I view the batch, then the final or attention-required state is shown.

**Dependencies:** PA-07 and PA-08, subject to the approved activation gates.

#### P0 — PA-10: Isolate record failures from eligible records

**User story:** As a payroll administrator, I want an invalid employee record isolated from other eligible records so that one record-level error does not force the entire batch to restart.

**Acceptance criteria**

- Given a batch contains both eligible and invalid records, when processing occurs, then record-level outcomes are tracked separately.
- Given a record-level failure occurs, when the batch continues, then the failure does not erase or hide other records' results.
- Given a record has not passed required checks, when activation occurs, then that record is not activated.
- Given an error requires stopping the whole batch, when processing stops, then the reason and affected scope are reported.

**Dependencies:** PA-07, PA-08, and PA-09. Conditions that stop a whole batch versus isolate a record require business approval.

#### P0 — PA-11: Safely retry interrupted processing

**User story:** As a payroll operations user, I want interrupted processing to be recoverable so that a retry does not create duplicate activation effects.

**Acceptance criteria**

- Given processing is interrupted, when the batch is retried or resumed, then already completed activation effects are not duplicated.
- Given a retry cannot safely proceed, when it is requested, then the workflow reports the issue and does not claim successful completion.
- Given processing is retried, when the outcome is shown, then original and subsequent outcomes remain traceable to the batch.

**Dependencies:** PA-09 and PA-10. Recovery and retry semantics require technical design.

### Epic 5 — Remediate Activation Exceptions

#### P0 — PA-12: Inspect actionable record-level errors

**User story:** As a payroll administrator, I want errors to identify the affected record and field with a useful explanation so that I can correct the right data without guessing.

**Acceptance criteria**

- Given validation or simulation finds an error, when I review it, then the message identifies the affected record and field when available.
- Given a corrective recommendation is available, when it is shown, then it is tied to the reported issue and does not silently change employee data.
- Given an error is not actionable automatically, when it is shown, then the workflow clearly indicates that manual investigation is needed.

**Dependencies:** PA-07 and PA-08.

#### P0 — PA-13: Correct and revalidate an affected record

**User story:** As a payroll administrator, I want to correct an invalid record and revalidate it without restarting the entire batch so that I can continue activation efficiently.

**Acceptance criteria**

- Given a record needs correction, when I update supported data, then the corrected record can be submitted for revalidation.
- Given revalidation succeeds, when the record is eligible, then it can continue through the remaining activation steps.
- Given revalidation still fails, when results are returned, then the current issue is shown and the record remains unactivated.
- Given a record is corrected, when it is processed, then other completed records are not unnecessarily reprocessed.

**Dependencies:** PA-10 and PA-12.

#### P1 — PA-14: Apply a reviewed bulk fix

**User story:** As a payroll administrator, I want to apply an approved correction to multiple eligible records so that I can resolve repeated activation errors efficiently.

**Acceptance criteria**

- Given multiple records have the same eligible issue, when I prepare a bulk fix, then the affected records and fields are visible before application.
- Given I confirm the fix, when it is applied, then only the selected eligible records and fields are changed.
- Given the fix is applied, when processing continues, then affected records are revalidated.
- Given a proposed fix affects a field not permitted for bulk correction, when I attempt it, then it is blocked or routed for the required approval.

**Dependencies:** PA-12 and PA-13. Eligible fields and approval requirements must be defined.

### Epic 6 — Review Activation Results and History

#### P0 — PA-15: Review batch and per-record outcomes

**User story:** As a payroll administrator, I want a clear summary of the batch and each employee record’s outcome so that I know what was activated and what still needs attention.

**Acceptance criteria**

- Given batch processing has started, when I view the batch, then I can distinguish activated, failed, and attention-required records.
- Given a record is not activated, when I view its outcome, then its current reason or next required action is available.
- Given the batch is still processing, when I view the summary, then it is not presented as complete.

**Dependencies:** PA-09 and PA-10.

#### P1 — PA-16: Review activation changes and decisions

**User story:** As an authorized reviewer, I want relevant mapping changes, corrections, validation results, and activation outcomes recorded so that I can investigate how a profile reached its final state.

**Acceptance criteria**

- Given an activation-relevant change or outcome occurs, when it is recorded, then it is associated with the relevant batch and employee record where applicable.
- Given a user is authorized to review the history, when they inspect an outcome, then they can trace it to relevant validation, simulation, and remediation results.
- Given a user is not authorized to view sensitive details, when they inspect history, then those details are not exposed.

**Dependencies:** PA-03, PA-07, PA-08, PA-13, and PA-15. Required audit events, roles, and retention need confirmation.

## Refinement decisions before implementation

1. Select the initial input formats and required employee fields.
2. Identify authoritative pay-code, entity hierarchy, jurisdiction, and statutory rule sources.
3. Define activation-blocking errors, warnings, and whole-batch stop conditions.
4. Define what the dry-run simulates and how its limitations are represented.
5. Confirm authorization for corrections, bulk fixes, and activation approval.
6. Confirm data privacy, access, retention, and audit requirements.
7. Define measurement baselines and calculation rules for the three program targets.
8. Decide whether to test AI-assisted mapping; it is optional and should not block core guided activation.

## Suggested delivery slices

1. **Understandable batch setup:** PA-01, PA-02.
2. **Reviewable activation preparation:** PA-03, PA-04, PA-05.
3. **Pre-commit confidence:** PA-07, PA-08.
4. **Resilient large-batch activation:** PA-09, PA-10, PA-11.
5. **Self-service exception handling:** PA-12, PA-13, then PA-14.
6. **Clear completion and traceability:** PA-15, then PA-16.
7. **Optional mapping experiment:** PA-06, only after requirements and evaluation are agreed.
