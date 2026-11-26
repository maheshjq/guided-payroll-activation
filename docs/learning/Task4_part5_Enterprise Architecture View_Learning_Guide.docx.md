**TASK 4.2**

# **Enterprise Architecture** **View**

*Learning Guide \| Phase 2 — Solution Architecture and Model-Driven Specifications*

| ROADMAP POSITIONPhase 2  •  Task 4 — Enterprise and Solution ArchitectureTask 4.2 focus: Establish how the proposed AI-Native Customer Onboarding solution fits into the enterprise environment.Primary output: Enterprise Architecture View — Working Analysis. |
| :---- |

*Six architecture domains, connected through traceability, dependencies and evidence*

# **1\. Purpose of this learning guide**

Task 4.2 develops an enterprise-level view of the AI-Native Customer Onboarding solution. It explains how business capabilities, applications, information, technology considerations, integrations, security and governance fit together in the enterprise context.

This activity builds on the Task 4.1 Architecture Requirements Assessment working output and the accepted Task 1–3 baseline. It is an analysis and modelling exercise, not an implementation activity or an approval of the architecture.

The goal is to establish the enterprise context and cross-domain relationships before decomposing the solution into detailed logical components in Task 4.3.

# **2\. Position within the 15-task roadmap**

| Roadmap activity | Focus | Relationship |
| :---- | :---- | :---- |
| Task 4.1 | Architecture Requirements Assessment | Identifies capabilities, actors, systems or external capabilities, integrations, data dependencies, requirements, constraints, assumptions, gaps and decisions. |
| Task 4.2 \| Current | Enterprise Architecture View | Organises the enterprise context across six architecture domains and explains their relationships and dependencies. |
| Task 4.3 \| Next | Solution Architecture Blueprint | Uses the enterprise view to define the target solution structure and its logical components and responsibilities. |

# **3\. Learning outcomes**

* Explain the purpose and scope of the six enterprise architecture domains.  
* Map the customer onboarding business capabilities to relevant application responsibilities and enterprise capabilities.  
* Describe important information concepts, data dependencies and data movement at an enterprise level.  
* Identify technology and infrastructure considerations without prematurely selecting products or platforms.  
* Describe internal and external integration relationships and their known dependencies.  
* Explain how security, human accountability, AI governance and control boundaries shape the architecture.  
* Preserve evidence status and traceability across the accepted Task 1–3 baseline and Task 4.1 working assessment.  
* Produce an Enterprise Architecture View suitable for human architecture review.

# **4\. Inputs and architectural context**

Use the following accepted baseline and working assessment as the source material:

* Task 1: BIZ-001 to BIZ-008.  
* Task 2: ARC-001 to ARC-008.  
* Task 3: OPS-001 to OPS-009.  
* Task 4.1: Architecture Requirements Assessment working output.  
* AUTH-029: governing the current analysis-only and technology-selection boundaries.

**Status reminder:** The Task 4.1 assessment is a working analysis, not an approved governed deliverable. Do not describe it as formally approved.

# **5\. The six architecture domains**

## **5.1 Business Architecture**

Describes the business capabilities, processes, value streams, actors, ownership and business outcomes that the solution supports. Use ARC-002 and ARC-007. Preserve the boundaries between deterministic rules, AI-assisted work and human-controlled decisions. Do not invent new capabilities; label any proposed additions for review.

## **5.2 Application Architecture**

Describes existing enterprise application capabilities, proposed solution-level responsibilities, external capabilities, application boundaries and interactions. The nine XC-01–XC-09 items are modelled external capabilities, not proof of actual products, vendors or interfaces. Core banking, CRM and IDV providers must not be replaced.

## **5.3 Data Architecture**

Describes information concepts, sources, ownership, movement, dependencies, classification hypotheses, lineage, auditability, retention and residency. Use ARC-005. Do not present proposed sensitivity classifications as validated bank classifications.

## **5.4 Technology and Infrastructure Architecture**

Describes hosting, execution, infrastructure dependencies, resilience, scalability, AI service boundaries, processing location, monitoring and continuity considerations. Do not select specific technologies, platforms, products, vendors, models or frameworks under AUTH-029.

## **5.5 Integration Architecture**

Describes internal and external relationships, integration purpose, triggers, information exchanged, criticality, dependencies and unresolved interface needs. Use ARC-005 relationships. Do not invent APIs, endpoints, protocols or products.

## **5.6 Security and Governance Architecture**

Describes identity and access, least privilege, human accountability, AI oversight, privacy, audit, untrusted inputs, contribution records, fallback, policy precedence, retention and provider governance. Do not claim regulatory compliance where applicable obligations have not been identified.

# **6\. Required analysis for each architecture domain**

For each of the six domains, document the following consistently:

* Purpose — why the domain exists and what it contributes to the enterprise solution.  
* Major elements — capabilities, applications, information concepts, infrastructure concerns, interfaces or controls relevant to the domain.  
* Relationships — how the domain connects to the other five domains.  
* Dependencies — what it relies on, including external capabilities, policy, data or decisions.  
* Constraints — confirmed boundaries that the design must respect.  
* Open decisions — choices that require an accountable human decision-maker.  
* Information gaps — facts needed but not present in the baseline.  
* Architecture risks — consequences if a dependency, assumption or gap is not resolved.

# **7\. Cross-domain relationships and traceability**

The Enterprise Architecture View must explain how the domains fit together rather than treating them as six independent descriptions.

* Business capabilities establish the business need and the outcomes to be supported.  
* Application responsibilities describe where business capabilities are enabled or coordinated.  
* Data architecture identifies the information required, created, exchanged and governed by those responsibilities.  
* Integration architecture describes how applications and external capabilities exchange information or invoke services.  
* Technology and infrastructure considerations establish the operating conditions and constraints for the architecture.  
* Security and governance controls apply across the domains, defining access, accountability, privacy, auditability and permitted AI behaviour.

**Traceability principle:** Every significant architectural element must have a business or operational justification traceable to the accepted baseline. Preserve existing identifiers; any new local references must be labelled assessment-local.

# **8\. Enterprise architecture outputs**

| Required output | Expected content |
| :---- | :---- |
| **Executive Architecture Overview** | A concise explanation of the enterprise context, scope, key constraints and architecture direction. |
| **Business Architecture View** | Capabilities, processes, actors, ownership considerations and automation boundaries. |
| **Application Architecture View** | Existing and modelled external capabilities, proposed responsibilities, boundaries and interactions. |
| **Data Architecture View** | Information concepts, sources, dependencies, movement, classification hypotheses and governance needs. |
| **Technology and Infrastructure Architecture View** | Technology-neutral hosting, execution, resilience, residency and operational considerations. |
| **Integration Architecture View** | Internal and external relationships, exchanged information, triggers, criticality and interface gaps. |
| **Security and Governance Architecture View** | Cross-domain security, privacy, human control, AI governance, audit and resilience principles. |
| **Cross-Domain Architecture Relationship Matrix** | A view of how the six domains depend on and influence one another. |
| **Architecture Dependencies and Constraints Register** | A structured record of dependencies, constraints, risks and their status. |
| **Architecture Decisions and Information Gaps Register** | Open decisions, accountable roles where known, missing evidence and impacts on subsequent design. |

# **9\. Diagrams and modelling guidance**

Where useful, include a high-level enterprise architecture diagram showing how the proposed customer onboarding solution fits into the enterprise environment. Mermaid may be used where appropriate.

* Keep the diagram at enterprise level; do not prematurely decompose it into detailed technical components.  
* Distinguish the proposed onboarding solution boundary from external enterprise capabilities.  
* Label assumed or unknown systems and interfaces clearly.  
* Show major relationships and information exchanges only where supported by the baseline.  
* Use consistent names and identifiers across the diagram, registers and narrative.  
* Ensure the diagram does not imply that an assumed capability, product or interface is confirmed.

# **10\. Evidence and status classification**

Every significant architectural statement must retain its evidence status:

| Code | Meaning |
| :---- | :---- |
| **C — Confirmed** | Recorded human decision or binding constraint. |
| **W — Working baseline** | Accepted for progression but proposed content; not validated as bank fact. |
| **A — Assumption** | Not validated or pending external confirmation. |
| **G — Information gap** | No supporting information exists in the baseline. |
| **D — Decision requiring approval** | An open decision requiring an accountable human. |

Do not upgrade assumptions or working-baseline content to confirmed facts. Preserve existing identifiers. New local references must be explicitly identified as assessment-local and must not be represented as repository IDs.

# **11\. Architecture constraints and safeguards**

* Respect all confirmed constraints and scope exclusions.  
* Preserve the distinction between confirmed, working, assumed, missing and approval-pending information.  
* Do not invent enterprise systems, products, vendors, interfaces or technologies.  
* Do not assume every business capability requires a new application or service.  
* Do not prematurely decompose the architecture into detailed technical components.  
* Do not resolve business, policy or governance decisions on behalf of accountable stakeholders.  
* Preserve the existing architecture layer separation and traceability principles.  
* Keep the architecture option-preserving where important decisions remain unresolved.  
* Preserve the binding AI boundaries: AI assists but does not make final customer decisions; account activation follows deterministic authorised workflows; screening dispositions remain human-controlled; AI access is least-privilege and audited; AI does not directly write to systems of record; rules and policy prevail; AI contributions are recorded; customer inputs are untrusted; manual fallback does not bypass controls.  
* Do not claim regulatory compliance; applicable regulatory obligations have not yet been identified in the accepted baseline.

# **12\. AI-assisted working method**

Provide Claude with the Task 4.1 working assessment and the accepted Task 1–3 baseline. Make the relevant source artefacts available in the project workspace or provide the verified extracts. Then run the complete prompt below. Keep the activity read-only and review the generated analysis against the source evidence.

# **13\. Complete Claude prompt — Task 4.2**

<details>
<summary><strong>View the complete copy-ready prompt</strong></summary>

```text
| \# Task 4.2 — Enterprise Architecture View Act as an Enterprise Architect with expertise in AI-native engineering, enterprise architecture, banking-domain architecture and model-driven solution design. \#\# Context Using the Task 4.1 Architecture Requirements Assessment working output and the accepted Task 1–3 baseline, develop an Enterprise Architecture View for the AI-Native Customer Onboarding solution. The assessment draws on: \- Task 1: BIZ-001 to BIZ-008 \- Task 2: ARC-001 to ARC-008 \- Task 3: OPS-001 to OPS-009 The Enterprise Architecture View must remain consistent with the accepted baseline and the constraints established under AUTH-029. The Task 4.1 assessment is a working analysis, not an approved governed deliverable. Do not describe it as formally approved. \#\# Objective Establish how the proposed AI-Native Customer Onboarding solution fits into the enterprise environment. Identify and describe the following six architecture domains: 1\. Business Architecture 2\. Application Architecture 3\. Data Architecture 4\. Technology and Infrastructure Architecture 5\. Integration Architecture 6\. Security and Governance Architecture \#\# 1\. Business Architecture Identify and describe: \- Business capabilities supported by the proposed solution. \- Relevant business processes and value streams. \- Key business actors and stakeholder groups. \- Business capability relationships and dependencies. \- Business ownership and accountability considerations. \- Boundaries between automated, AI-assisted and human-controlled activities. Use the existing capability baseline, particularly ARC-002 and ARC-007. Explain how the proposed solution supports the customer onboarding business capability. Do not create new business capabilities without identifying them as proposed additions requiring review. \#\# 2\. Application Architecture Identify and describe: \- Existing enterprise application capabilities relevant to onboarding. \- Proposed solution-level application responsibilities. \- External enterprise applications and service capabilities. \- Application boundaries and interactions. \- Responsibilities that may be fulfilled by existing enterprise systems. \- Capabilities that may require additional solution components, subject to later design decisions. Consider the external capabilities already identified in the baseline, including: \- XC-01: Core banking account management. \- XC-02: CRM / customer master. \- XC-03: Identity verification services. \- XC-04: Screening services. \- XC-05: Financial crime investigation and reporting. \- XC-06: Enterprise model risk management / AI governance. \- XC-07: Enterprise data protection and privacy. \- XC-08: Enterprise identity and access management. \- XC-09: Enterprise records retention. These are modelled external capabilities. Do not assume that their actual systems, products, vendors or interfaces have been confirmed. Preserve the constraints that core banking, CRM and IDV providers are not to be replaced. \#\# 3\. Data Architecture Identify and describe: \- Major business information concepts. \- Important data sources and information dependencies. \- Data ownership and stewardship considerations. \- Data movement across business and application boundaries. \- Data classification and sensitivity considerations. \- Data lineage, auditability and traceability requirements. \- Data retention and residency dependencies. \- Information exchanged with external systems. Use the existing information concepts from ARC-005. Explain how information supports business capabilities, application responsibilities, operational decisions and governance. Do not treat proposed sensitivity classifications as validated bank classifications. \#\# 4\. Technology and Infrastructure Architecture Establish the technology and infrastructure architecture considerations without selecting specific technologies. Identify: \- Hosting and deployment considerations. \- Application execution and integration requirements. \- Infrastructure dependencies. \- Availability, resilience and scalability considerations. \- AI service execution and access boundaries. \- Data residency and processing-location constraints. \- Operational monitoring and service continuity requirements. Clearly distinguish confirmed constraints from requirements that still need definition. Do not select or recommend specific: \- Cloud providers. \- Infrastructure platforms. \- Databases. \- Programming frameworks. \- LLM providers or models. \- AI orchestration frameworks. \- Middleware or integration products. \- Container or deployment platforms. Technology selection is not authorised under AUTH-029. \#\# 5\. Integration Architecture Identify and describe: \- Internal and external integration relationships. \- Systems or capabilities exchanging information. \- Integration purposes and business triggers. \- Major information exchanged. \- Dependencies between integration points. \- Criticality and operational implications. \- Integration risks and unresolved interface requirements. Use the relationships documented in ARC-005. Pay particular attention to: \- Identity verification requests and results. \- Screening requests and results. \- Financial-crime escalation handoffs. \- Customer master creation. \- Account creation and activation. \- Consent and privacy information. \- Approval authority and access. \- AI governance reporting. \- Evidence retention. Do not invent APIs, endpoints, protocols, interface specifications or integration products. Where an interface is unknown, identify the dependency and record the information gap. \#\# 6\. Security and Governance Architecture Describe the security and governance principles that must shape the enterprise architecture. Cover: \- Identity and access management. \- Least-privilege access. \- Human approval and accountability. \- AI governance and oversight. \- Data protection and privacy. \- Auditability and traceability. \- Untrusted customer-supplied content. \- Model and AI contribution records. \- Resilience and manual fallback. \- Policy and business-rule precedence. \- Records retention. \- External provider governance. Preserve the binding AI boundaries: \- AI may recommend, summarise, extract, classify and draft. \- AI must not approve, decline or make final customer decisions. \- Account creation and activation must occur only through deterministic, authorised workflows after required checks and approvals. \- Screening alert disposition and escalation remain with authorised humans. \- AI must have least-privilege, scoped and audited access. \- AI must not directly write to systems of record. \- Rules and policy take precedence over AI outputs. \- Every AI contribution must be recorded. \- Customer-supplied content must be treated as untrusted data. \- Manual fallback must be available when AI is degraded, without bypassing controls. Do not claim regulatory compliance. Applicable regulatory obligations have not yet been identified in the accepted baseline. \#\# 7\. Architecture Relationships and Dependencies Explain how the six architecture domains relate to one another. For each domain, document: \- Purpose. \- Major elements. \- Relationships with other architecture domains. \- Dependencies. \- Relevant constraints. \- Open decisions. \- Information gaps. \- Architecture risks. Show the traceability from business capabilities to application responsibilities, data requirements, integrations, technology considerations and governance controls. Every significant architectural element must have a traceable business or operational justification. \#\# 8\. Enterprise Architecture View — Required Outputs Produce the following: 1\. Executive Architecture Overview. 2\. Business Architecture View. 3\. Application Architecture View. 4\. Data Architecture View. 5\. Technology and Infrastructure Architecture View. 6\. Integration Architecture View. 7\. Security and Governance Architecture View. 8\. Cross-Domain Architecture Relationship Matrix. 9\. Architecture Dependencies and Constraints Register. 10\. Architecture Decisions and Information Gaps Register. Where useful, include a high-level enterprise architecture diagram showing how the proposed customer onboarding solution fits into the enterprise environment. Use Mermaid for diagrams where appropriate. Ensure that all diagram elements are consistent with the written architecture. \#\# 9\. Evidence and Status Classification For every significant architectural statement, preserve its evidence status. Use the following classifications: \- C — Confirmed: Recorded human decision or binding constraint. \- W — Working baseline: Accepted for progression but proposed content; not validated as bank fact. \- A — Assumption: Not validated or pending external confirmation. \- G — Information gap: No supporting information exists in the baseline. \- D — Decision requiring approval: An open decision requiring an accountable human. Do not upgrade assumptions or working-baseline content to confirmed facts. Preserve existing identifiers from the accepted baseline. Any new local references must be explicitly identified as assessment-local and must not be represented as repository IDs. \#\# 10\. Architecture Constraints and Safeguards The architecture must: 1\. Respect all confirmed constraints and scope exclusions. 2\. Preserve the distinction between confirmed, working, assumed, missing and approval-pending information. 3\. Avoid inventing enterprise systems, products, vendors, interfaces or technologies. 4\. Avoid assuming that every business capability requires a new application or service. 5\. Avoid prematurely decomposing the architecture into detailed technical components. 6\. Avoid resolving business, policy or governance decisions on behalf of accountable stakeholders. 7\. Preserve the existing architecture layer separation and traceability principles. 8\. Keep the architecture option-preserving where important decisions remain unresolved. \#\# 11\. Working Status and Execution Boundaries This is a Task 4.2 learning activity under AUTH-029. It is an architecture analysis and modelling exercise only. \- Work read-only from the available approved baseline and Task 4.1 working assessment. \- Do not write to the repository. \- Do not modify existing files or governed artefacts. \- Do not create new repository identifiers. \- Do not generate application code. \- Do not implement infrastructure or integration configurations. \- Do not select vendors, platforms, products or technology components. \- Do not claim that the architecture has received formal human approval. Present the output as: \*\*Task 4.2 — Enterprise Architecture View: Working Analysis\*\* Conclude with: 1\. Key architectural findings. 2\. Unresolved dependencies and decisions. 3\. Information required from the enterprise or bank. 4\. Risks that could affect subsequent solution architecture design. 5\. Recommendations for proceeding to Task 4.3 — Solution Architecture Blueprint. The final output must be evidence-based, traceable, internally consistent and suitable for human architecture review. |
| :---- |

```
</details>

# **14\. How to review Claude's output**

* ☐ Check that all six domains are covered and that their relationships are explained, not merely listed.  
* ☐ Verify that XC-01 to XC-09 remain modelled external capabilities and are not presented as confirmed installed systems.  
* ☐ Check that core banking, CRM and IDV non-replacement constraints are preserved.  
* ☐ Verify that the AI boundaries and human decision rights remain intact.  
* ☐ Check that no vendor, platform, product, LLM, framework, API or interface has been invented or selected.  
* ☐ Confirm that every important element retains C, W, A, G or D status and baseline traceability.  
* ☐ Check that the diagrams agree with the narrative and do not imply unsupported facts.  
* ☐ Keep the output as a working analysis until the appropriate human review and authorisation steps occur.

# **15\. Common mistakes to avoid**

* Treating modelled external capabilities as proof that named applications exist.  
* Drawing a complete current-state bank landscape when the actual bank and system inventory are unknown.  
* Selecting technology because it is familiar or commonly used in banking.  
* Assuming a new application or service is required for every capability.  
* Turning assumptions into facts through diagram labels or confident prose.  
* Mixing enterprise-level architecture with detailed solution component design, which belongs to Task 4.3.  
* Claiming compliance with regulatory instruments that have not been identified.  
* Allowing AI-generated decisions to bypass accountable human approval.

# **16\. Completion criteria and handover to Task 4.3**

Task 4.2 is ready for human architecture review when the team has:

* Produced all six architecture-domain views.  
* Explained cross-domain relationships and traceability.  
* Documented dependencies, constraints, risks and unresolved decisions.  
* Preserved evidence classifications and baseline identifiers.  
* Created a consistent high-level enterprise architecture diagram where useful.  
* Confirmed that no unauthorised technology selection or repository modification occurred.

Handover to Task 4.3: use the reviewed enterprise context to define the logical target solution architecture, including candidate solution components, responsibilities, boundaries, inputs, outputs and interactions. Do not treat unresolved enterprise facts or decisions as settled during that decomposition.

# **17\. Learner reflection**

1. Which domain has the strongest confirmed evidence, and which is most affected by information gaps?  
2. How does the business capability baseline trace into application responsibilities?  
3. Which external capabilities must the solution coordinate with rather than replace?  
4. Which cross-domain dependencies could materially change the solution architecture?  
5. How did the evidence-status discipline prevent assumptions from becoming false facts?  
6. What must be resolved or explicitly carried forward before Task 4.3?