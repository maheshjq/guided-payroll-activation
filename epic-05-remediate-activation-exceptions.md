# Epic 5: Remediate Activation Exceptions

## Outcome

Users can understand and correct activation errors at the affected record or field, then revalidate and continue without restarting the whole batch.

## Problem trace

The problem statement identifies opaque aggregated errors, manual reconciliation across confirmation screens, and the need for row-and-column diagnostics, corrective recommendations, and bulk fixes.

## Primary users

- Client payroll administrators
- Implementation specialists

## Scope

- Present invalid or unresolved records in an activation remediation workflow.
- Identify affected rows and fields where available and explain the issue.
- Allow supported corrections and bulk fixes for eligible fields.
- Revalidate corrected data before allowing it to proceed.
- Keep unresolved records distinct from records that have completed activation.

## Acceptance criteria

- An error is actionable and points to the affected record and field when that information is available.
- Users can locate records requiring correction without reprocessing the entire batch.
- A bulk fix makes its affected records and fields clear before it is applied.
- Corrected records are revalidated before activation.
- The workflow does not silently alter sensitive or unrelated employee data.

## Out of scope

- Automatically changing sensitive compensation, tax, identity, or banking values without authorized review.
- Prescribing one-click fixes for every error category.
- Defining approvals or batch-wide suspension thresholds not stated in the problem statement.

## Measures

Track time to resolve activation exceptions, remediation completion rate, and support touchpoints associated with error correction.

## Open decisions

- Which fields and error classes support bulk remediation?
- Which corrections require additional authorization?
- How should the workflow present errors that have no safe automatic recommendation?
