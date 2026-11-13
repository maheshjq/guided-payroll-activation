# Presentation Walkthrough: Guided Payroll Activation

Suggested length: 20 to 25 minutes plus questions. Audience: business sponsors, product and delivery leads, and technical stakeholders. The story below is illustrative and should be replaced with a real client example where one exists. All figures except the targets from the problem statement are placeholders.

## Opening story (2 minutes)

Meet Priya, a payroll administrator at a company that has just signed a large payroll contract. She has 1,000 employees to activate before the first pay run in three weeks.

She uploads her file and works through the wizard, screen by screen. At the final submission, the system stops. The message reads "Upload failed: Invalid configuration." Somewhere in the file, record 850 has a missing tax identifier, and the whole batch is locked. She cannot tell which row or column is wrong. She calls the implementation team. Two specialists spend days reconciling pay codes by hand. The go-live date slips by weeks.

Pause and ask the audience: how many of you have seen this happen?

Key message: the cost is not one failed record. It is the delay, the delivery effort, and the risk that something slips through and hits the first live payroll.

## Slide 1: The problem (2 minutes)

- Hundreds or thousands of profiles must be activated before live payroll.
- Validation happens late, so one error blocks everyone.
- Errors are vague, not cell-level.
- Mapping and pay code reconciliation are manual.
- Multi-entity rules are assigned by hand.
- No dry run before the hard commit.

Say: payroll leaves no margin for error, so activation is the gatekeeper for compliance and data integrity.

## Slide 2: Why it matters to the business (2 minutes)

- Time to value: go-lives slip from days to months, delaying revenue recognition.
- Cost of delivery: specialists hand-hold every client.
- First payroll failures: latent errors cause wrong pay, missed deductions, and tax filing mistakes.
- Regulatory exposure: penalties and retrospective adjustments.
- Early churn: the first 30 to 60 days shape trust.

Say: this is a revenue, cost, and risk problem, not only a usability problem.

## Slide 3: The vision and targets (1 minute)

Replace the step-by-step wizard with an automated, asynchronous, self-remediating activation engine.

- Cut end-to-end activation time by at least 65%.
- Cut implementation support touchpoints per 1,000 activations by 75%.
- Reach a 99.8% first-time-right rate on the first payroll run.

Say: baselines and measurement windows still need to be agreed, so we treat these as targets, not promises.

## Slide 4: Priya's journey, redesigned (3 minutes)

Retell the story with the new solution, one beat per epic.

1. Prepare: Priya starts a named batch, uploads her file, and selects the company context.
2. Map: the system proposes how her columns match internal fields. She accepts or corrects each suggestion.
3. Validate and simulate: every rule runs immediately and a dry run checks the statutory engines. Record 850 is flagged with its exact row, column, and a suggested fix.
4. Activate: the 999 valid records activate. Only record 850 waits.
5. Remediate: she fixes it, or applies one bulk fix to a whole subsidiary. Corrected records go back through validation, not through the whole wizard.
6. Review: she sees what activated, what changed, and a full history for audit.

Say: nobody restarts, nobody phones the implementation team for a single record.

## Slide 5: The six epics (2 minutes)

Show the flow from the requirements document map: prepare, map, validate and simulate, activate, remediate, review. Point out the loop from remediation back to validation and the note that historical payroll migration is out of scope.

## Slide 6: Solution architecture, the big picture (3 minutes)

Show the one-page diagram (`docs/solution-architecture.svg`). Walk top to bottom:

- Users sign in through the edge layer, protected by Cloud Armor and Identity Platform.
- Six Cloud Run services, one per epic, handle the flow.
- Orchestration with Pub/Sub, Workflows, and Dataflow makes processing asynchronous.
- Data is split by purpose: files in Cloud Storage, records in Cloud SQL or AlloyDB, the remediation queue in Firestore, and history and reporting in BigQuery.
- Security and operations apply across all layers.

Say: the design is serverless-first, so it scales with batch size and costs little when idle.

## Slide 7: How AI helps, and where it stops (2 minutes)

- Gemini on Vertex AI suggests column and pay code mappings, using approved past mappings as context.
- Sensitive values are masked before any model call, and prompts and responses are screened.
- AI only suggests. A person approves, and deterministic rules decide validity.
- Mapping accuracy is measured against a golden dataset over time.

Say: this keeps the speed benefit without handing payroll decisions to a model.

## Slide 8: Security and trust (2 minutes)

- Tenant isolation at the API, database, and storage levels.
- Customer-managed encryption keys, VPC Service Controls, and Sensitive Data Protection for tax IDs and bank details.
- Immutable audit trail with retention locks.
- Target frameworks: SOC 2, ISO 27001, GDPR, and applicable payroll regulations.

Say: payroll data is among the most sensitive a client holds, so security is a design input, not an add-on.

## Slide 9: Delivery plan (2 minutes)

- P0 stories form the first usable release: batch setup, mapping, validation, partial activation, and a basic remediation queue.
- P1 adds bulk fixes, richer simulation, and reporting.
- P2 covers experiments, such as deeper AI assistance.

Say: priorities are recommendations for refinement, not commitments.

## Slide 10: Decisions needed and next steps (2 minutes)

In priority order:

1. Confirm data residency, compliance frameworks, and where the payroll and statutory engines run.
2. Choose the processing model, Cloud Run with Pub/Sub or Dataflow, based on expected batch size.
3. Agree the AI guardrails and evaluation approach.
4. Agree metric baselines and measurement windows.
5. Detail the user journey and acceptance criteria for the P0 stories.

Close with the story: the next time Priya uploads 1,000 employees, record 850 is a ticket in a queue, not a stopped project.

## Likely questions

- How do we know the 65% target is realistic? Baselines are not yet measured. The first action is to agree them.
- What if the AI maps a field wrongly? A person approves every mapping, and validation rules and the dry run still apply.
- Can this handle very large clients? Processing is chunked and asynchronous. Dataflow is available for the largest files.
- Does this replace historical payroll migration? No. Prior pay runs and year-to-date balances are out of scope.
- What does it cost to run? Mostly pay-per-use. A cost model needs real batch volumes.

## Presenter tips

- Open with the story, not the architecture. Return to Priya on slides 4 and 10.
- Keep the architecture slide to three minutes. Offer the detailed diagram for the technical follow-up.
- Have the detailed Mermaid diagram in `tech-stack.md` ready for engineering questions.
