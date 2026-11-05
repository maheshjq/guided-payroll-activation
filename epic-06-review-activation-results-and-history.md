# Epic 6: Review Activation Results and History

## Outcome

Users can understand the outcome of a guided activation batch, see which employee profiles were activated or need attention, and review relevant changes made during setup and remediation.

## Problem trace

The problem statement calls for contextual audit logs and identifies generic failure notices as a major failure mode. Its target outcomes depend on reliable activation and reduced support effort.

## Primary users

- Client payroll administrators
- Implementation specialists
- Authorized payroll/compliance reviewers

## Scope

- Summarize the batch outcome and expose per-record activation status.
- Make validation, simulation, remediation, and activation results available in context.
- Record relevant mapping changes, corrections, and activation outcomes for troubleshooting.
- Apply the project’s approved access, privacy, and retention controls to activation data and history.

## Acceptance criteria

- Users can distinguish activated records from records that failed or still need attention.
- A user can trace an activation outcome to its relevant validation or remediation result.
- Relevant changes and outcomes are recorded with enough context for authorized troubleshooting.
- Sensitive details are not exposed to users who are not authorized to see them.
- History and diagnostic detail follow confirmed retention and privacy requirements.

## Out of scope

- Claiming audit records are immutable or tamper-proof without an agreed design and requirement.
- Defining regulatory retention periods or certification requirements not established by the problem statement.
- A general-purpose analytics or payroll reporting product.

## Measures

Track time to understand batch outcomes, support requests for activation status, and completeness of the agreed activation history.

## Open decisions

- Which actions and outcomes must be recorded?
- Which roles can view each level of detail?
- What retention and export requirements apply to batch history?
