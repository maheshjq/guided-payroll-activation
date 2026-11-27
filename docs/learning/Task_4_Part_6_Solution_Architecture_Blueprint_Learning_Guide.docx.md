**TASK 4.3**

# **Solution Architecture Blueprint**

*Learning Guide and Complete Working Analysis Prompt*

**50-Hour AI-Native Engineering Programme**

| Learning purposeTranslate the Task 4.2 Enterprise Architecture View into a coherent, technology-neutral logical solution architecture. Define logical building blocks, their responsibilities and interactions, workflow orchestration, deterministic and AI-assisted boundaries, information flows, integration coordination, governance enforcement and operational failure handling. |
| :---- |

# **1\. Purpose of this learning guide**

Task 4.3 moves the architecture from the enterprise-level view developed in Task 4.2 towards a logical solution blueprint. The focus is on how the proposed onboarding solution is organised and how its responsibilities collaborate—not on selecting products or deciding how the solution will physically be deployed.

The guide is designed to help the learner understand the architectural reasoning, prepare the required analysis, use the supplied prompt effectively, and review the result for traceability, consistency and governance.

# **2\. Position in the Task 4 sequence**

| Activity | Primary question | Expected architectural outcome |
| :---- | :---- | :---- |
| **Task 4.1 — Architecture Requirements Assessment** | What requirements, constraints, assumptions, decisions and gaps shape the architecture? | A classified requirements and constraints assessment. |
| **Task 4.2 — Enterprise Architecture View** | What are the business, application, data, technology, integration and governance domains? | An enterprise-level architecture view and cross-domain relationships. |
| **Task 4.3 — Solution Architecture Blueprint** | How should the onboarding solution be logically organised and how do its parts collaborate? | A technology-neutral logical solution blueprint with traceability and diagrams. |

Key distinction: Task 4.2 identifies enterprise context and solution responsibilities. Task 4.3 organises those responsibilities into logical building blocks and explains their interactions. It does not authorise implementation or technology selection.

# **3\. Learning objectives**

* Explain the difference between an enterprise architecture view and a solution architecture blueprint.  
* Translate SOL-01 to SOL-19 into a traceable set of logical building blocks without assuming one component per SOL.  
* Organise logical responsibilities into useful architecture layers while avoiding premature physical decomposition.  
* Explain the onboarding workflow from VS-01 to VS-08, including alternative outcomes and unresolved decision points.  
* Separate deterministic business processing, AI-assisted advisory work and human-accountable decisions.  
* Trace information concepts INF-01 to INF-22 across producers, consumers and external relationships.  
* Describe the ten material integration relationships using their existing REL identifiers.  
* Map AIB and CTL constraints to logical enforcement points and audit evidence.  
* Describe safe failure and fallback behaviour without inventing unsupported service levels or retry policies.  
* Maintain C/W/A/G/D evidence status, preserve open decisions and respect AUTH-029.

# **4\. What the learner should understand before starting**

## **4.1 Enterprise view versus solution blueprint**

An enterprise architecture view establishes the wider context: business capabilities, enterprise services, information domains, external dependencies, constraints and governance. A solution architecture blueprint takes the proposed solution boundary and defines its internal logical organisation, responsibilities, interactions and control points.

## **4.2 Logical building blocks are not deployment units**

A logical building block describes a coherent responsibility. It does not automatically mean a separate application, microservice, agent, container, database or deployable unit. Several SOL responsibilities may be grouped where the rationale is clear and traceability is retained. Conversely, a responsibility may later be decomposed, but that is not decided by this activity.

## **4.3 Technology-neutrality**

The blueprint may describe generic capabilities such as workflow coordination, information management, identity enforcement or integration coordination. It must not select a cloud, database, SQL implementation, API gateway, message broker, programming language, LLM, container platform or vendor.

## **4.4 Evidence status**

| Code | Meaning |
| :---- | :---- |
| **C** | Confirmed: recorded human decision or binding constraint |
| **W** | Working baseline: accepted for progression, but proposed content |
| **A** | Assumption |
| **G** | Information gap |
| **D** | Decision requiring approval |

Do not upgrade a working proposal, assumption, gap or pending decision into a confirmed fact merely to make the blueprint look complete. Label proposed architectural interpretation separately from source evidence.

# **5\. Inputs and preparation**

Use the following as the source baseline; inspect the detailed artefacts rather than relying only on summaries:

* Task 1: BIZ-001 to BIZ-008 and HRD-001.  
* Task 2: ARC-001 to ARC-008 and HRD-011.  
* Task 3: OPS-001 to OPS-009 and HRD-013, HRD-014 and HRD-016.  
* Task 4.1: Architecture Requirements Assessment working analysis.  
* Task 4.2: Enterprise Architecture View working analysis, including its six domain views, relationship matrix, dependency register and decision/gap register.  
* Project governance instructions, including CLAUDE.md and the current authorisation state.

## **Preparation checklist**

* Confirm AUTH-029 and the permitted read-only scope.  
* Confirm the current source versions and provenance of the Task 1–3 baseline.  
* Have the full Task 4.2 working analysis available.  
* Keep the SOL, BC, PRC, INF, REL, CTL, AIB, DEC, OQ, DEP and TDEC references available for traceability.  
* Record any discrepancies between source artefacts and working analyses; do not silently reconcile them.

# **6\. Recommended learning and analysis sequence**

## **Step 1 — Re-establish scope and governance**

Read the repository instructions, confirm AUTH-029, inspect provenance and establish what is permitted. Do not create or modify repository artefacts.

## **Step 2 — Reconstruct the solution boundary**

Use Task 4.2 to restate the applicant/channel boundary, proposed onboarding solution boundary and modelled external capabilities XC-01 to XC-09. Preserve non-replacement constraints.

## **Step 3 — Build the logical building block catalogue**

Group related SOL responsibilities into coherent logical building blocks. For each, document purpose, responsibilities, SOL/BC/PRC/INF links, interactions, controls, status and open decisions.

## **Step 4 — Organise logical layers**

Use the candidate layers as a starting point, not a mandatory design. Explain layer responsibilities, dependencies and cross-layer interactions.

## **Step 5 — Model workflow and orchestration**

Trace VS-01 through VS-08. Include declined, withdrawn and lapsed outcomes. Keep DEC-005, OQ-104, DEC-012 and DEC-004 open.

## **Step 6 — Separate rules, AI and human authority**

Identify deterministic responsibilities and advisory AI responsibilities. For each AI use, trace inputs, output, receiving responsibility, human review, audit and fallback.

## **Step 7 — Trace information**

Use INF-01 to INF-22 to identify producing and consuming responsibilities, external relationships and controls. Keep sensitivity classifications as unvalidated hypotheses.

## **Step 8 — Define integration coordination**

Cover REL-011, REL-014, REL-017, REL-037, REL-038, REL-077, REL-078, REL-079, REL-076, REL-074 and REL-075. Describe behaviour without inventing interfaces or protocols.

## **Step 9 — Map security and governance enforcement**

Map AIB and CTL constraints to logical enforcement points and evidence. Distinguish binding constraints from proposed mechanisms and unverified enterprise services.

## **Step 10 — Model resilience and failure handling**

Describe safe behaviour for provider, AI, rules, approval, workflow and audit failures. Do not invent recovery targets, retries or service levels.

## **Step 11 — Produce diagrams and traceability**

Create the eight requested Mermaid views and the business-to-solution and AIB enforcement matrices. Ensure diagrams agree with the written catalogue.

## **Step 12 — Review and hand over**

Run the quality checklist, record gaps and decisions, and hand over only what is supported. Confirm Task 4.4 from the official roadmap rather than guessing its scope.

# **7\. Expected outputs and acceptance checks**

* Executive summary and scope/governance statement.  
* Overall logical solution architecture.  
* Logical building block catalogue with complete SOL traceability.  
* Logical architecture layer view.  
* Business workflow and orchestration architecture.  
* Deterministic rules and AI-assisted architecture.  
* Information/data flow matrix covering INF-01 to INF-22.  
* Integration architecture covering the ten material relationships.  
* Security, governance and audit enforcement view.  
* Operational resilience and failure-handling model.  
* Eight consistent Mermaid architecture diagrams.  
* Business-to-solution traceability matrix covering SOL-01 to SOL-19.  
* AIB constraint enforcement matrix covering AIB-001 to AIB-010.  
* Decision, variation-point, dependency and information-gap analysis.  
* Quality review, findings, recommendations and Task 4.4 handover.

## **Completion review**

* ☐ Every SOL-01 to SOL-19 is represented and traceable.  
* ☐ Logical building blocks are not misrepresented as microservices or deployable units.  
* ☐ All ten material integration relationships retain their correct REL identifiers.  
* ☐ AIB-001 to AIB-010 are preserved and have explicit logical enforcement points.  
* ☐ AI cannot be interpreted as having final decision, alert disposition or system-of-record write authority.  
* ☐ Human accountability and deterministic activation controls remain intact.  
* ☐ INF-01 to INF-22 are considered without inventing physical schemas or data products.  
* ☐ External capabilities XC-01 to XC-09 remain modelled and unverified where appropriate.  
* ☐ C/W/A/G/D classifications and open decisions remain visible.  
* ☐ No technology, vendor, interface or protocol has been selected.  
* ☐ No unauthorised repository changes have occurred.

# **8\. Common mistakes to avoid**

* **One SOL equals one microservice:** Not supported. SOLs are solution responsibilities; grouping and deployment remain undecided.  
* **Treating XC-01 to XC-09 as verified systems:** They are modelled external capabilities; existence and interfaces remain A/G unless verified.  
* **Letting AI approve, decline, disposition alerts or activate accounts:** Contradicts binding AI and automation boundaries.  
* **Treating model confidence as proof:** Confidence may support routing only.  
* **Inventing APIs, message brokers or protocols:** The integration architecture is logical and technology-neutral.  
* **Inventing retention, residency or NFR values:** These remain unresolved decisions or information gaps.  
* **Treating proposed architecture as approved:** Task 4.3 remains a working analysis under the stated governance boundary.  
* **Guessing Task 4.4:** Use the official course roadmap or authorised project source.

# **9\. Suggested facilitation and review questions**

* What makes two SOL responsibilities belong in the same logical building block?  
* How can we show workflow orchestration without selecting a workflow product?  
* Where must deterministic rules override AI-generated recommendations?  
* What evidence is needed to reconstruct an AI contribution and a human decision?  
* What happens to the onboarding case when IDV or screening is unavailable?  
* Which decisions can remain variation points without blocking the logical design?  
* How can we prove every SOL and every AIB constraint is represented?  
* Which parts of the blueprint are evidence-based and which are proposed architectural interpretation?

# **10\. Complete Task 4.3 working analysis prompt**

The following prompt is reproduced from the supplied Task 4.3 prompt source and is intended to be used as the working instruction for the architecture analysis. It is included in full so the learning guide and execution prompt remain together.

# **Task 4.3 — Solution Architecture Blueprint**

## **Complete Working Analysis Prompt**

### **1\. Role and Context**

Act as a Senior Enterprise and Solution Architect with expertise in:

* Enterprise and solution architecture  
* AI-native application architecture  
* Banking and financial services  
* Business process orchestration  
* Human-in-the-loop decision systems  
* Data and integration architecture  
* AI governance, security and operational resilience  
* Architecture traceability and design governance

Your task is to develop **Task 4.3 — Solution Architecture Blueprint** for the AI-Native Customer Onboarding solution.

The blueprint must translate the Task 4.2 Enterprise Architecture View into a coherent, technology-neutral logical solution architecture.

You must work strictly from the existing accepted Task 1–3 baseline and the Task 4.1 and Task 4.2 working analyses.

Do not treat working analyses as formally approved architecture artefacts.

### **2\. Governance and Authorisation Boundary**

**Current status: Task 4 learning activity under AUTH-029.**

The work is a read-only architecture learning and analysis exercise.

Before starting:

1. Inspect the relevant project instructions and repository governance rules, including CLAUDE.md.  
2. Confirm the current authorisation status.  
3. Identify the permitted working scope.  
4. Inspect the relevant existing baseline artefacts and their provenance.  
5. Identify any restrictions that affect this activity.

Unless separate explicit authorisation is provided:

* Do not create or modify repository files.  
* Do not create new repository IDs.  
* Do not update existing baseline artefacts.  
* Do not modify YAML specifications, architecture catalogues, ADRs, configuration files or code.  
* Do not stage, commit or push anything.  
* Do not implement the architecture.  
* Do not claim that the blueprint has been formally approved.  
* Do not interpret this task as authorisation to select technologies or configure infrastructure.

You may produce the complete working analysis in the response or a permitted read-only scratchpad.

If the repository instructions conflict with this prompt, follow the higher-priority governance instructions and report the conflict.

### **3\. Authoritative Inputs**

Use the following sources as the architecture baseline.

**Task 1 — Business Architecture**

* BIZ-001 to BIZ-008  
* HRD-001

**Task 2 — Enterprise and Solution Architecture**

* ARC-001 to ARC-008  
* HRD-011

**Task 3 — Operational Architecture**

* OPS-001 to OPS-009  
* HRD-013  
* HRD-014  
* HRD-016

**Task 4.1 — Architecture Requirements Assessment**

Use the working assessment as the requirements and constraints analysis. It is not formally approved.

**Task 4.2 — Enterprise Architecture View**

Use the complete Task 4.2 working analysis as the immediate input to this activity.

It covers:

6. Executive Architecture Overview  
7. Business Architecture View  
8. Application Architecture View  
9. Data Architecture View  
10. Technology and Infrastructure Architecture View  
11. Integration Architecture View  
12. Security and Governance Architecture View  
13. Cross-Domain Architecture Relationship Matrix  
14. Architecture Dependencies and Constraints Register  
15. Architecture Decisions and Information Gaps Register

Do not rely exclusively on the executive summary of Task 4.2. Examine the detailed domain views, relationships, registers and conclusions.

Where source artefacts and working analyses differ, identify the discrepancy and preserve the source provenance. Do not silently reconcile differences.

### **4\. Status Classification**

Preserve the existing evidence classification throughout the blueprint.

\| Code \| Meaning \|

\|---\|---\|

\| C \| Confirmed: recorded human decision or binding constraint \|

\| W \| Working baseline: accepted for progression, but proposed content \|

\| A \| Assumption \|

\| G \| Information gap \|

\| D \| Decision requiring approval \|

Apply these classifications to architecture statements, building blocks, relationships, integration points, security controls and design recommendations.

Do not promote W, A, G or D content to C.

Clearly distinguish:

* Existing baseline facts  
* Confirmed constraints  
* Proposed logical architecture  
* Assumptions  
* Unresolved decisions  
* Information gaps  
* Recommendations requiring human review

Any local references introduced during this analysis must be clearly labelled as local working references. They must not be represented as repository IDs.

# **5\. Task 4.3 Objectives**

Develop a Solution Architecture Blueprint that answers the following questions:

16. How should the proposed onboarding solution be logically organised?  
17. What are the major logical building blocks required to realise SOL-01 to SOL-19?  
18. What responsibilities belong to each logical building block?  
19. How do the building blocks interact to support the onboarding value stream?  
20. How are business rules, AI assistance and human decision-making separated?  
21. How does the solution coordinate with external enterprise capabilities XC-01 to XC-09?  
22. How does information flow between the logical building blocks?  
23. Where are security, governance, audit and operational controls enforced?  
24. How does the architecture handle unavailable external providers and unavailable AI services?  
25. Which architecture decisions and information gaps prevent the blueprint from being finalised?

The blueprint must provide sufficient logical detail for the next engineering activities without prematurely defining implementation components.

# **6\. Required Architecture Design**

## **6.1 Overall Logical Solution Architecture**

Develop an overall logical architecture showing:

* Applicant and channel interaction boundary  
* Onboarding solution boundary  
* Logical application and orchestration responsibilities  
* Deterministic business rule capabilities  
* AI-assisted capabilities  
* Human review and approval responsibilities  
* Information and evidence management  
* Integration and external enterprise capability boundary  
* Security and governance controls  
* Audit and monitoring responsibilities

Show how the proposed onboarding solution sits between the applicant/channel environment and the existing enterprise capabilities.

Preserve the following non-replacement constraints:

* XC-01 Core Banking  
* XC-02 CRM / Customer Master  
* XC-03 Identity Verification

Screening is coordinated rather than replaced, but its existing enterprise capability and implementation must remain unverified.

Do not invent actual enterprise systems or claim that modelled external capabilities are confirmed implementations.

## **6.2 Logical Building Block Identification**

Identify the logical building blocks required to realise the 19 solution capabilities.

Use SOL-01 to SOL-19 as the primary traceability anchors.

For each proposed building block, provide:

\| Attribute \| Required description \|

\|---\|---\|

\| Logical building block ID \| Local working reference, if needed \|

\| Building block name \| Clear architecture-level name \|

\| Purpose \| Why it exists \|

\| Responsibilities \| What it does \|

\| Related SOL IDs \| SOL-01 to SOL-19 \|

\| Related business capabilities \| Corresponding BC identifiers \|

\| Related processes \| Relevant PRC identifiers \|

\| Information handled \| Relevant INF identifiers \|

\| Interactions \| Other logical building blocks and external capabilities \|

\| Controls \| Relevant CTL and AIB identifiers \|

\| Evidence status \| C/W/A/G/D \|

\| Open decisions \| Relevant DEC, OQ, DEP or TDEC references \|

Important:

Logical building blocks are architecture abstractions.

Do not assume that:

* Every SOL must become a separate application.  
* Every logical building block requires a separate service.  
* Every responsibility requires a separate microservice.  
* A logical building block must map to a separate container.  
* A logical building block must map to a particular database or technology product.

Where several SOL responsibilities could reasonably be grouped, explain the architectural rationale and preserve traceability to each SOL.

Where a capability may be supplied by an enterprise shared service, identify that as an unresolved placement decision rather than making the selection.

## **6.3 Logical Architecture Layers**

Organise the proposed solution into logical layers where useful.

Consider the following as candidate architectural groupings, not predetermined implementation layers:

26. Experience and Interaction  
27. Application Intake and Information Processing  
28. Business Rules and Policy Evaluation  
29. AI-Assisted Intelligence  
30. Workflow and Business Orchestration  
31. Human Review and Decision Management  
32. Information and Evidence Management  
33. Enterprise Integration and Coordination  
34. Audit, Monitoring and Governance

For each layer:

* Define its architectural purpose.  
* Identify its logical responsibilities.  
* Map the relevant SOL capabilities.  
* Identify information dependencies.  
* Identify interactions with other layers.  
* Identify applicable security and governance controls.  
* Explain whether the layer is a distinct responsibility or merely a logical grouping.

Do not force all SOL capabilities into these layers if the evidence supports a different arrangement.

## **6.4 Business Workflow and Orchestration Architecture**

Develop the logical workflow architecture using the existing onboarding value stream:

VS-01 Initiate

→ VS-02 Capture

→ VS-03 Interpret and Validate

→ VS-04 Verify and Assess

→ VS-05 Resolve Exceptions

→ VS-06 Decide

→ VS-07 Establish and Activate

→ VS-08 Confirm and Inform

Include the alternative outcomes:

* Declined  
* Withdrawn  
* Lapsed before decision

Explain:

* How the workflow coordinates the logical building blocks.  
* How application state and status are maintained.  
* How work is routed to operational users and reviewers.  
* How exceptions are managed.  
* How approvals and authority checks are enforced.  
* How integration dependencies affect workflow progression.  
* How the solution prevents account establishment before the required checks and approvals.

Explicitly preserve the unresolved decisions:

* DEC-005: Approval matrix and possible rules-only approval path.  
* OQ-104: Referral destinations.  
* DEC-012: Conditional activation.  
* DEC-004: Channels.

Do not invent workflow branches or final authority assignments where the baseline is unresolved.

## **6.5 Deterministic Rules and AI-Assisted Architecture**

Define the separation between deterministic business processing and AI-assisted functions.

**Deterministic responsibilities**

Use the relevant baseline capabilities to identify:

* Eligibility and completeness evaluation  
* Business rule evaluation  
* Policy precedence  
* Risk and validation controls  
* Approval authority enforcement  
* Workflow progression  
* Account establishment control  
* Audit recording  
* Status management

**AI-assisted responsibilities**

Use the existing proposed AI opportunities to identify:

* Applicant guidance  
* Document classification and extraction  
* Capture-quality assistance  
* Data matching and discrepancy explanation  
* Rating explanation  
* Case preparation  
* Work triage  
* Other explicitly supported AI-assisted activities

For each AI-assisted responsibility, define:

35. Purpose.  
36. Input information.  
37. Expected advisory output.  
38. Receiving logical building block.  
39. Human review requirement.  
40. Relevant AI governance controls.  
41. Audit information required.  
42. Fallback behaviour.

Preserve the binding AI constraints:

* AIB-001: AI must not make final decisions.  
* AIB-002: Account establishment must follow the deterministic authorised workflow.  
* AIB-003: Screening alert disposition remains human-accountable.  
* AIB-004: Model confidence is used for routing, not proof of correctness.  
* AIB-005: AI must not have a direct write path to systems of record.  
* AIB-006: Business rules and policy take precedence over AI output.  
* AIB-007: Every AI contribution must be recorded.  
* AIB-008: Customer-supplied content is untrusted data.  
* AIB-009: Manual fallback must be available when AI is unavailable.  
* AIB-010: Customer communications must follow approved templates and validated content slots.

Do not introduce additional AI autonomy or decision-making authority.

## **6.6 Information and Data Architecture**

Use ARC-005 and INF-01 to INF-22 as the information baseline.

Explain:

* Which logical building blocks create information.  
* Which building blocks consume information.  
* Where onboarding-specific information is provisionally mastered.  
* How extracted information retains source linkage.  
* How evidence is assembled for human review.  
* How decisions and AI contributions are recorded.  
* How information is exchanged with external capabilities.  
* How information is made available for operational analytics and governance.

Include a logical information flow matrix:

\| Information ID \| Information concept \| Producing responsibility \| Consuming responsibility \| External relationship \| Relevant controls \| Status \|

Preserve the current data classifications as unvalidated hypotheses.

Do not invent:

* Physical database structures  
* Table definitions  
* SQL schemas  
* Data storage products  
* Retention periods  
* Data residency decisions  
* Encryption implementations  
* Data ownership assignments

Explicitly carry forward:

* OQ-011: Retention periods.  
* DEC-011: Data residency and hosting.  
* DEC-010: Policy and methodology governance.  
* DEP-001: Bank CDD policy, risk methodology and approval matrix.  
* DEP-002: Historical operational data.  
* N-16: Risk methodology version recording gap.  
* TDEC-008: Outstanding audit-path proposals.

## **6.7 Integration and External Coordination Architecture**

Use the existing ARC-005 relationships and REL identifiers.

The blueprint must cover the following integration relationships:

43. REL-011 — Identity verification with XC-03.  
44. REL-014 — Screening with XC-04.  
45. REL-017 — Financial-crime escalation with XC-05.  
46. REL-037 — Account creation and activation with XC-01.  
47. REL-038 — Customer master creation with XC-02.  
48. REL-077 — Consent and privacy with XC-07.  
49. REL-078 — Evidence retention with XC-09.  
50. REL-079 — Approval authority and access with XC-08.  
51. REL-076 — AI governance reporting with XC-06.  
52. REL-074 and REL-075 — Provider service management with XC-03 and XC-04.

For each relationship, describe:

* Business purpose.  
* Triggering process or event.  
* Information exchanged.  
* Sending logical responsibility.  
* Receiving external capability.  
* Criticality.  
* Required response behaviour.  
* Failure and unavailability handling.  
* Relevant security and governance controls.  
* Unresolved dependencies and decisions.

Do not invent APIs, endpoints, message brokers, protocols, interface formats, authentication products or vendor-specific integration patterns.

Treat all external capabilities as modelled capabilities whose actual implementation and interfaces remain A/G unless verified by an authoritative source.

Explicitly address:

* Provider unavailable: pause the affected workflow where required.  
* Failed or inconclusive verification: route to human review.  
* Screening match: human disposition.  
* Escalation: application remains held while unresolved.  
* Account creation: deterministic authorised workflow only.  
* External system writes: no direct AI write path.

Also identify integration gaps not modelled in ARC-005, including notification channels, fraud-signal routes and exception routes. Do not silently add them as confirmed integrations.

## **6.8 Security, Governance and Audit Architecture**

Translate the existing security and governance principles into logical enforcement points.

For each control, explain:

* The logical building block responsible for enforcement.  
* The interaction or workflow point where it applies.  
* The evidence or audit record produced.  
* The related baseline control or constraint.  
* The evidence status.

Cover:

* Identity and access management.  
* Least-privilege access.  
* AI execution boundaries.  
* Human decision accountability.  
* Deterministic activation.  
* Rule and policy precedence.  
* AI monitoring and suspension.  
* Untrusted customer content.  
* Manual fallback.  
* Approved customer communications.  
* Data protection and privacy.  
* Decision auditability.  
* AI contribution traceability.  
* Records retention.  
* External provider governance.  
* Fairness and outcome monitoring.

Make the distinction between:

53. Confirmed governance constraints.  
54. Proposed logical enforcement mechanisms.  
55. Existing enterprise services that are not yet verified.  
56. Decisions and information gaps requiring resolution.

Do not claim regulatory compliance. Applicable obligations and licence category remain unresolved.

## **6.9 Operational Resilience and Failure Handling**

Develop a logical failure-handling model.

At a minimum, consider:

* Identity verification provider unavailable.  
* Screening capability unavailable.  
* Core banking or CRM interface unavailable.  
* AI service unavailable.  
* AI output invalid or inconclusive.  
* Business rule evaluation failure.  
* Approval authority unavailable.  
* Workflow interruption.  
* Incomplete or inconsistent information.  
* Audit recording failure.

For each scenario, specify:

\| Scenario \| Affected capability \| Required system behaviour \| Human involvement \| Workflow status \| Recovery consideration \| Baseline reference \|

Preserve the binding principle that controls must never be skipped to maintain throughput.

Do not invent availability percentages, recovery time objectives, retry policies or service-level thresholds.

Carry forward OQ-008, OQ-009, TDEC-002 and other relevant NFR gaps.

# **7\. Required Visual Architecture Views**

Produce the following diagrams using Mermaid.

All diagrams must be consistent with the textual blueprint.

### **Diagram 1 — Overall Logical Solution Architecture**

Show:

* Actors  
* Experience boundary  
* Logical solution layers  
* Workflow/orchestration  
* Deterministic rules  
* AI assistance  
* Human decision responsibilities  
* Information and audit responsibilities  
* Enterprise integration boundary  
* External capabilities XC-01 to XC-09  
* Security and governance cross-cutting concerns

### **Diagram 2 — Logical Building Block Architecture**

Show the proposed logical building blocks and their relationships.

Map each building block to its relevant SOL identifiers.

Avoid representing each SOL as a separate technical component unless explicitly supported by the architecture evidence.

### **Diagram 3 — Business Workflow and Decision Architecture**

Show the onboarding value stream and alternative outcomes.

Clearly distinguish:

* Deterministic processing  
* AI-assisted advisory activities  
* Human review and approval  
* External verification and screening dependencies  
* Controlled account establishment

### **Diagram 4 — AI and Deterministic Processing Boundary**

Show:

* Customer-provided content  
* Input isolation and validation  
* AI-assisted processing  
* Advisory output  
* Deterministic rules and policy evaluation  
* Human review  
* Workflow progression  
* Audit recording  
* Manual fallback

Make it visually impossible to interpret AI as having final decision or account activation authority.

### **Diagram 5 — Information and Data Flow Architecture**

Show the principal information concepts and their movement across logical building blocks.

Use INF identifiers.

Avoid physical data stores or database products.

### **Diagram 6 — Enterprise Integration Architecture**

Show the ten material integration relationships and their relevant REL identifiers.

Distinguish confirmed constraints from assumed or unverified external capabilities.

### **Diagram 7 — Security and Governance Enforcement Architecture**

Show the cross-cutting controls and the logical points where they are enforced.

Include the relevant AIB and CTL references.

### **Diagram 8 — Operational Resilience and Failure Handling**

Show how the solution responds to provider failures, AI unavailability, invalid results, workflow interruption and other material failure scenarios.

Use Mermaid syntax that renders correctly.

Keep diagrams readable. If one diagram becomes too complex, split it into logical views rather than omitting important relationships.

# **8\. Architecture Traceability**

Provide a consolidated traceability matrix.

At a minimum:

\| Business capability \| Process \| SOL capability \| Logical building block \| Information \| Integration \| Governance control \| Status \|

Ensure SOL-01 to SOL-19 are covered.

Also provide an AIB traceability matrix:

\| AIB ID \| Binding constraint \| Architecture enforcement point \| Logical building block \| Evidence or audit record \| Status \|

The purpose is to demonstrate that the proposed logical architecture is grounded in the accepted baseline rather than invented independently.

Where a relationship cannot be established from the available sources, explicitly mark it as an information gap.

# **9\. Architecture Decisions and Design Variations**

Carry forward the existing open decisions.

At a minimum:

* DEC-002 and DEC-003: Product and segment.  
* DEC-004: Channels.  
* DEC-005: Approval matrix.  
* DEC-007: AI risk appetite and classification.  
* DEC-008: Build, buy or reuse.  
* DEC-010: Risk methodology governance.  
* DEC-011: Data residency and hosting.  
* DEC-012: Conditional activation.  
* DEC-101: Capability ownership.  
* DEC-102: Five pending capabilities.  
* DEC-103: Rule management ownership.  
* DEC-104: AI governance ownership.  
* OQ-104: Referral destinations.  
* OQ-101, OQ-102 and OQ-016: Enterprise capability model and current estate.  
* TDEC-008: Audit-path gaps.

For each decision, explain:

57. What architectural aspect it affects.  
58. Which logical building blocks are affected.  
59. What design alternatives may need to remain open.  
60. What information is required to resolve it.  
61. Whether it blocks further logical design or only final implementation.

Do not make the decisions on behalf of the bank or architecture authority.

Identify architecture variation points so that the blueprint can accommodate future decisions without unnecessary redesign.

# **10\. Technology-Neutrality Requirements**

AUTH-029 prohibits technology and vendor selection at this stage.

Therefore, the blueprint must remain logical and technology-neutral.

Do not select or recommend specific:

* Cloud providers.  
* Hosting platforms.  
* Databases.  
* SQL implementations.  
* Programming languages.  
* Application frameworks.  
* LLMs or AI model providers.  
* AI agent frameworks.  
* API gateways.  
* Message brokers.  
* Integration middleware.  
* Workflow products.  
* Container platforms.  
* Kubernetes distributions.  
* CI/CD platforms.  
* Monitoring products.  
* Security products.  
* Vendor-specific architecture patterns.

You may describe technology capabilities generically where they are necessary to explain the architecture.

For example, describe a logical integration responsibility rather than selecting an API gateway or message broker.

Do not turn logical building blocks into microservices, containers, agents or deployable units without supporting evidence and authorisation.

# **11\. Quality and Consistency Review**

Before presenting the blueprint, perform a structured architecture review.

Check:

### **Business alignment**

* Does the architecture realise the existing business capabilities?  
* Does it support the existing value stream?  
* Are human responsibilities preserved?  
* Are scope exclusions respected?

### **Application architecture**

* Are all SOL-01 to SOL-19 represented?  
* Are logical responsibilities clear?  
* Are shared enterprise service placement decisions still open?  
* Have unnecessary components been introduced?

### **Data architecture**

* Are INF-01 to INF-22 traceable?  
* Are source linkages and AI audit records preserved?  
* Are data ownership, classification, retention and residency gaps visible?

### **Integration architecture**

* Are all ten material integration relationships covered?  
* Are the REL identifiers correct?  
* Are external capability assumptions visible?  
* Are provider failure behaviours addressed?

### **Security and governance**

* Are AIB-001 to AIB-010 enforced?  
* Is there any accidental AI decision or write authority?  
* Are human approval and accountability preserved?  
* Are audit gaps identified?

### **Operational architecture**

* Are failure conditions addressed?  
* Are manual fallback arrangements preserved?  
* Have unsupported service-level targets been avoided?

### **Architecture governance**

* Are C/W/A/G/D statuses maintained?  
* Are open decisions preserved?  
* Is the architecture technology-neutral?  
* Has any unauthorised repository change occurred?

Report identified inconsistencies, unsupported relationships and unresolved issues. Do not silently correct them.

# **12\. Required Deliverable Structure**

Present the complete Task 4.3 working analysis in the following order:

62. Executive Summary  
63. Architecture Scope, Inputs and Governance Status  
64. Architecture Principles and Binding Constraints  
65. Overall Logical Solution Architecture  
66. Logical Building Block Catalogue  
67. Logical Architecture Layer View  
68. Business Workflow and Orchestration Architecture  
69. Deterministic Rules and AI-Assisted Architecture  
70. Information and Data Flow Architecture  
71. Enterprise Integration and Coordination Architecture  
72. Security, Governance and Audit Architecture  
73. Operational Resilience and Failure Handling  
74. Architecture Diagrams  
75. Business-to-Solution Traceability Matrix  
76. AI Constraint Enforcement Matrix  
77. Architecture Decisions and Variation Points  
78. Dependencies, Assumptions and Information Gaps  
79. Architecture Quality and Consistency Review  
80. Key Findings and Recommendations  
81. Handover to Task 4.4

For each section, distinguish existing baseline evidence from proposed architecture interpretation.

# **13\. Handover to Task 4.4**

Conclude with a structured handover identifying:

* What Task 4.3 has established.  
* What remains unresolved.  
* Which logical building blocks require further refinement.  
* Which information gaps block progression.  
* Which decisions require human approval.  
* Which architecture relationships require validation.  
* What should be carried forward into Task 4.4.

Do not invent the title, scope or activities of Task 4.4. Use the course roadmap or authorised project source to establish its exact purpose. If that information is unavailable, explicitly state that the next task definition must be obtained.

# **14\. Final Output and Governance Statement**

End the analysis with:

**Task 4.3 — Solution Architecture Blueprint**

* Status: Working architecture analysis.  
* Authorisation: AUTH-029, subject to current repository governance.  
* Formal human approval: Not obtained.  
* Technology selection: None.  
* Vendor selection: None.  
* Physical deployment architecture: Not defined.  
* Implementation: Not performed.  
* Repository modifications: None.  
* Outstanding decisions and information gaps: Explicitly identified.

The final output must be a coherent, traceable and technology-neutral logical solution architecture.

The central design principle is:

**Business Capability → Solution Responsibility → Logical Building Block → Information Flow → Integration Relationship → Governance Enforcement → Operational Assurance**

Preserve the accepted baseline, maintain evidence integrity, and keep all unresolved enterprise decisions visible.

Do not sacrifice governance, traceability or accuracy in order to make the architecture appear more complete than the available evidence permits.

# **11\. Final governance reminder**

Task 4.3 is a working architecture analysis under AUTH-029, subject to the current repository governance rules. Formal human approval has not been obtained. No technology or vendor selection, physical deployment architecture or implementation is authorised by this learning activity. No repository modifications should be made unless separately authorised.