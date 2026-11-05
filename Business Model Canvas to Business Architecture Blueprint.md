# Guided Activation: Business Model Canvas and Business Architecture Blueprint

## Purpose and scope

This document translates the verified problem statement into a business model view and a guided-activation architecture blueprint. Its scope is **bulk guided activation of employee profiles during enterprise onboarding, tenant provisioning, or organizational restructuring**.

It does not define a general payroll platform, replace the payroll engine, or claim that proposed capabilities and commercial assumptions have already been implemented or approved. Statements not established by the problem statement are labeled **Assumption to validate** or **Decision required**.

## 1. Business intent

### Problem

The current bulk guided activation workflow is slow, semi-manual, and prone to data discrepancies. Late or sequential validation can make one invalid record block a large batch. Administrators and implementation specialists must manually map data, resolve configuration gaps, and repeat confirmation steps. The workflow lacks pre-activation sandboxing and actionable, record-level error reporting.

### Intended outcome

Improve the guided activation journey so that large employee batches can be prepared, checked, simulated, activated, and remediated with less manual effort and fewer errors—without compromising payroll accuracy or statutory compliance.

### Success measures from the problem statement

- Reduce end-to-end activation cycle time by at least 65%.
- Reduce professional implementation support touchpoints per 1,000 employee activations by 75%.
- Achieve a 99.8% first-time-right payroll run rate for newly activated cohorts.

**Measurement decision required:** Define baselines, cohort boundaries, observation windows, and how each metric is calculated before using these targets to assess delivery.

### Constraints

- Activation setup must preserve payroll data integrity and statutory compliance.
- Validation and simulation must occur before profiles are hard-committed to live payroll.
- Invalid records must be isolated without losing the status of valid records.
- Employee, compensation, tax, benefits, and banking information requires appropriate protection.

## 2. Business Model Canvas

This canvas describes the business model implications of improving guided activation. It does not assume a new standalone product or revenue stream.

| Canvas block | Guided-activation view |
|---|---|
| **Customer segments** | Enterprise payroll customers activating hundreds or thousands of employee profiles during onboarding, tenant provisioning, or organizational restructuring. **Assumption to validate:** Whether the initial target is limited to new customers or also includes existing customers restructuring their organizations. |
| **Value propositions** | Faster, lower-effort bulk activation; earlier detection of configuration issues; continuation of valid records when other records fail; actionable diagnostics and remediation; reduced risk of first-payroll errors. |
| **Channels** | The guided activation workflow through which customer payroll administrators and implementation specialists currently perform bulk setup. **Decision required:** Confirm whether the initial delivery surface is an administrative UI, an API, an implementation workspace, or a combination. |
| **Customer relationships** | A guided, self-service-oriented activation experience with implementation support available for exceptions. This aims to reduce reliance on hands-on support, not eliminate support. |
| **Revenue streams** | No new activation-specific revenue stream is established by the problem statement. **Assumption to validate:** Value is realized through the existing payroll offering by reducing delayed go-lives, onboarding overhead, and early churn. |
| **Key resources** | The existing payroll activation workflow and payroll data model; authoritative validation and statutory capabilities; source-to-target field definitions; secure handling of employee and payroll data; product, engineering, payroll, compliance, and implementation expertise. |
| **Key activities** | Ingest and map activation data; resolve applicable entity and jurisdiction context; validate and simulate before commit; process large batches asynchronously; isolate and remediate errors; activate eligible profiles; provide diagnostics and an audit trail. |
| **Key partners** | No external partner is required by the problem statement. **Decision required:** Identify any source-system, statutory-data, or verification providers that the existing payroll product depends on and that this workflow must integrate with. |
| **Cost structure** | Current implementation and support effort, engineering and operational effort to improve the workflow, and the cost of operating secure batch processing and validation. **Assumption to validate:** Quantify how much implementation effort and operational cost can be reduced. |

## 3. Business architecture blueprint

### Capabilities in scope

1. **Guided batch intake and setup** — accept a bulk activation batch and establish the context required to process it.
2. **Data mapping and normalization** — align source fields and custom pay codes with the payroll system’s expected data.
3. **Entity and jurisdiction resolution** — resolve applicable parent-child entity and jurisdiction context, and surface ambiguity for review.
4. **Pre-activation validation and simulation** — identify syntax, configuration, and statutory conflicts before activation.
5. **Asynchronous batch activation and partial commit** — process large batches without requiring a single all-or-nothing wizard submission; allow eligible valid profiles to proceed while invalid profiles are isolated.
6. **Remediation and bulk fixes** — give administrators actionable record- and field-level errors and a way to correct eligible issues without restarting the entire batch.
7. **Activation diagnostics and audit** — retain the relevant status and change context for review and troubleshooting.

These are capabilities of the **guided activation process**, not a proposal to build a new general-purpose payroll engine.

### Guided activation value stream

1. **Prepare batch** — administrator supplies the employee data and activation context.
2. **Map and resolve** — source fields are aligned to payroll fields; entity, department, and jurisdiction context is resolved or flagged for review.
3. **Validate and simulate** — inline and statutory checks, followed by a pre-activation dry-run, surface issues before commit.
4. **Process activation** — the batch is processed asynchronously; eligible valid profiles can proceed without being blocked by unrelated invalid records.
5. **Remediate exceptions** — invalid records are presented with actionable diagnostics; supported corrections can be applied and revalidated.
6. **Review outcome** — administrators can see batch and profile outcomes and the relevant activation history.

The exact ordering and ability to revisit steps should be confirmed during workflow design. This sequence expresses the required business journey, not a mandated technical architecture.

### Business rules and decision points

- A record with an activation-blocking issue must not be activated.
- An invalid record must not erase or hide the status of other records in its batch.
- Partial commit must preserve all required validation and compliance controls.
- Ambiguous mappings or entity assignments must be made visible for resolution rather than silently guessed.
- Corrections must be checked again before the affected record proceeds.
- **Decision required:** Define which issues block a record, which can be warnings, and which failure conditions can pause or stop a batch.

### Information handled

The activation workflow may process employee identity, compensation, tax withholding, banking, benefit, pay-code, and organizational entity data. Limit access and retention to what is needed for activation, and apply the project’s approved privacy and security controls.

### Roles and governance

- **Payroll administrator:** prepares and reviews activation data, resolves surfaced issues, and initiates or approves activation according to the product’s authorization model.
- **Implementation specialist:** supports customer onboarding and complex exceptions; reducing support touchpoints is a target, not a removal of this role.
- **Payroll/compliance owner:** confirms applicable validation rules and the meaning of activation-blocking conditions.
- **Product/engineering owner:** delivers and operates the guided activation capability and its diagnostics.

**Decision required:** Confirm role permissions, approval requirements for sensitive changes, and audit/retention obligations with the responsible business and compliance owners.

## 4. AI-native engineering boundaries

The problem statement permits AI- **or rule-driven** schema mapping; it does not require AI.

- AI may be evaluated for suggesting source-field or custom-pay-code mappings and explaining validation messages.
- Mapping suggestions must remain reviewable and correctable; uncertain cases must be surfaced, not silently treated as correct.
- Statutory calculations, authoritative compliance decisions, and activation eligibility must use approved deterministic business rules and controls.
- AI output must not bypass validation, user authorization, or activation gates.
- **Decision required:** Select an AI approach only after comparing it with deterministic mapping and defining evaluation data, acceptable error rates, privacy controls, and human review.

## 5. Explicitly out of scope for this blueprint

- Redesigning payroll calculation, payment, tax filing, benefits administration, or the broader employee lifecycle.
- Creating a new pricing, PEPM, or revenue model.
- Promising guaranteed statutory accuracy or zero payroll errors.
- Selecting an event broker, cloud architecture, service boundaries, or external provider before technical discovery.
- Introducing unsupported policies such as a fixed batch error-rate suspension threshold.

## 6. Traceability to the problem statement

| Problem-statement concern or proposed scope | Blueprint response |
|---|---|
| Manual reconciliation of schemas and custom pay codes | Data mapping and normalization |
| Cross-entity dependency mapping | Entity and jurisdiction resolution |
| Late validation and no pre-ingestion sandbox | Pre-activation validation and simulation |
| One invalid record can abort a batch | Asynchronous processing, partial commit, and exception isolation |
| Generic failure notices | Record- and field-level diagnostics |
| Repeated manual correction | Remediation and supported bulk fixes |
| High activation time and support effort; first-payroll errors | Program-level measures retained without assigning unsupported per-capability targets |
