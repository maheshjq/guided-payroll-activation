# Epic 1: Prepare a Guided Activation Batch

## Outcome

Payroll administrators and implementation specialists can start a bulk guided activation with the employee data and organizational context needed for downstream mapping, validation, simulation, and activation.

## Problem trace

The problem statement focuses on activating hundreds or thousands of employee profiles during enterprise onboarding, tenant provisioning, or organizational restructuring. The workflow currently depends on rigid wizard steps and manual intervention.

## Primary users

- Client payroll administrators
- Implementation specialists

## Scope

- Start and identify a guided activation batch.
- Accept the supported bulk employee data input for activation.
- Capture or select the applicable customer, organization, and activation context.
- Check that the input can be read and provide clear feedback when it cannot.
- Preserve batch progress so later steps do not require restarting the entire wizard after an isolated issue.

## Acceptance criteria

- A user can start an activation batch and see which batch they are working on.
- Unreadable or structurally unusable input is reported with a useful reason rather than a generic upload failure.
- The batch can proceed to mapping and validation when its input is structurally usable.
- The user can distinguish an input/setup problem from a later record-level validation issue.

## Out of scope

- General employee data management outside guided bulk activation.
- Defining supported file formats or external integrations before product discovery.
- Activating profiles before required mapping, validation, and approval steps are complete.

## Measures

Track batch setup completion time and setup-related support touchpoints. The program-level targets are in the [Business Model Canvas and Blueprint](./Business%20Model%20Canvas%20to%20Business%20Architecture%20Blueprint.md); no separate target is established for this epic.

## Open decisions

- Which input methods and formats are supported in the first release?
- What activation context must the user provide before mapping can begin?
- How should an in-progress batch be resumed or abandoned?
