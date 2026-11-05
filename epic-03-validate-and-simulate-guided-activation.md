# Epic 3: Validate and Simulate Guided Activation

## Outcome

Users can identify data and configuration conflicts before activation and run a pre-activation dry-run against the applicable statutory rules.

## Problem trace

The problem statement describes sequential or final-stage validation, lack of pre-ingestion sandboxing, and downstream failures caused by issues that were not detected before live payroll.

## Primary users

- Client payroll administrators
- Implementation specialists
- Payroll/compliance owners

## Scope

- Perform inline and pre-activation validation on mapped employee records.
- Check the relevant payroll configuration and statutory constraints.
- Provide a dry-run or simulation before live activation.
- Distinguish issues that prevent activation from issues that require review or are informational, according to approved rules.

## Acceptance criteria

- Users can validate a batch before activation and review the results.
- Detected issues identify the affected record and field when applicable and explain why they matter.
- The applicable validation outcome is available to the activation decision; failed checks cannot be silently bypassed.
- A dry-run does not activate profiles or create live payroll effects.
- The simulation uses the applicable approved rules and makes limitations visible to users.

## Out of scope

- Replacing or allowing generative AI to override the authoritative statutory rules.
- Guaranteeing that a dry-run eliminates every possible first-payroll issue.
- Defining legal rules or warning-versus-blocking policy without an accountable payroll/compliance owner.

## Measures

Track issues detected before activation, issues first found in the first live payroll, and time to complete validation/simulation. The 99.8% first-time-right payroll run rate is a program target; its definition and measurement window require agreement.

## Open decisions

- Which validation rules and statutory engine are authoritative?
- Which results block activation versus require review?
- What data and conditions must the dry-run reproduce to be useful?
