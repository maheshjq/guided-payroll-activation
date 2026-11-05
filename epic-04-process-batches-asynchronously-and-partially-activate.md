# Epic 4: Process Batches Asynchronously and Partially Activate

## Outcome

Large guided activation batches can be processed without holding the user in a monolithic wizard, and a failure in one employee record does not automatically prevent other eligible records from activating.

## Problem trace

The problem statement explicitly calls for asynchronous batch processing and partial batch commit, and describes a single invalid record aborting or locking an entire batch.

## Primary users

- Client payroll administrators
- Implementation specialists
- Payroll operations

## Scope

- Process large activation batches asynchronously.
- Show the batch’s processing state and per-record outcome.
- Activate records that have passed required checks, subject to approved business rules.
- Isolate records that cannot proceed without discarding other records’ results.
- Preserve enough processing state to report completion and recover from processing failures safely.

## Acceptance criteria

- The user can see whether the batch is queued, processing, completed, or requires attention.
- A record-level failure does not by itself force valid records to be re-entered or the entire batch to be restarted.
- Only records that satisfy the required activation checks are activated.
- A failed or retried processing operation does not unintentionally create duplicate activation effects.
- The outcome for each record remains associated with its batch.

## Out of scope

- Choosing a specific queue, event broker, or service architecture.
- Suspending a batch at an unapproved fixed error-rate threshold.
- Bypassing compliance checks to increase the number of records committed.

## Measures

Track end-to-end activation cycle time, batch restart frequency, records activated without a full-batch restart, and duplicate-effect incidents. Program targets: 65% lower cycle time and 75% fewer implementation touchpoints per 1,000 activations.

## Open decisions

- Which failures are isolated to a record, and which require stopping the batch?
- What retry and recovery behavior is appropriate?
- What user controls are needed while asynchronous processing is underway?
