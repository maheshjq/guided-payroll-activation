# TASK 3 — PART 3

**Operational Modelling and Process Foundation**

*Beginner-friendly classroom guide and exact Claude Code prompt*

| How to read the titleThis is the third classroom guide/document in the sequence. The activity described by the supplied prompt is Task 3 — Part 1, titled “Operational Modelling and Process Foundation”. |
| :---- |

# **1\. What are we doing in this task?**

Tasks 1 and 2 established the business problem, intended outcomes, business architecture, capabilities and KPIs. Task 3 starts translating that business-level understanding into a practical description of how work is carried out.

Operational modelling explains the work: what starts a process, what activities happen and in what order, which roles participate, what information is needed and produced, where decisions and handovers occur, and what happens when the normal process cannot continue.

| A simple distinctionA capability describes what the organisation needs to be able to do. A process describes how work is carried out to exercise that capability. An exception pathway explains what happens when something goes wrong or a person needs to review or decide. |
| :---- |

# **2\. What will you create?**

| Deliverable | In simple terms | Purpose |
| :---- | :---- | :---- |
| **OPS-009 — Task 3 Register** | A tracker for Task 3 deliverables, status, sources, dependencies, assumptions, questions and validation. | Shows what is planned, created and still outstanding. |
| **OPS-002 — Operational Process Model** | A structured description of business processes and their steps. | Explains how the business work is performed. |
| **OPS-003 — Exception and Human-Review Pathways** | A structured description of exceptions, non-standard situations, referrals and human-review points. | Makes exception handling and human accountability visible. |

# **3\. Important concepts**

**Process:** A connected sequence of activities that turns a trigger and inputs into an outcome.

**Trigger:** The event that starts a process, such as receiving a request or a completed submission.

**Precondition:** Something that must be true or available before a process or step can begin.

**Role:** A business role that performs an activity or holds responsibility. Use roles found in the project's source artefacts; do not invent them.

**Input and output:** Information or items needed by a process, and the information or result it produces.

**Decision point:** A point where information is assessed and an outcome is selected. Identify who has authority; an AI recommendation is not automatically an authorised decision.

**Handover:** A transfer of work or responsibility between roles, processes or capabilities.

**Exception:** A situation that interrupts or changes the normal process, such as missing or conflicting information.

**Human review:** A point where a person must examine information, exercise judgement or make a decision.

**Deterministic activity:** An activity carried out according to explicit rules or fixed conditions.

**AI-supported activity:** An activity where AI may assist with interpretation, summarisation, classification, prediction or recommendations within approved boundaries.

# **4\. How the three deliverables fit together**

1. Create OPS-009 first. It is the register for tracking the Task 3 work; it is not proof that the work is complete.  
2. Create OPS-002 to describe the normal operational processes. Connect processes to the existing business domains, capabilities, objectives, KPIs, roles and information.  
3. Create OPS-003 to describe what happens when the normal process is interrupted, an exception occurs or human review is required.  
4. Check consistency: exceptions should refer to real processes, and all references should use identifiers found in the project artefacts.

# **5\. The workflow in Claude Code**

5. **Inspect the repository —** Read project instructions and the relevant Task 0, Task 1 and Task 2 artefacts. Identify actual file paths and identifier conventions.  
6. **Prepare a source inventory —** List which existing artefacts inform Task 3\. Missing information must be recorded as an open item, not guessed.  
7. **Create the register —** Create OPS-009 first, using the repository's existing metadata and YAML conventions.  
8. **Model the processes —** Create OPS-002 by elaborating existing process definitions where appropriate. Describe business operations, not software.  
9. **Model exceptions and human review —** Create OPS-003, identifying exception triggers, initial handling, review needs, escalation information and unresolved destinations or authority.  
10. **Validate and report —** Check syntax, identifiers, references, traceability, human accountability and the strict boundaries. Report actual file changes.  
11. **Stop for review —** Stop after Part 1\. Do not begin Part 2 until a human has reviewed the outputs and confirmed the next step.

# **6\. What do validation results mean?**

Validation is useful, but it is not the same as business approval. A YAML syntax check can show that a file is well-formed. A reference check can show that an identifier exists. A traceability check can show that a process points to a capability or KPI. None of these alone proves that the process is how the organisation really works.

* PASS means that a particular automated check passed; it does not prove every business statement is correct.  
* DRAFT means the deliverable exists as a draft. File creation alone must not make it complete or approved.  
* Human review is needed to assess whether process steps, roles, decisions, exception categories and mappings make business sense.  
* Keep open questions visible until evidence and an authorised human decision resolve them.

# **7\. Human review checklist**

Before accepting Part 1 as a working foundation, review:

* ☐ Can each process be traced to a real business need, capability or intended outcome?  
* ☐ Are triggers, steps, inputs, outputs and handovers understandable?  
* ☐ Are roles taken from existing project sources rather than invented?  
* ☐ Are decision points linked to the correct decision rights or clearly marked unresolved?  
* ☐ Are KPIs connected to processes for a meaningful reason, not merely because the identifiers exist?  
* ☐ Are exception categories relevant and supported, or clearly marked as proposed?  
* ☐ Are human-review pathways clear without inventing approval authority or destinations?  
* ☐ Are AI-supported activities distinguished from deterministic activities and human decisions?  
* ☐ Are assumptions, questions and dependencies visible in OPS-009?  
* ☐ Were Task 0, Task 1 and Task 2 baseline artefacts left unchanged?  
* ☐ Does the report show actual files changed and validation results?  
* ☐ Did Claude Code stop without starting Part 2, Task 4, committing or pushing?

# **8\. Boundaries to remember**

| This is not technical designDo not select databases, APIs, frameworks, vendors, infrastructure or deployment platforms in this task. The purpose is to model business operations. |
| :---- |

* Do not create a new project or change the original 15-task roadmap.  
* Do not invent missing processes, stakeholders, owners, thresholds, policies or regulatory obligations.  
* Do not present a proposed process as confirmed real-world practice.  
* Do not treat an AI-generated recommendation as an authorised business decision.  
* Do not modify earlier task artefacts, commit or push changes.  
* Do not begin Part 2 automatically; wait for human review and confirmation.

# **9\. Exact Claude Code prompt**

The following prompt is reproduced from the text supplied for this guide. It is intentionally not shortened or rewritten. Copy it into the Claude Code session opened in the relevant project repository.

\# TASK 3 — PART 3  
   
\# Operational Modelling and Process Foundation  
   
\#\# Project context  
   
You are continuing the existing Business-First AI-Native Engineering Project.  
   
The project has completed:  
   
\- Task 0 — Project Bootstrap  
\- Task 1 — Business Problem, Intent and Value Model  
\- Task 2 — Business Architecture and Capability Modelling, including KPI creation  
   
You are now implementing:  
   
\*\*Task 3 — Operational Blueprint, Requirements and Decision Modelling\*\*  
   
The project follows the original 15-task roadmap. Do not create a new project or change the roadmap.  
   
\#\# 1\. Objective  
   
Translate the business architecture established in Tasks 1 and 2 into an operational model.  
   
The purpose is to establish:  
   
\- How the business capabilities operate in practice.  
\- Which operational processes deliver the intended business outcomes.  
\- Which roles participate in each process.  
\- What information enters and leaves each process.  
\- Where decisions, handovers and dependencies occur.  
\- How exceptions and human interventions are managed.  
   
This is an operational modelling exercise, not application implementation or technical solution architecture.  
   
\#\# 2\. Repository inspection and project continuity  
   
Before creating anything, inspect the current repository.  
   
Read the relevant materials from:  
   
\- Task 0 project bootstrap and repository instructions.  
\- Task 1 business problem, business intent, objectives and value model.  
\- Task 2 business architecture and capability models.  
\- Task 2 KPI definitions and measurement specifications.  
\- Existing stakeholder, business domain, capability, value-stream and ownership artefacts.  
\- README.md and CLAUDE.md, if present.  
   
Identify the actual file paths and existing identifier conventions.  
   
Prepare a short source inventory explaining which existing artefacts will inform Task 3\.  
   
Do not invent missing Task 1 or Task 2 artefacts. Report missing or incomplete information as an open item.  
   
\#\# 3\. Implementation principles  
   
Follow these principles:  
   
1\. Use the actual business context established in Tasks 1 and 2\.  
2\. Preserve existing business objectives, capabilities and KPIs.  
3\. Every proposed process must have a business justification.  
4\. Do not invent stakeholders, process owners, policies, thresholds or regulatory obligations.  
5\. Distinguish confirmed facts, assumptions, proposals and unresolved questions.  
6\. Do not introduce specific technologies, databases, APIs, frameworks, vendors or infrastructure.  
7\. Distinguish human activities, deterministic business activities and AI-supported activities.  
8\. Retain human accountability wherever business judgement or approval is required.  
9\. Do not treat an AI-generated recommendation as an authorised business decision.  
   
\#\# 4\. Establish the Task 3 working register — OPS-009  
   
Create the Task 3 Register first.  
   
Suggested location:  
   
\`docs/operations/OPS-009-task-03-register.yaml\`  
   
The register should track:  
   
\- Task 3 deliverable identifiers.  
\- Deliverable names.  
\- Status.  
\- Version.  
\- Source artefacts.  
\- Dependencies.  
\- Outstanding questions.  
\- Assumptions.  
\- Decisions requiring human review.  
\- Validation status.  
   
Use the repository's existing metadata and YAML conventions where available.  
   
Use DRAFT status for newly created artefacts.  
   
Do not mark deliverables complete merely because files have been created.  
   
\#\# 5\. Develop the Operational Process Model — OPS-002  
   
Create:  
   
\`docs/operations/OPS-002-operational-process-model.yaml\`  
   
Identify the operational processes required to deliver the business capabilities defined in Task 2\.  
   
For each process, describe:  
   
\- Process identifier and name.  
\- Business purpose.  
\- Related business domain.  
\- Related business capability.  
\- Related business objective.  
\- Related KPI.  
\- Trigger or initiating event.  
\- Preconditions.  
\- Participating business roles.  
\- Process activities and sequence.  
\- Inputs and outputs.  
\- Business information used.  
\- Decision points.  
\- Handoffs between roles or capabilities.  
\- Exceptions and dependencies.  
\- Human intervention points.  
\- Automation opportunities and limitations.  
\- Related controls and unresolved matters.  
   
Use local step identifiers within each process rather than inventing additional enterprise-wide identifier families.  
   
\#\#\# Process modelling expectations  
   
The process model should explain the actual business operation.  
   
For example:  
   
\- What triggers the process?  
\- Who performs the first activity?  
\- What information is required?  
\- What happens when information is incomplete?  
\- Where does a decision take place?  
\- Who is accountable for that decision?  
\- What happens after the decision?  
\- How is the outcome communicated or recorded?  
   
Ensure that processes collectively cover the important capabilities and business outcomes from Task 2\.  
   
Avoid duplicating existing process definitions. Elaborate existing definitions where appropriate.  
   
\#\# 6\. Develop Exception and Human-Review Pathways — OPS-003  
   
Create:  
   
\`docs/operations/OPS-003-exception-and-human-review-pathways.yaml\`  
   
Identify situations where normal operational processes cannot continue as expected.  
   
Consider:  
   
\- Missing information.  
\- Incomplete submissions.  
\- Conflicting information.  
\- Failed verification.  
\- Unavailable information sources.  
\- Suspected fraud or risk indicators, where relevant to the project.  
\- Process failures.  
\- Customer or stakeholder disputes.  
\- Requests requiring human judgement.  
\- Escalation and referral situations.  
   
For each exception, define:  
   
\- Exception identifier.  
\- Description.  
\- Triggering condition.  
\- Related process.  
\- Initial handling activity.  
\- Responsible or proposed responsible role.  
\- Human-review requirement.  
\- Escalation path.  
\- Permitted outcomes.  
\- Required information.  
\- Resolution evidence.  
\- Related business rules or decisions.  
\- Outstanding questions.  
   
Use local identifiers within the relevant process or exception structure.  
   
\#\#\# Human and AI boundaries  
   
Clearly distinguish:  
   
\- Activities that can be automated deterministically.  
\- Activities where AI can assist.  
\- Activities requiring human review.  
\- Decisions that must remain with an authorised human.  
   
AI may assist with interpretation, summarisation, classification, prediction or recommendations where appropriate to the project.  
   
AI must not independently exercise authority that belongs to a human decision-maker.  
   
Do not invent approval authority or escalation destinations.  
   
\#\# 7\. Validate Part 1  
   
After creating the three deliverables:  
   
\- Check YAML syntax.  
\- Check identifier consistency.  
\- Check references to Task 1 and Task 2 artefacts.  
\- Check capability and KPI traceability.  
\- Check that all major processes have meaningful business justification.  
\- Check exception coverage.  
\- Check human accountability.  
\- Check for invented business facts or unsupported assumptions.  
\- Check that no Task 0, Task 1 or Task 2 baseline artefacts were unintentionally changed.  
   
Update OPS-009 with actual deliverable status and validation results.  
   
\#\# 8\. Final report and checkpoint  
   
Present:  
   
1\. Task 1 and Task 2 source inventory.  
2\. Operational process inventory.  
3\. Capability-to-process mapping.  
4\. KPI-to-process mapping.  
5\. Exception and human-review summary.  
6\. Open assumptions and decisions.  
7\. Files created and their status.  
8\. Validation results.  
9\. Issues requiring human review.  
   
Show the actual file changes.  
   
Stop after Part 1\.  
   
Do not begin Part 2 automatically. Wait for human review and confirmation.  
   
\#\# 9\. Strict boundaries  
   
Do not:  
   
\- Modify Task 0, Task 1 or Task 2 artefacts.  
\- Change the original 15-task roadmap.  
\- Start Task 4 or application implementation.  
\- Select technologies or technical components.  
\- Invent regulatory obligations or business policies.  
\- Resolve decisions without evidence and human confirmation.  
\- Commit or push changes.  
   
The objective is to establish a traceable operational foundation for Part 2\.

# **10\. What happens next?**

Part 1 establishes the operational process foundation and exception pathways. Part 2 continues Task 3 with the remaining requirements, rules, decision model, operational controls, traceability matrix and consolidated operational blueprint, following the project plan. Do not start it until the Part 1 outputs have been reviewed and the next step has been confirmed.

| Part 1 completion checkpointThe goal is not to create the largest possible number of process steps. The goal is a clear, traceable and reviewable operational model grounded in the earlier business artefacts, with uncertainty visible and human accountability preserved. |
| :---- |

