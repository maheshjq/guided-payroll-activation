# Requirements Document Map

This diagram shows how the current project documents relate: the verified problem statement establishes the need, the business model and architecture blueprint frame the response, and the epics organize the guided-activation work.

```mermaid
flowchart TD
    PS["Verified problem statement<br/>Why change? What hurts? What outcomes matter?"]
    BB["Business Model Canvas + Business Architecture Blueprint<br/>Who benefits? What value? What capabilities and boundaries?"]
    PS --> BB

    subgraph EPICS["Six epics — work to deliver guided activation"]
        E1["1. Prepare activation batch"]
        E2["2. Map data and resolve activation context"]
        E3["3. Validate and simulate"]
        E4["4. Process asynchronously and partially activate"]
        E5["5. Remediate exceptions"]
        E6["6. Review results and history"]

        E1 --> E2 --> E3
        E3 -->|"Eligible records"| E4
        E3 -->|"Records with errors"| E5
        E5 -->|"Corrected records"| E3
        E4 --> E6
        E5 --> E6
    end

    BB --> EPICS

    AI["Optional AI assistance<br/>May suggest mappings in Epic 2;<br/>does not approve or activate records"]
    AI -.-> E2

    NEXT["Next refinement<br/>Break epics into stories and testable requirements;<br/>define architecture, security, and evaluation details"]
    EPICS --> NEXT

    OUT["Outside current scope<br/>Full historical payroll migration<br/>(e.g., prior pay runs and year-to-date balances)"]
    BB -.-> OUT

    TARGETS["Program success measures from the problem statement<br/>65% faster activation · 75% fewer support touchpoints<br/>99.8% first-time-right payroll runs"]
    E6 --> TARGETS
```

## How to read this

- The **problem statement** is the source of the verified problem and program-level success targets.
- The **Business Model Canvas and Business Architecture Blueprint** describe the guided-activation value and its scope.
- The **epics** break that scope into outcomes. Their sequence represents the user journey; engineering dependencies may differ.
- The remediation loop sends corrected records back through validation; it does not mean restarting the full batch.
- AI is optional and limited to assistive mapping. It does not replace validation or make activation decisions.
- The current focus is **data preparation for activating employee profiles**, not migration of historical payroll records such as prior pay runs or year-to-date balances.

## Related project documents

- [Problem statement](./Problem%20statement.md)
- [Business Model Canvas and Business Architecture Blueprint](./Business%20Model%20Canvas%20to%20Business%20Architecture%20Blueprint.md)
- [Epic 1: Prepare a Guided Activation Batch](./epic-01-guided-activation-batch-setup.md)
- [Epic 2: Map Data and Resolve Activation Context](./epic-02-map-data-and-resolve-activation-context.md)
- [Epic 3: Validate and Simulate Guided Activation](./epic-03-validate-and-simulate-guided-activation.md)
- [Epic 4: Process Batches Asynchronously and Partially Activate](./epic-04-process-batches-asynchronously-and-partially-activate.md)
- [Epic 5: Remediate Activation Exceptions](./epic-05-remediate-activation-exceptions.md)
- [Epic 6: Review Activation Results and History](./epic-06-review-activation-results-and-history.md)
