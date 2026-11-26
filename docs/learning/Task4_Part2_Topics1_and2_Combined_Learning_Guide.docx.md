**TASK 4 — ENTERPRISE AND SOLUTION ARCHITECTURE**

# **Part 1 — Architecture Foundations**

*Combined Learning Guide: Topic 1 and Topic 2*

| Central learning idea: Understand the enterprise before designing a particular solution. Enterprise Architecture provides the wider organisational context; Solution Architecture defines how a specific solution should be structured within that context. |
| :---- |

# **How to use this guide**

This guide is designed for conceptual learning before students use Claude Code to inspect their actual Task 1–3 repositories. Work through the explanations and examples first. Then use the exercises to check understanding. Repository inspection and architecture modelling should follow only after students can explain the concepts in their own words.

# **Learning outcomes for Part 1**

* Explain Enterprise Architecture and why enterprises need it.  
* Describe the four commonly used Enterprise Architecture domains.  
* Explain Solution Architecture and the main concerns it addresses.  
* Distinguish Enterprise Architecture from Solution Architecture.  
* Explain how enterprise capabilities, standards and constraints influence an individual solution.  
* Recognise the additional considerations introduced by AI-native solutions.

# **TOPIC 1 — What is Enterprise Architecture?**

## **1\. Start with a practical question**

Imagine a bank decides to introduce a digital customer onboarding service. Its objective is to enable customers to open accounts digitally, reduce paperwork, speed up processing and improve customer experience while maintaining appropriate risk controls and regulatory obligations.

The initiative may prompt immediate questions about a mobile application, database, cloud platform, AI model or APIs. Those are important design questions, but before answering them the bank needs to understand how the initiative fits into the wider enterprise.

* Which business capabilities and departments will be affected?  
* Which existing business processes will change?  
* What customer information will be required?  
* Which existing applications and systems will be involved?  
* What security, risk, compliance and governance requirements apply?  
* How will the new solution interact with existing enterprise systems?

| Key question: How will this initiative fit into the overall enterprise? This is where Enterprise Architecture becomes important. |
| :---- |

## **2\. Definition of Enterprise Architecture**

Enterprise Architecture (EA) is the discipline of understanding, structuring and governing an enterprise as an interconnected whole. It provides a coordinated view of business strategy and objectives, business capabilities and processes, organisational structures and responsibilities, enterprise information and data, applications and systems, technology infrastructure, and governance, standards and constraints.

| In simple terms: Enterprise Architecture helps an organisation understand how its business and technology elements fit together, and how they should evolve to achieve its strategic objectives. |
| :---- |

## **3\. Why do enterprises need Enterprise Architecture?**

Consider a bank in which each department makes technology decisions independently:

| Department | Independent initiative |
| :---- | :---- |
| Retail Banking | Develops a digital onboarding application |
| Risk Management | Implements a separate customer risk assessment system |
| Compliance | Maintains an independent customer screening process |
| Customer Service | Introduces a separate customer information platform |
| IT | Maintains several disconnected customer databases |

This fragmented approach can lead to:

* Customer information being collected multiple times.  
* Inconsistent customer records across departments.  
* Systems that do not communicate effectively.  
* Unnecessary process handovers.  
* Different security and access-control standards.  
* Duplicated investment in capabilities that may already exist.

Enterprise Architecture helps the organisation establish a coordinated view of shared capabilities, information, applications, integration and governance. The goal is not necessarily to have one system for everything; it is to make sure that business functions and systems work coherently.

## **4\. The four commonly used Enterprise Architecture domains**

A widely used way of understanding Enterprise Architecture is through four domains. They are different views of the same enterprise, not four independent exercises.

| Domain | What it describes | Examples |
| :---- | :---- | :---- |
| Business Architecture | What the enterprise does and how it operates. | Strategy, objectives, capabilities, processes, organisational responsibilities. |
| Data Architecture | What information the enterprise needs and how it is managed. | Data entities and concepts, ownership, data flows, quality and governance. |
| Application Architecture | The applications and software systems supporting business operations. | Enterprise applications, application responsibilities, interactions and integration. |
| Technology Architecture | The underlying technology environment. | Compute, hosting, networks, cloud environments, platforms and runtime infrastructure. |

### **Banking example across the four domains**

| Architecture domain | Customer onboarding example |
| :---- | :---- |
| Business | Customer registration, identity verification, risk assessment and account opening. |
| Data | Customer details, identity documents, screening results and application records. |
| Application | Onboarding application, customer information system and screening application. |
| Technology | Hosting infrastructure, databases, networks and runtime environments. |

For example, Business Architecture identifies the need to verify customer identity; Data Architecture identifies the identity information required; Application Architecture identifies the applications supporting verification; and Technology Architecture identifies the infrastructure on which those applications operate.

## **5\. Enterprise Architecture versus an individual IT project**

Compare these two questions:

* “How should the bank’s overall customer information, applications and technology landscape be organised to support its business strategy?” — an Enterprise Architecture concern.  
* “How should the new customer onboarding solution be structured, including its logical components, interfaces, data flows and interactions?” — a Solution Architecture concern.

The second question is narrower. It focuses on a particular solution. Topic 2 explores this distinction in more detail.

## **6\. How Enterprise Architecture relates to AI-native engineering**

AI-native engineering should not begin with an AI model or an agent. It should begin with understanding the enterprise and its business needs.

| Progression | Question answered |
| :---- | :---- |
| Enterprise Strategy | What is the organisation trying to achieve? |
| Enterprise Architecture | How do business, data, applications and technology fit together? |
| Solution Architecture | How should a particular solution be structured? |
| Model-driven Specifications | How do we express the solution structure and behaviour in governed, structured artefacts? |
| AI-native Engineering | How do AI agents and engineering harnesses implement and verify the solution? |

| Key principle: AI agents should implement an architecture that has been reasoned about and governed, not independently invent the enterprise architecture while writing code. |
| :---- |

Enterprise Architecture also helps identify where AI may be appropriate, where deterministic processing is necessary, and where human accountability must be preserved.

## **7\. Topic 1 classroom exercise**

Scenario: A university wants to introduce a digital student registration and enrolment service. Classify each activity under the most relevant Enterprise Architecture domain.

| Activity | Domain |
| :---- | :---- |
| Defining student registration and course enrolment processes. | Business Architecture |
| Defining student records, course information and enrolment data. | Data Architecture |
| Defining the student portal and student management system. | Application Architecture |
| Defining cloud hosting, network infrastructure and runtime environments. | Technology Architecture |

## **Topic 1 learning takeaways**

* Enterprise Architecture provides an enterprise-wide view of how the organisation works.  
* It helps align business strategy, operations, information, applications and technology.  
* The four commonly used domains are Business, Data, Application and Technology Architecture.  
* The domains are interconnected views of the same enterprise.  
* Enterprise Architecture provides the wider context for designing individual solutions.

# **TOPIC 2 — What is Solution Architecture, and how does it differ from Enterprise Architecture?**

## **1\. Start with a practical business situation**

Imagine that a bank has decided to introduce a new AI-native digital customer onboarding solution. The bank already has business processes for customer registration, customer information systems, identity verification capabilities, risk assessment and screening processes, existing databases and APIs, and security and governance requirements.

The bank now needs to design a particular solution that brings the relevant capabilities together.

| Key question: How should we structure this solution so that it delivers the intended business outcomes and works within the existing enterprise environment? |
| :---- |

## **2\. What is Solution Architecture?**

Solution Architecture is the discipline of defining the structure, responsibilities, interactions and governing decisions of a particular solution to satisfy identified business and stakeholder needs. It describes how the solution should work as a coherent system.

A Solution Architecture considers:

* What capabilities the solution must provide.  
* What logical components or services are required.  
* What responsibilities each component performs.  
* How components interact with one another.  
* What information is exchanged and managed.  
* How the solution integrates with existing enterprise systems.  
* What security, performance, resilience and other quality requirements must be satisfied.  
* What constraints and architectural decisions govern the solution.

| In simple terms: Enterprise Architecture explains how the organisation fits together. Solution Architecture explains how a particular solution should be structured to serve the organisation. |
| :---- |

## **3\. Practical example: Digital customer onboarding**

Assume the bank has identified these business capabilities:

* Customer information capture  
* Identity verification  
* Customer screening  
* Risk assessment  
* Exception handling  
* Account opening  
* Customer notification

These are business-level capabilities. They describe what the business needs to accomplish, but do not yet explain how the software solution will be structured. A solution architect translates these needs into logical solution responsibilities.

| Business capability | Possible logical solution responsibility |
| :---- | :---- |
| Customer information capture | Customer Information Management |
| Identity verification | Identity Verification |
| Customer screening | Screening Integration |
| Risk assessment | Risk Assessment |
| Exception handling | Exception and Human Review Management |
| Account opening | Account Opening Coordination |
| Customer notification | Notification Management |

Important: these logical responsibilities are not necessarily separate microservices, containers or applications. Those implementation decisions come later. A logical responsibility describes what needs to be done, not yet the technology or deployment form used to do it.

## **4\. What does a Solution Architecture contain?**

A Solution Architecture is more than a list of components. It describes how the components work together. The following six views are useful ways to organise architectural reasoning.

| Architectural view | Key question | Onboarding example |
| :---- | :---- | :---- |
| Logical component architecture | What are the major responsibilities within the solution? | Customer Information, Identity Verification, Screening and Account Opening responsibilities. |
| Interaction architecture | How do components communicate and coordinate? | The onboarding workflow requests identity verification and receives its result. |
| Information and data architecture | What information is required, exchanged, stored and retrieved? | Customer details, identity evidence and verification outcomes. |
| Integration architecture | How does the solution interact with existing or external systems? | Connecting to an existing customer information system or screening service. |
| Security and governance architecture | How are access, privacy, permissions, accountability and controls maintained? | Human approval boundaries, audit trails and role-based access. |
| Quality and operational architecture | How will the solution satisfy quality expectations and operate reliably? | Availability, scalability, maintainability, performance and recovery. |

These views are related. A change in one can affect the others. For example, introducing an external identity verification service affects component interactions, data exchange, security and operational dependencies.

## **5\. Enterprise Architecture versus Solution Architecture**

The distinction is primarily one of scope and focus. Enterprise Architecture considers the organisation-wide landscape. Solution Architecture focuses on the structure of a particular solution within that landscape.

| Dimension | Enterprise Architecture | Solution Architecture |
| :---- | :---- | :---- |
| Scope | Entire enterprise | Specific solution or initiative |
| Primary concern | Enterprise-wide alignment and coherence | Structure of a particular solution |
| Focus | Business, data, applications and technology across the organisation | Components, interactions, data flows and integration within the solution |
| Business perspective | Enterprise strategy and capabilities | Business needs supported by the solution |
| Applications | Overall application landscape | Applications and components participating in the solution |
| Data | Enterprise information architecture | Information used and exchanged by the solution |
| Technology | Enterprise technology landscape and standards | Technology requirements and architecture for the solution |
| Typical outputs | Enterprise views, roadmaps, principles and standards | Solution views, logical designs and architecture decisions |
| Key question | How should the enterprise fit together? | How should this solution be structured? |

## **6\. An analogy: City planning and a hospital**

Think about constructing a city:

* Enterprise Architecture is like city planning. It considers roads, utilities, zones, public services, infrastructure and how everything works together.  
* Solution Architecture is like designing a particular hospital within that city. It considers departments, rooms, services, information systems, utilities and how they interact.

A hospital must follow the city’s planning requirements, but it also needs its own detailed architectural design. Similarly, a solution must fit within the enterprise architecture, but it requires its own architecture.

## **7\. How the two architectures relate**

| Enterprise Architecture provides | Solution Architecture uses this to define |
| :---- | :---- |
| Existing enterprise capabilities | Which solution responsibilities are needed and which capabilities can be reused. |
| Business needs and strategic direction | The scope and intended outcomes of the particular solution. |
| Enterprise information and data governance | The information the solution needs to handle and the rules governing it. |
| Existing application landscape | The systems to integrate with and the boundaries of the solution. |
| Enterprise security standards and constraints | Solution-level security, access, privacy and control designs. |

The relationship is also iterative: a new solution can reveal gaps, duplicated capabilities or improvement opportunities that should be considered at enterprise level.

## **8\. What makes Solution Architecture AI-native?**

AI-native engineering introduces additional architectural considerations, but it does not mean replacing every software component with an AI agent.

| Traditional architecture concern | Additional AI-native consideration |
| :---- | :---- |
| Application components | AI agents and clearly bounded agent responsibilities. |
| Business logic | A deliberate combination of deterministic rules and AI-supported reasoning. |
| Application integration | Agent-to-service interactions and MCP-mediated integration where appropriate. |
| Data access | Enterprise knowledge retrieval and governed data access. |
| Application testing | Agent evaluation and model behaviour testing. |
| Deployment | Model, specification and container traceability. |
| Security | Agent permissions, tool access, model security and guardrails. |

Example: in customer screening, an AI agent might help interpret an ambiguous document or summarise screening information. However, it must not independently clear a suspicious screening alert, bypass deterministic screening controls or independently approve a customer. Tool access, permissions, outputs and human oversight must be governed.

| Key principle: AI-native architecture means designing the appropriate combination of deterministic software, AI capabilities, agents, human decisions and governance. AI agents are only one part of the solution. |
| :---- |

## **9\. Topic 2 classroom exercise — Enterprise or Solution Architecture?**

Scenario: A retail organisation is introducing an online ordering solution. Classify each activity as an Enterprise Architecture concern or a Solution Architecture concern.

| No. | Activity | Expected classification |
| :---- | :---- | :---- |
| 1 | Establishing a common enterprise-wide customer data governance policy. | Enterprise Architecture |
| 2 | Defining an Order Management component for a new online ordering solution. | Solution Architecture |
| 3 | Rationalising the application portfolio across all departments. | Enterprise Architecture |
| 4 | Designing how the online ordering solution exchanges order details with an existing inventory system. | Solution Architecture |
| 5 | Establishing an enterprise-wide security architecture standard. | Enterprise Architecture |
| 6 | Defining a component to coordinate payment processing and handle failed payment responses. | Solution Architecture |

Facilitator note: Ask students to explain the scope behind each classification. The purpose is to recognise whether the concern applies across the enterprise or to the design of one particular solution.

## **10\. Topic 2 key learning takeaways**

* Solution Architecture defines the structure, responsibilities and interactions of a particular solution.  
* A solution architecture should be grounded in business and stakeholder needs.  
* Enterprise Architecture provides the wider context, standards, reusable capabilities and constraints.  
* Solution Architecture translates business needs into logical solution responsibilities and relationships.  
* Logical components do not automatically imply microservices, containers or specific products.  
* AI-native solutions combine deterministic software, AI capabilities, human decisions and governance.

## **11\. Transition to Topic 3**

We have established two ideas:

* Enterprise Architecture tells us how the enterprise fits together.  
* Solution Architecture tells us how a particular solution should be structured.

| Next topic: How do we translate Business Architecture into Solution Architecture? |
| :---- |

**Business Capability → Business Process → Business Requirement → Solution Capability → Logical Component**

This connects the work students completed in Tasks 1, 2 and 3 to Task 4\. It also establishes the architectural reasoning students should understand before asking Claude Code to inspect their actual repositories.

# **Facilitator recap — questions for classroom discussion**

* Why is Enterprise Architecture broader than Solution Architecture?  
* Can a solution be well designed technically but still conflict with enterprise needs? Explain with an example.  
* Why should logical solution responsibilities be identified before choosing microservices or containers?  
* Why should an AI-native solution preserve deterministic controls and human accountability where required?  
* What evidence from Tasks 1–3 should students inspect before proposing a solution architecture?