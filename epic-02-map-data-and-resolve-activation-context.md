# Epic 2: Map Data and Resolve Activation Context

## Outcome

Users can align source employee fields and custom pay codes to the payroll system’s expected fields and resolve the entity or jurisdiction context needed for guided activation.

## Problem trace

The problem statement identifies manual schema and pay-code reconciliation, as well as repetitive, error-prone parent-child entity and jurisdiction assignments.

## Primary users

- Client payroll administrators
- Implementation specialists

## Scope

- Show source-to-target field mapping for the activation batch.
- Identify missing, incompatible, or ambiguous mappings before records proceed.
- Resolve or request review of applicable entity, department, and jurisdiction context.
- Allow users to review and correct mappings and assignments.
- Optionally evaluate AI- or rule-driven suggestions as assistive features; suggestions do not constitute approval.

## Acceptance criteria

- Users can identify which fields and activation-context assignments are mapped, missing, or require review.
- Ambiguous or conflicting mappings and entity assignments are surfaced instead of silently resolved.
- User-approved corrections are available to subsequent validation and simulation steps.
- Any AI-assisted suggestion can be reviewed and corrected before use; no suggestion alone activates a profile.

## Out of scope

- Designing a general-purpose data integration platform.
- Determining statutory rules or calculating payroll results.
- Automatically deciding unresolved legal-entity or jurisdiction relationships.

## Measures

Track manual reconciliation effort, mapping correction rate, and unresolved entity/jurisdiction assignments. The problem-statement targets apply to the overall activation outcome; no mapping-specific threshold is yet defined.

## Open decisions

- Which source fields and pay-code mappings are required?
- Which organizational settings may inherit from a parent entity?
- Should mapping suggestions be deterministic, AI-assisted, or a combination?
- What data and evaluation thresholds are acceptable if AI assistance is tested?
