**TASK 4 — ENTERPRISE AND SOLUTION ARCHITECTURE**

# **Topic 3 — From Business Architecture to Solution Architecture**

*Learning Guide and Classroom Exercise*

| Central idea: Translate business needs into solution responsibilities through a traceable reasoning process. Do not jump directly from a broad business objective to software components, platforms or AI agents. |
| :---- |

# **Learning objectives**

By the end of this topic, students should be able to:

* Explain why business needs must be understood before designing a solution.  
* Distinguish business capabilities, business processes and business requirements.  
* Explain what solution capabilities represent.  
* Identify logical solution components from solution responsibilities.  
* Trace proposed logical components back to business needs.  
* Explain where deterministic processing, AI-supported processing, human oversight and governance may fit within a solution.

# **1\. The fundamental challenge**

Imagine a business stakeholder tells an IT team: “We need to improve our customer onboarding process.” This describes a business need, but it is not sufficient information to start designing software.

The statement does not yet explain:

* Which business capabilities are involved.  
* Which processes must be supported.  
* What requirements must be satisfied.  
* What decisions must be made.  
* What information must be processed.  
* What responsibilities the solution must perform.

If developers immediately start building screens, APIs and AI agents, they risk developing a solution that does not properly address the business problem.

| Key lesson: Use a structured translation process to move from business understanding to solution architecture. |
| :---- |

# **2\. The business-to-solution architecture translation chain**

| Stage | Core question | Customer identity verification example |
| :---- | :---- | :---- |
| 1\. Business capability | What must the business be able to do? | Identity Verification |
| 2\. Business process | How does the business perform this activity? | Collect and verify identity information |
| 3\. Business requirements | What must be achieved or supported? | Capture identity details and verification evidence |
| 4\. Solution capabilities | What must the solution be capable of doing? | Identity Verification Management |
| 5\. Logical solution components | What logical responsibilities should exist? | Identity Verification Component |

| Central reasoning chain: Business Capability → Business Process → Business Requirement → Solution Capability → Logical Solution Component |
| :---- |

# **3\. Stage 1 — Business Capability**

A business capability describes what an organisation must be able to do to achieve its objectives.

A bank may need capabilities such as:

* Customer Management  
* Customer Onboarding  
* Identity Verification  
* Risk Assessment  
* Customer Screening  
* Account Management

A capability does not describe a software application. Identity Verification remains a business capability even if the bank currently performs it manually.

| Important distinction: A capability describes what the business can do, not how it performs the activity or which technology it uses. |
| :---- |

# **4\. Stage 2 — Business Process**

A business process explains how the organisation performs an activity through an organised sequence of steps.

A simplified identity verification process might involve:

1. Receive customer identity information.  
2. Review identity documents.  
3. Perform identity verification checks.  
4. Assess the verification outcome.  
5. Proceed according to the process when checks are successful, or refer an exception for appropriate review.

A capability may support multiple processes, and a process may use multiple capabilities. The capability describes the ability; the process describes how that ability is exercised.

# **5\. Stage 3 — Business Requirements**

Business requirements express what the business needs the solution or its supporting operations to achieve.

| Example requirement | Description |
| :---- | :---- |
| REQ-001 | The solution must capture customer identity information. |
| REQ-002 | The solution must support identity document submission. |
| REQ-003 | The solution must record verification outcomes. |
| REQ-004 | The solution must support referral of unresolved verification cases for human review. |

Requirements are more specific than capabilities. A requirement should be sufficiently clear to support design, implementation and verification.

# **6\. Stage 4 — Solution Capabilities**

At this stage, the reasoning crosses from describing what the business must do to describing what the solution must be capable of providing.

| Business requirement | Possible solution capability |
| :---- | :---- |
| Capture customer identity information. | Customer Information Capture |
| Accept identity documents. | Document Submission |
| Record verification outcomes. | Verification Result Management |
| Refer unresolved cases for review. | Human Review Management |

A solution capability represents a functional ability that the solution must provide. It does not necessarily represent a separate software component.

# **7\. Stage 5 — Logical Solution Components**

Once solution responsibilities are understood, we can identify logical components that own or coordinate those responsibilities.

| Solution capability | Possible logical component |
| :---- | :---- |
| Customer Information Capture | Customer Information Component |
| Document Submission | Document Management Component |
| Verification Result Management | Verification Management Component |
| Human Review Management | Exception and Human Review Component |

| Important boundary: These are logical responsibilities, not yet decisions about microservices, containers, programming languages, databases, cloud platforms, AI models or frameworks. |
| :---- |

# **8\. Complete example — Customer onboarding**

| Architectural stage | Customer onboarding example |
| :---- | :---- |
| Business capability | Customer Onboarding |
| Business process | Receive application, capture information, verify identity and assess the application |
| Business requirement | The solution must capture customer information and support identity verification |
| Solution capability | Customer Information Management and Identity Verification |
| Logical component | Customer Information Component and Identity Verification Component |

Each stage should provide the reasoning for the next. Every proposed logical component should be traceable to a genuine business need.

# **9\. Where does AI-native engineering enter this translation?**

Once logical responsibilities are understood, we can consider how those responsibilities should be implemented. An identity verification responsibility might involve:

* Deterministic document-format validation.  
* OCR or document extraction.  
* AI-assisted interpretation of unclear information.  
* Verification against approved sources.  
* Human review of unresolved cases.

Not every responsibility requires an AI agent. AI-native architecture should select an appropriate combination of deterministic processing, AI-supported processing, human oversight and governance.

| Concern | Illustrative responsibility |
| :---- | :---- |
| Deterministic processing | Format checks, mandatory fields and defined validation rules. |
| AI-supported processing | Document interpretation and information extraction. |
| Human oversight | Review and resolution of cases requiring human judgement. |
| Governance | Permissions, auditability and controlled decision boundaries. |

| Key principle: Business-driven architecture becomes the foundation for AI-native solution design. AI should support the intended business process without bypassing required controls or human accountability. |
| :---- |

# **10\. Classroom exercise**

Scenario: A university is introducing a digital student enrolment solution. Consider the business capability “Student Enrolment”.

Ask students to identify:

6. One business process supporting this capability.  
7. Two business requirements.  
8. Two solution capabilities.  
9. Two possible logical components.

Facilitator guidance: Ask students to explain the reasoning connecting each stage. Encourage them to avoid jumping directly to a student portal, database, microservice or AI agent without first establishing the business and solution responsibilities.

## **Illustrative answer structure (not a prescribed design)**

| Stage | Student response |
| :---- | :---- |
| Business capability | Student Enrolment |
| Business process | For example, receive enrolment request, check eligibility, confirm course selection and record enrolment. |
| Business requirements | For example, capture enrolment requests and record eligibility outcomes. |
| Solution capabilities | For example, Enrolment Request Management and Eligibility Assessment. |
| Logical components | For example, Enrolment Management and Eligibility Assessment components. |

# **11\. Knowledge check**

Use these questions for individual reflection or a short classroom discussion.

10. What does a business capability primarily describe?  
11. Which architectural element explains how an organisation performs an activity through an organised sequence of steps?  
12. A requirement states that unresolved identity verification cases must be referred for human review. What is a plausible solution capability?  
13. What should a logical solution component be traceable to?

## **Suggested answers**

| Question | Suggested answer and reasoning |
| :---- | :---- |
| 1 | What the organisation must be able to do. A capability expresses an organisational ability independently of the process or technology used. |
| 2 | Business process. It describes the activities and their sequence. |
| 3 | Human Review Management. It supports the required referral and review function. |
| 4 | A business need and supporting solution responsibility. Logical components should be justified by responsibilities that trace back to business needs. |

# **12\. Key learning takeaways**

* A business capability describes what the business must be able to do.  
* A business process describes how the business performs an activity.  
* A business requirement expresses what must be achieved or supported.  
* A solution capability describes a functional ability the solution must provide.  
* A logical component represents a solution responsibility.  
* Logical components should be traceable to business needs.  
* Technology and implementation choices should not be made prematurely.  
* AI-native solutions combine deterministic processing, AI support, human oversight and governance.

# **13\. Transition to Topic 4**

The first three topics have established:

* Topic 1 — Enterprise Architecture: how the enterprise fits together.  
* Topic 2 — Solution Architecture: how a particular solution should be structured.  
* Topic 3 — Business-to-solution translation: how business needs lead to solution responsibilities.

| Next topic: Topic 4 — What are Architecture Domains and Architecture Layers? |
| :---- |

We will explore Business, Data, Application and Technology Architecture domains; logical versus physical architecture; architecture layers and their relationships; and how UI, application, domain and AI runtime concepts fit into a layered solution architecture.

After Topic 4, students will have a stronger foundation for architecture principles, constraints and quality attributes.