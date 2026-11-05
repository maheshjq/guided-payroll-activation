# guided-payroll-activation

Product discovery documentation for improving bulk guided activation of employee profiles in a payroll management system.

This repository contains documents only. It has no source code. The content is an AI-generated draft and requires review and refinement by the product team before it is treated as a commitment.

## Problem summary

During enterprise onboarding, tenant provisioning, or organizational restructuring, hundreds or thousands of employee profiles must be activated before live payroll. The current wizard-based process is slow, manual, and fragile. Validation fails late and cascades across the batch. Errors are opaque. Multi-entity rules are mapped by hand. There is no dry-run capability.

The proposed direction is an automated, asynchronous, self-remediating activation engine with smart data mapping, a pre-activation dry run, partial batch commit with error isolation, and row-and-column diagnostics with bulk fixes.

## Target outcomes

- Reduce end-to-end activation cycle time by at least 65%.
- Reduce implementation support touchpoints per 1,000 employee activations by 75%.
- Achieve a 99.8% first-time-right payroll run rate for newly activated cohorts.

Baselines, cohort definitions, and measurement windows still need to be agreed.

## Scope

In scope: preparing and mapping activation data, resolving activation context, pre-activation validation and simulation, asynchronous processing, exception remediation, and results review.

Out of scope: migration of historical payroll records, such as prior pay runs and year-to-date balances.

## Document guide

Read in this order for the full picture.

| Document | Purpose |
| :-- | :-- |
| [Problem statement](./Problem%20statement.md) | Source of the problem, bottlenecks, impact, and success targets |
| [Business Model Canvas to Business Architecture Blueprint](./Business%20Model%20Canvas%20to%20Business%20Architecture%20Blueprint.md) | Value, stakeholders, capabilities, and boundaries |
| [Requirements document map](./requirements-document-map.md) | Diagram of how the documents and epics relate |
| [Product backlog](./product-backlog.md) | Prioritized user stories (P0 to P2) across all epics |
| [Tech stack and architecture](./tech-stack.md) | Proposed Google Cloud stack, security posture, and Mermaid architecture diagram |

## Epics

The epic sequence represents the user journey. Engineering dependencies may differ.

1. [Prepare a Guided Activation Batch](./epic-01-guided-activation-batch-setup.md)
2. [Map Data and Resolve Activation Context](./epic-02-map-data-and-resolve-activation-context.md)
3. [Validate and Simulate Guided Activation](./epic-03-validate-and-simulate-guided-activation.md)
4. [Process Batches Asynchronously and Partially Activate](./epic-04-process-batches-asynchronously-and-partially-activate.md)
5. [Remediate Activation Exceptions](./epic-05-remediate-activation-exceptions.md)
6. [Review Activation Results and History](./epic-06-review-activation-results-and-history.md)

Eligible records flow from validation to processing. Records with errors flow to remediation and return to validation, so a single bad record does not force a restart of the whole batch.

## Priority legend

- P0: foundational for a usable first release.
- P1: important follow-on scope.
- P2: optional discovery or experiment.

## How these documents were produced

The documents were generated through a sequence of prompts:

1. Understand the workspace contents.
2. Identify the epics for the business problem.
3. Identify the features for each epic.
4. Write the user stories as a product backlog.
5. Explain the user journey, workflow, and end-to-end process for a prioritized epic.

Step 5 has no dedicated document yet.

## Suggested next steps

1. Document the user journey and end-to-end workflow for a prioritized epic.
2. Break the P0 stories into testable requirements and acceptance criteria.
3. Define architecture, security, and evaluation details.
4. Agree on metric baselines and measurement windows.
