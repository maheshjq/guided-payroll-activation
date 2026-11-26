**TASK 4**

# **Enterprise and Solution** **Architecture**

*Learning Guide \| Phase 2 — Solution Architecture and Model-Driven Specifications*

| ROADMAP POSITIONPhase 2  •  Tasks 4–6Task 4 focus: Define enterprise and solution architecture, including architecture, integration and data flows.Primary output: Solution Architecture Blueprint. |
| :---- |

*From approved business and operational understanding to a coherent target solution design*

# **1\. Purpose of this learning guide**

Task 4 translates the approved understanding developed in Tasks 1, 2 and 3 into an architecture view that explains how the enterprise and proposed solution should be structured. It connects business capabilities and operational needs to applications, data, integrations, technology considerations and solution components.

This is an architecture-design activity, not an implementation exercise. Learners should establish what is known, expose what is missing, document design choices and obtain human review before treating the architecture as approved.

# **2\. Position within the 15-task roadmap**

| Roadmap task | Focus | Relationship to Task 4 |
| :---- | :---- | :---- |
| Tasks 1–3 \| Phase 1 | Business understanding and value definition | Provide approved business intent, capabilities, operational blueprint, requirements and decisions. |
| Task 4 \| Current | Enterprise and Solution Architecture | Structures the target architecture and defines component, integration and data-flow relationships. |
| Task 5 \| Next | Rules, Analytics and AI Decision Framework | Uses the architecture context to identify where rules, analytics and AI support decisions. |
| Task 6 \| Next | Structured Specifications and UISpec Contract | Turns architecture and decision requirements into structured, machine-readable specifications and contracts. |

# **3\. Learning outcomes**

* Analyse approved business and operational requirements from Tasks 1–3 and identify their architecture implications.  
* Describe the enterprise context in which the solution will operate.  
* Identify major architecture domains and explain their responsibilities and relationships.  
* Decompose a proposed solution into logical components with clear responsibilities and boundaries.  
* Describe major application, integration and data flows.  
* Record assumptions, information gaps, constraints, risks and decisions requiring approval.  
* Produce architecture diagrams and a reviewable Solution Architecture Blueprint without prematurely generating application code.

# **4\. Inputs required before starting**

Use the approved artefacts from Tasks 1, 2 and 3 as the source of truth. Depending on the project, these may include:

* Business problem, intent, value model and success measures.  
* Business architecture and capability model.  
* Operational blueprint, process models and decision requirements.  
* Stakeholder, user and external-actor information.  
* Requirements, constraints, assumptions and approved decisions.  
* Existing enterprise-system, data-source or integration information already documented.

**Important:** If an input is missing, do not silently reconstruct it. Record the gap and identify the evidence or decision needed.

# **5\. Core concepts**

**Enterprise architecture —** A structured view of the enterprise’s business, information, application and technology environment, including how these parts relate.

**Solution architecture —** The logical design of a particular solution: its major components, responsibilities, boundaries, interactions and constraints.

**Business architecture —** The capabilities, value streams, processes, roles and business outcomes that the solution must support.

**Application architecture —** The applications, services and software components involved, including their responsibilities and interactions.

**Data architecture —** The important data entities, sources, ownership, movement, storage and dependencies relevant to the solution.

**Integration architecture —** The interfaces and interaction patterns through which systems and components exchange information or invoke capabilities.

**Technology architecture —** The technology environment and platform considerations needed to host, connect, secure and operate the solution.

# **6\. Task 4 activity sequence**

## **4.1 Architecture requirements assessment**

Review approved outputs from Tasks 1–3. Extract capabilities, systems, stakeholders, integrations, data sources, functional and non-functional requirements, constraints and assumptions. Separate confirmed facts from unknowns and decisions needing approval.

**Expected output:** Architecture Requirements Assessment.

## **4.2 Enterprise architecture view**

Place the proposed solution in its enterprise context. Identify relevant business, application, data, integration and technology domains and show key relationships. Include only systems and capabilities supported by evidence.

**Expected output:** Enterprise Architecture View.

## **4.3 Solution architecture blueprint**

Decompose the target solution into logical components. For each, state purpose, responsibilities, inputs, outputs, dependencies and interactions. Define boundaries and avoid unnecessary duplication.

**Expected output:** Solution Architecture Blueprint.

## **4.4 Integration architecture**

Identify source and destination systems, information exchanged, triggers, communication patterns and failure-handling needs. Distinguish confirmed integration facts from proposed design choices.

**Expected output:** Integration Architecture View and integration inventory.

## **4.5 Data flows**

Trace important information flows. Identify origin, destination, purpose, transformation or validation needs, dependencies and relevant security considerations.

**Expected output:** Logical Data Flow Models.

## **4.6 Architecture diagrams**

Create diagrams for enterprise context, solution components, interactions, integrations and end-to-end data movement. Keep labels consistent with the written architecture.

**Expected output:** Architecture diagram set.

## **4.7 Architecture review**

Review completeness, consistency, traceability, security, scalability, maintainability, integration and data-flow coverage. Record findings and conditions for approval.

**Expected output:** Architecture Review Report.

# **7\. Architecture Requirements Assessment — what to identify**

**Business capabilities:** What the solution must enable the business to do. Link each capability to approved business intent or process evidence.

**Existing enterprise systems and applications:** Systems already in use or explicitly identified in source artefacts. Record their known role; do not infer capabilities.

**Users, stakeholders and external actors:** People, teams, organisations or systems that interact with or are affected by the solution.

**Integration needs:** Known or required system-to-system interactions, including business purpose and information exchanged.

**Data sources and dependencies:** Known records, datasets, systems of record, data owners and upstream/downstream dependencies.

**Functional requirements:** Behaviours or capabilities the solution must provide.

**Non-functional requirements:** Quality attributes and operational expectations, such as security, availability, performance, scalability, auditability and maintainability, where specified.

**Constraints and assumptions:** Technology, policy, regulatory, organisational, timing or resource limits; distinguish confirmed constraints from assumptions.

# **8\. Evidence discipline**

Every material statement in the assessment should be classified as one of the following:

| Classification | How to use it |
| :---- | :---- |
| **Confirmed requirement** | Directly supported by an approved Task 1, 2 or 3 artefact or other identified authoritative evidence. |
| **Assumption** | A temporary proposition used to explore a design. State rationale, impact and validation action or owner. |
| **Information gap** | Information required for a sound design but not available in the source material. |
| **Architecture decision requiring approval** | A design choice with meaningful impact that must be reviewed and accepted by the authorised human decision-maker. |

# **9\. Recommended documentation structure**

1. Document control: title, version, date, author, status and approval record.  
2. Executive summary and architecture purpose.  
3. Scope, context and source artefacts reviewed.  
4. Architecture requirements assessment.  
5. Enterprise architecture view.  
6. Target solution architecture and component catalogue.  
7. Integration architecture and integration inventory.  
8. Data-flow models and data dependencies.  
9. Architecture decisions, assumptions, constraints and open questions.  
10. Risks, quality attributes and security considerations.  
11. Architecture diagrams.  
12. Validation findings, review comments and approval status.

# **10\. Quality and validation checklist**

* ☐ Every major architecture element can be traced to a business capability, requirement or explicitly labelled design need.  
* ☐ The architecture does not introduce unsupported systems, APIs, data sources or technologies as facts.  
* ☐ Component responsibilities and boundaries are understandable and non-duplicative.  
* ☐ Integration sources, destinations and purposes are identified where known.  
* ☐ Important data flows have clear origins, destinations and purposes.  
* ☐ Functional and non-functional requirements are considered.  
* ☐ Security, access, privacy and governance concerns are visible at the appropriate level.  
* ☐ Assumptions, information gaps and decisions requiring approval are explicit.  
* ☐ Written descriptions and diagrams use consistent names and tell the same story.  
* ☐ The work is presented for human review; it is not labelled approved without approval evidence.

# **11\. AI-assisted working method**

Use the prompt below as the first AI-assisted activity in Task 4\. Provide Claude with the approved outputs from Tasks 1, 2 and 3, or make those files available in the project workspace. Ask it to analyse the evidence before attempting architecture design.

## **Prompt 4.1 — Architecture Requirements Assessment**

| Act as an Enterprise Architect with expertise in AI-native engineering, enterprise architecture and model-driven solution design. Using the approved outputs from Tasks 1, 2 and 3, analyse the business and operational requirements. Identify: 1\. Business capabilities that the solution must support. 2\. Existing enterprise systems and applications. 3\. Key users, stakeholders and external actors. 4\. Existing systems that must be integrated. 5\. Major data sources and data dependencies. 6\. Functional and non-functional requirements. 7\. Architecture constraints and assumptions. Do not invent missing information. Clearly distinguish: \- Confirmed requirements \- Assumptions \- Information gaps \- Architecture decisions requiring approval Do not begin implementation or generate application code. Present the findings as an Architecture Requirements Assessment. |
| :---- |

# **12\. How to use Prompt 4.1 responsibly**

13. Attach or provide the approved Task 1, Task 2 and Task 3 outputs before running the prompt.  
14. Ask the AI to identify the source artefact supporting each confirmed requirement, where possible.  
15. Check that assumptions and common industry practices have not been presented as confirmed facts.  
16. Review information gaps and decide which ones block architecture design.  
17. Have the relevant human owner validate material requirements and assumptions.  
18. Save the output as a draft Architecture Requirements Assessment with a clear version and review status.

# **13\. Common mistakes to avoid**

* Starting with technology choices before understanding approved business and operational requirements.  
* Treating a plausible industry-standard feature as a confirmed requirement.  
* Inventing enterprise systems, APIs, integrations or data sources to make a diagram look complete.  
* Mixing logical architecture with detailed implementation or deployment configuration too early.  
* Using inconsistent component names across diagrams and documents.  
* Allowing AI-generated design decisions to bypass human review and approval.  
* Moving into Task 5 decision-rule and AI decision-framework design before the Task 4 architecture context is sufficiently established.

# **14\. Completion criteria and handover to Task 5**

Task 4 is ready for human review when the team has produced:

* Architecture Requirements Assessment based on approved Task 1–3 evidence.  
* Enterprise Architecture View.  
* Solution Architecture Blueprint with documented component responsibilities.  
* Integration and data-flow views.  
* Consistent architecture diagrams.  
* Register of assumptions, gaps, constraints, risks and decisions requiring approval.  
* Architecture Review Report with findings and approval conditions.

Handover to Task 5: provide the reviewed architecture context so the team can identify business rules, analytics needs and AI-supported decisions within the correct business and system boundaries. Task 5 should not silently redesign or contradict the approved Task 4 architecture.

# **15\. Learner reflection**

19. Which architecture requirements were directly supported by the approved Task 1–3 artefacts?  
20. What information gaps most affected the architecture assessment?  
21. Which assumptions could materially change the proposed solution?  
22. Which architecture decisions require human approval, and why?  
23. How did AI accelerate analysis, and what did the human reviewer need to correct or challenge?