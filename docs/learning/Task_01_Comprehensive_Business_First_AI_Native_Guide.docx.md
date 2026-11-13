# **Business-First AI-Native** **Engineering Application(Business Problem , Intent , Value Model)**

**PHASE 1 · TASK 1 OF 15**

*Business Problem, Intent and Value Model*

Banking and Financial Services · AI-Native Customer Onboarding

| Comprehensive beginner-friendly project record. This edition combines the original business-direction discussion, the customer-onboarding problem definition, the banking-domain business case, the Claude Code implementation prompt, the reported execution results and the review/approval hand-off—in the order the work unfolded. |
| :---- |

# **Document guide and project status**

This document is an editable learning, implementation and governance record. It preserves the supplied discussions and distinguishes proposed ideas, provisional assumptions, reported execution evidence and review recommendations.

| Stage | What this document contains |
| :---- | :---- |
| A. Project direction | Why the project starts with a business problem and the initial choice of customer onboarding. |
| B. Initial customer onboarding analysis | General domain context, problem hypotheses, draft problem statement, stakeholder needs, intent and value hypotheses. |
| C. Banking domain selection | Banking-specific context, problem statement, objectives, stakeholders, journey, KPIs, AI opportunities, scope and constraints. |
| D. Formal Task 1 package | Artifact catalogue, Task 1 acceptance criteria and connection to Tasks 2–15. |
| E. Claude Code execution | Exact optimised Task 1 prompt and the execution report supplied by the user. |
| F. Review and hand-off | Review assessment, open decisions, working-baseline acceptance and Task 2 authorisation prompt. |

Important evidence note: the execution report states that 13 deliverables were created and 87 automated checks passed. Those results are reproduced as reported; this document does not independently inspect the project folder or rerun the checks.

# **PART A — Establish the new project and business direction**

## **1\. New independent project**

Project: Business-First AI-Native Engineering Application. This is a new independent project, separate from the earlier AI-native application project that had its own completed 15-task implementation. The previous project must remain untouched.

The new project follows a 15-task roadmap organised into five phases. Task 1 belongs to Phase 1—Business Understanding and Value Definition.

## **2\. Why business-first engineering?**

The first task is not to choose an AI model, technology stack or application architecture. It is to understand the business problem, why it matters, who experiences it, what value should be created and how success will be measured.

The governing principle is: understand the business problem before designing the application that solves it.

## **3\. Initial business-direction choices**

| Potential direction | Focus |
| :---- | :---- |
| Enterprise business process transformation | Transform complex business processes into structured, intelligent applications. |
| Finance and financial decision support | Support financial analysis, planning and decision workflows. |
| Customer onboarding and service automation | Improve the end-to-end customer onboarding journey. |
| AI-native software engineering and development automation | Apply AI-native methods to software engineering work. |
| Another business problem | Select a different business opportunity. |

## **4\. Selected direction and initial problem statement**

Selected business direction: Customer onboarding.

Initial problem statement: “A model driven AI native customer on boarding application.”

This initial wording identifies the intended application direction, but it is not yet a complete business problem statement. The following analysis turns it into a business-led problem definition.

## **5\. Seven areas to establish in Task 1**

* Business context — What is happening in the business?  
* Problem definition — What problem are we trying to solve?  
* Stakeholders and customers — Who experiences the problem?  
* Business intent — What should change?  
* Value hypothesis — What measurable benefits should result?  
* Constraints and assumptions — What boundaries must we respect?  
* Success measures — How will we know the solution has worked?

## **6\. First expected business artifacts**

| Artifact | Purpose |
| :---- | :---- |
| Business Problem Statement | Precisely defines the problem. |
| Business Context Document | Explains the current business situation. |
| Stakeholder Map | Identifies affected parties. |
| Business Intent Model | Defines the desired future state. |
| Value Hypothesis | Explains expected business benefits. |
| KPI and Success Model | Defines measurable outcomes. |
| Business Case | Consolidates the rationale for investment. |

These artifacts should be structured and machine-readable where appropriate so that they can feed into model-driven specifications in later tasks.

# **PART B — Initial customer-onboarding business analysis**

## **7\. Business context: what is customer onboarding?**

Customer onboarding is the process through which an organisation establishes a relationship with a new customer and makes that customer ready to use its products or services. Depending on the organisation, it may involve:

* Capturing customer information.  
* Identifying and verifying the customer.  
* Collecting supporting documents.  
* Validating submitted information.  
* Checking eligibility.  
* Performing risk and compliance assessments.  
* Obtaining approvals.  
* Creating customer accounts or profiles.  
* Activating products or services.  
* Communicating onboarding progress to the customer.

The process may involve customers, customer-service representatives, operations teams, compliance officers, relationship managers and external systems.

## **8\. Why onboarding matters**

| Business dimension | Intended improvement |
| :---- | :---- |
| Customer experience | Simpler, clearer and more transparent onboarding. |
| Operational efficiency | Less repetitive manual processing. |
| Processing speed | Shorter time from application to activation. |
| Data quality | More complete and accurate customer information. |
| Compliance | Consistent execution of required controls. |
| Decision quality | Better-supported eligibility and risk decisions. |
| Business growth | Higher completion and conversion rates. |

These are potential benefits, not established outcomes. Actual baselines and targets must be defined after understanding the selected business context.

## **9\. Illustrative current-state journey**

* Customer submits an onboarding application.  
* Operations team receives customer information.  
* Staff check application completeness.  
* Supporting documents are collected and examined.  
* Customer information is verified against relevant records.  
* Eligibility and risk checks are performed.  
* Exceptions are referred to relevant teams for review.  
* Approvals are obtained.  
* Customer account or profile is created.  
* Customer is notified and the service is activated.

Illustrative process only. The actual process, order and control requirements depend on the organisation and industry. Multiple departments and applications may be involved; information may be transferred, re-entered, checked repeatedly or passed between teams.

## **10\. Initial problem hypotheses**

| No. | Potential business problem | Possible consequence |
| :---- | :---- | :---- |
| 1 | Fragmented onboarding processes | Inconsistent customer experience. |
| 2 | Repeated manual data entry | Higher operational effort and errors. |
| 3 | Unstructured document submissions | Delays in extracting and validating information. |
| 4 | Incomplete applications | Repeated customer interactions. |
| 5 | Disconnected systems | Limited end-to-end visibility. |
| 6 | Rule and policy complexity | Inconsistent or delayed decisions. |
| 7 | Manual exception handling | Operational bottlenecks. |
| 8 | Limited progress visibility | Customer dissatisfaction and enquiries. |
| 9 | Weak performance monitoring | Difficulty identifying process inefficiencies. |

These are hypotheses to investigate, not confirmed facts about a particular organisation.

## **11\. Initial draft business problem statement**

Organizations need to onboard customers through processes that may involve multiple information sources, document submissions, validation activities, eligibility assessments, approvals and operational hand-offs.

When these activities are fragmented, heavily dependent on manual processing or supported by disconnected systems, organizations may experience delays, repeated data handling, inconsistent processing, limited visibility and increased operational effort.

There is an opportunity to establish a unified, model-driven customer-onboarding capability that coordinates the onboarding journey, manages customer information, supports document interpretation and verification, applies defined business rules, assists with appropriate decisions and provides visibility across the process.

The proposed application will explore how AI models, deterministic business logic and controlled workflows can work together to improve customer experience, operational efficiency, data quality and decision support while maintaining appropriate governance and human oversight.

## **12\. Initial scope boundary**

| Proposed in-scope capabilities | Potentially outside initial scope |
| :---- | :---- |
| Customer application intake | Full enterprise CRM replacement |
| Customer information management | Complete replacement of core banking/ERP systems |
| Document collection and interpretation | Unrestricted autonomous approval |
| Data completeness and validation | Unsupervised regulatory decisions |
| Business-rule execution | Replacement of all human compliance responsibilities |
| Eligibility and risk decision support | Full enterprise risk-management platform |
| Exception and approval workflows | Every possible back-office process |
| Customer status and notifications | Full marketing automation |

This is a business capability boundary, not a technology architecture.

## **13\. Initial stakeholder groups**

| Stakeholder | Need / expected support |
| :---- | :---- |
| Customer | Simple application, clear instructions, minimal repeated requests and timely updates. |
| Customer-service / onboarding officer | Unified view of applications, customer information, missing documents and pending activities. |
| Operations manager | Process visibility, workload management, turnaround reporting and exception monitoring. |
| Compliance and risk officer | Traceable checks, documented evidence, policy compliance and appropriate escalation. |
| Business owner / management | Customer conversion, operating efficiency, lower costs and measurable performance. |
| Technology, security, data governance and audit | Secure integration, access controls, data governance and evidence of control execution. |

## **14\. Initial business intent**

Create a unified, intelligent and governed customer-onboarding experience.

Enable organisations to manage the customer-onboarding lifecycle through a model-driven platform that combines structured business workflows, deterministic validation, AI-powered interpretation and decision support, and accountable human oversight.

Intended result: a more efficient, transparent, accurate and customer-centric onboarding process.

## **15\. Initial business objectives**

* Simplify the customer onboarding journey.  
* Reduce avoidable manual processing.  
* Improve customer-data completeness and quality.  
* Accelerate appropriate verification and decision processes.  
* Improve visibility and accountability across onboarding activities.  
* Maintain compliance, security and auditability.

## **16\. Initial value hypotheses**

| Value area | Hypothesis | Example measure |
| :---- | :---- | :---- |
| Customer experience | A simpler process will improve completion. | Application completion rate. |
| Operational efficiency | Automation of repetitive activities will reduce handling effort. | Average staff handling time. |
| Processing speed | Better coordination will reduce delays. | End-to-end onboarding time. |
| Data quality | Structured intake and validation will reduce incomplete records. | First-time-right rate. |
| Decision support | Better information extraction and case presentation will support timely reviews. | Decision turnaround time. |
| Compliance | Consistent workflows and traceable evidence will strengthen controls. | Control exceptions and audit findings. |
| Business growth | Fewer avoidable drop-offs may improve conversion. | Application-to-activation conversion. |

## **17\. Illustrative value calculation**

Assume 10,000 applications per month and 30 minutes of manual handling per application:

10,000 × 30 \= 300,000 minutes \= 5,000 staff-hours per month.

If a redesigned process reduced average manual handling time by 20%, the illustrative potential saving would be 5,000 × 20% \= 1,000 hours per month.

This is an illustrative scenario only—not a forecast, committed target or demonstrated AI benefit. Actual benefits require baseline measurements and process analysis.

## **18\. Initial assumptions and constraints**

| ID | Initial assumption | Why it matters |
| :---- | :---- | :---- |
| A01 | The organisation receives customer information from digital or assisted channels. | Defines intake. |
| A02 | Applications may contain structured and unstructured information. | Helps assess document AI usefulness. |
| A03 | Some decisions can be represented as explicit business rules. | Supports deterministic processing. |
| A04 | Some information may require interpretation or contextual analysis. | Identifies possible AI use cases. |
| A05 | Some cases require human review and approval. | Establishes accountability. |
| A06 | The organisation needs an auditable record of onboarding activities. | Influences governance and traceability. |
| A07 | Existing systems may need integration. | Influences enterprise architecture and scope. |

* Customer privacy and personal-data protection.  
* Information security and access controls.  
* Applicable identity verification and compliance obligations.  
* Data retention and audit requirements.  
* Accuracy and reliability of extracted information.  
* Model uncertainty and potentially incorrect AI outputs.  
* Human approval for designated high-impact decisions.  
* Integration constraints and operational cost.

The exact regulatory obligations cannot be finalised until the industry and jurisdiction are confirmed.

# **PART C — Confirm banking and financial services as the primary context**

## **19\. Industry decision**

Selected primary industry: Banking and financial services. Proposed business domain: digital customer onboarding. Working customer segment: individual retail banking customers. This is a starting assumption, not a restriction on the future platform.

Banking is a rich enterprise reference scenario because onboarding involves customer experience, identity verification, customer due diligence, risk assessment, operational decisions, integration and auditability. It also demonstrates how deterministic software and probabilistic AI can work together in a governed application.

The business case is a proposed reference scenario, not a claim about a particular bank's current performance.

## **20\. Banking customer onboarding context**

Banking customer onboarding is the end-to-end process through which a bank establishes a relationship with a new customer and enables access to an agreed banking product or service. For an individual retail customer, this may include:

* Customer registration and application submission.  
* Personal information collection.  
* Identity document collection and verification.  
* Customer identification and due diligence.  
* Address and other information verification.  
* Applicable sanctions and risk screening.  
* Customer risk assessment and review.  
* Account eligibility and product selection.  
* Compliance and operational approvals.  
* Customer record and account creation.  
* Account activation and customer notification.

The precise activities, evidence and approval requirements depend on the bank, product, customer type and applicable jurisdiction.

## **21\. Why this process matters to a bank**

| Business dimension | Why it matters |
| :---- | :---- |
| Customer acquisition | A difficult application journey can discourage prospective customers. |
| Customer experience | Customers expect clear instructions and timely updates. |
| Operational efficiency | Manual reviews and repeated data entry consume staff capacity. |
| Data quality | Incorrect customer information can affect downstream banking operations. |
| Compliance | Required customer due diligence and other controls must be applied consistently. |
| Risk management | Potentially suspicious, incomplete or higher-risk cases require appropriate handling. |
| Revenue generation | Delayed account activation can delay access to banking products and services. |

The objective is not simply to open accounts faster. It is to onboard eligible customers efficiently while preserving appropriate controls and customer protection.

## **22\. Banking-specific problem hypotheses**

| ID | Potential problem | Possible business impact |
| :---- | :---- | :---- |
| P01 | Customer information is captured through disconnected channels. | Repeated data entry and inconsistent records. |
| P02 | Documents arrive in different formats and qualities. | Manual interpretation and processing delays. |
| P03 | Customer information is incomplete or inconsistent. | Repeated customer contact and rework. |
| P04 | Verification activities are spread across systems. | Limited visibility and operational delays. |
| P05 | Business rules and policy requirements are complex. | Inconsistent processing or incorrect routing. |
| P06 | Higher-risk or unusual cases need additional investigation. | Increased exception-handling workload. |
| P07 | Approval activities involve multiple stakeholders. | Handoffs and approval bottlenecks. |
| P08 | Customers have limited visibility of application progress. | More enquiries and customer dissatisfaction. |
| P09 | Management lacks consolidated operational insights. | Difficulty identifying bottlenecks and measuring performance. |

These hypotheses require validation through business interviews, process observation and operational data. A bank may not experience all nine.

## **23\. Formal banking business problem statement — Draft v1.0**

Banks need to onboard new customers through a controlled process involving customer information collection, identity verification, customer due diligence, risk screening, eligibility assessment, approvals and account activation.

However, where these activities are supported by fragmented processes, disconnected information sources, manual document handling and complex operational handoffs, banks may experience avoidable processing delays, repeated work, inconsistent data, limited application visibility and increased operational effort.

The business opportunity is to establish a unified, model-driven customer-onboarding capability that coordinates the end-to-end journey, manages customer information, supports document interpretation and verification, executes defined business rules, assists appropriate risk and operational assessments, and provides traceability across onboarding activities.

The proposed application will combine deterministic business processes with probabilistic AI capabilities where they provide measurable value, while maintaining appropriate policy enforcement, human accountability, security and auditability.

## **24\. Banking business intent and objectives**

Business intent: Create a unified, intelligent and governed banking customer-onboarding experience.

Enable banks to manage the customer-onboarding lifecycle through a model-driven application that combines structured business workflows, deterministic verification and policy rules, AI-powered interpretation and decision support, and accountable human oversight.

| Objective | Intended result |
| :---- | :---- |
| BO1 — Improve customer experience | Make application submission, information requests and progress tracking clearer. |
| BO2 — Improve operational efficiency | Reduce avoidable manual work, duplication and rework. |
| BO3 — Improve information quality | Improve completeness, consistency and accuracy of customer records. |
| BO4 — Improve processing efficiency | Coordinate verification, screening, review and approval activities. |
| BO5 — Strengthen risk and compliance operations | Support consistent execution and traceability of required controls. |
| BO6 — Improve management visibility | Provide insight into application volumes, processing time, exceptions and outcomes. |

## **25\. Banking stakeholder analysis**

| Stakeholder | Primary need | Expected application support |
| :---- | :---- | :---- |
| Prospective customer | Simple and transparent onboarding. | Guided application, document submission, status updates. |
| Relationship manager / branch officer | Customer application visibility. | Customer profile, application status, missing information. |
| Onboarding operations officer | Efficient case processing. | Work queues, verification results, exception handling. |
| KYC / due-diligence officer | Reliable customer information and evidence. | Document evidence, verification records, review workflow. |
| Compliance and risk officer | Policy adherence and appropriate escalation. | Risk indicators, screening outcomes, case review and audit trail. |
| Operations manager | Operational control and performance. | Workload, turnaround time, bottleneck and exception reporting. |
| Business owner | Customer growth and operational value. | Conversion, onboarding cost, activation and customer-experience KPIs. |
| Technology and security teams | Secure and maintainable integration. | APIs, identity controls, access management, monitoring. |
| Internal audit | Evidence of control execution. | Decision history, timestamps, approvals and audit records. |

## **26\. Proposed banking onboarding journey**

* Customer application initiation — customer selects a banking product and begins an application.  
* Customer information capture — personal information and required declarations are collected.  
* Document submission and interpretation — documents are submitted; AI may extract and interpret relevant information.  
* Information validation — deterministic checks validate mandatory fields, formats and consistency.  
* Identity verification and due diligence — relevant verification and due-diligence checks are performed.  
* Screening and risk assessment — applicable screening and risk processes are executed using approved data and policies.  
* Exception and human review — uncertain, conflicting or higher-risk cases are routed to authorised officers.  
* Eligibility and approval — decisions are made under the bank's approved policy and authorisation framework.  
* Account creation and activation — approved applications proceed to appropriate account-opening systems.  
* Customer notification and monitoring — customer receives updates and the bank monitors onboarding performance.

This is a proposed logical journey, not a legally prescribed sequence. Actual checks and ordering must be validated for the selected jurisdiction and products. Detailed process modelling belongs in Task 3\.

## **27\. Banking value proposition**

* For customers: a simpler, more transparent application experience with fewer avoidable information requests.  
* For operations teams: a unified view of applications, documents, validation results, exceptions and pending decisions.  
* For compliance and risk teams: better-organised evidence, consistent workflow execution and traceable reviews.  
* For management: improved visibility into onboarding efficiency, customer conversion, operating costs and process performance.

## **28\. Candidate banking KPIs**

| KPI | What it measures | Proposed measurement |
| :---- | :---- | :---- |
| Application completion rate | Customers completing applications. | Completed applications ÷ initiated applications. |
| Onboarding turnaround time | Time to complete onboarding. | Median time from submission to activation. |
| First-time-right rate | Applications processed without avoidable rework. | Applications completed without correction ÷ completed applications. |
| Document acceptance rate | Documents accepted without resubmission. | Documents accepted first time ÷ documents submitted. |
| Manual handling time | Staff effort per application. | Average active staff-processing time. |
| Exception rate | Applications requiring exception handling. | Exception applications ÷ submitted applications. |
| Approval turnaround time | Time taken for required approvals. | Median time from review request to decision. |
| Cost per onboarded customer | Operational cost of successful onboarding. | Total attributable onboarding cost ÷ customers onboarded. |
| Customer satisfaction | Customer perception of onboarding. | Survey or defined customer feedback measure. |
| Control exception rate | Deviations from required controls. | Recorded control exceptions ÷ relevant applications. |

These are candidate KPIs. The bank must select measures aligned with actual objectives and data availability.

## **29\. Banking illustrative value calculation**

Assumptions: 10,000 monthly applications; 30 minutes of manual handling per application; hypothetical 20% reduction in average manual handling time.

10,000 × 30 \= 300,000 minutes. 300,000 ÷ 60 \= 5,000 hours per month. 5,000 × 20% \= 1,000 hours per month of illustrative potential reduction.

This is not a forecast, committed target or demonstrated AI benefit. A defensible financial case requires actual staffing costs, processing volumes, baseline handling times, implementation costs, model usage costs, integration costs and ongoing operational expenses.

## **30\. Where AI may create value**

| Business activity | Proposed approach | Reason / control principle |
| :---- | :---- | :---- |
| Mandatory field validation | Deterministic rules. | Exact, predictable requirements. |
| Document classification | AI model where justified. | Documents may vary in format and appearance. |
| Information extraction | AI model plus validation. | Interpret unstructured documents, then validate extracted fields. |
| Customer-data consistency | Deterministic checks; AI assistance where useful. | Exact comparisons and defined tolerances. |
| Identity verification | Approved verification service and deterministic controls. | Requires reliable evidence and policy compliance. |
| Sanctions screening | Approved screening systems and governed review. | High-impact compliance process. |
| Customer risk assessment | Approved risk methodology; analytics may assist. | Must follow approved policy and validation requirements. |
| Ambiguous case interpretation | AI-assisted analysis with human review. | Contextual interpretation may be useful. |
| Approval and account activation | Authorised deterministic workflow. | Must respect policy, permissions and approval authority. |
| Customer communication | AI-assisted language generation with approved templates and controls. | May improve clarity and personalisation. |

Important principle: an AI model may interpret information, estimate possibilities and recommend an action. It must not bypass approved policy or independently authorise a regulated or high-impact decision merely because it reports a high confidence score. These boundaries will be examined systematically in Task 5\.

## **31\. Banking scope, assumptions and constraints**

| Proposed initial scope | Not assumed to be included initially |  |
| :---- | :---- | :---- |
| Individual retail customer application intake | Replacement of the bank's core banking system |  |
| Customer information management | Complete replacement of enterprise CRM |  |
| Document upload and interpretation | Unrestricted autonomous customer approval |  |
| Data validation | Replacement of identity-verification providers |  |
| Onboarding workflow orchestration | Full enterprise compliance platform |  |
| Rule-based eligibility workflow | Autonomous sanctions or AML clearance |  |
| Exception and approval handling | Autonomous high-impact risk decisions |  |
| Application status and reporting | Replacement of all existing operational systems |  |
| Governed AI capabilities | Unrestricted agent access to banking systems |  |
| **ID** | **Assumption** | **Validation needed** |
| A01 | Customers can apply through digital or assisted channels. | Confirm channels. |
| A02 | Customer documents may be structured or unstructured. | Identify document types. |
| A03 | The bank has approved onboarding policies and business rules. | Obtain policy owners and rule sources. |
| A04 | Some documents can benefit from AI interpretation. | Evaluate document types and baseline performance. |
| A05 | Some applications require manual review. | Identify escalation criteria. |
| A06 | Existing banking systems need integration. | Identify systems and integration constraints. |
| A07 | Onboarding actions must be traceable. | Confirm audit and retention requirements. |

* Customer privacy and personal-data protection.  
* Banking secrecy and confidentiality requirements.  
* Applicable KYC and customer due-diligence obligations.  
* AML/CTF controls, where applicable.  
* Sanctions-screening requirements, where applicable.  
* Secure authentication and role-based authorisation.  
* Data quality, integrity and retention.  
* Model accuracy, uncertainty and explainability appropriate to each use case.  
* Human review and approval for designated decisions.  
* Third-party service and AI model governance.

These are business and architectural considerations, not a complete legal compliance assessment. Jurisdiction-specific requirements remain pending.

## **32\. Investment rationale and consolidated Business Case Canvas**

| Dimension | Investment rationale |
| :---- | :---- |
| Customer value | Reduce friction and improve transparency throughout onboarding. |
| Operational value | Reduce repetitive work, unnecessary hand-offs and avoidable rework. |
| Risk and control value | Improve evidence management, process consistency and traceability. |
| Management value | Provide better operational and business performance insights. |
| Strategic value | Establish a reusable model-driven platform capable of incorporating AI where justified. |

## **Business Case Canvas — Banking Customer Onboarding · Draft v1.0**

| Canvas element | Current proposed definition |
| :---- | :---- |
| Business opportunity | Improve the end-to-end onboarding experience and operational efficiency for individual retail banking customers. |
| Business problem | Fragmented processes, manual document handling, inconsistent customer information, operational hand-offs and complex verification activities may create delays, rework and limited visibility. |
| Business intent | Establish a unified, intelligent and governed customer-onboarding experience. |
| Target stakeholders | Customers, relationship managers, onboarding officers, operations managers, KYC and compliance officers, risk teams, business owners, IT and audit. |
| Proposed business capabilities | Customer application and information management; document management and interpretation; identity verification and due-diligence coordination; rules and eligibility management; screening and risk workflow coordination; exception and approval management; account activation coordination; customer communication and status tracking; performance monitoring and reporting. |
| AI value proposition | AI for document interpretation, information extraction, contextual assistance and appropriate decision support, combined with deterministic rules, approved verification services and human oversight. |
| Expected benefits | Improved customer experience, reduced manual effort, faster processing, improved data quality, better operational visibility and more consistent control execution. |
| Success measures | Completion rate, onboarding turnaround time, first-time-right rate, manual handling time, exception rate, cost per onboarded customer, customer satisfaction and control exceptions. |
| Major constraints | Privacy, banking confidentiality, regulatory compliance, security, auditability, model uncertainty, integration and operational cost. |

# **PART D — Formal Task 1 package and connection to the roadmap**

## **33\. Formal Task 1 artifact package**

| Artifact ID | Artifact | Format |
| :---- | :---- | :---- |
| BIZ-001 | Business Context and Problem Statement | Markdown |
| BIZ-002 | Business Case and Value Model | YAML plus readable document |
| BIZ-003 | Stakeholder Register | YAML / table |
| BIZ-004 | Business Objectives and KPI Catalogue | YAML / table |
| BIZ-005 | Assumptions, Constraints and Risks Register | YAML |
| BIZ-006 | Business Case Approval Record | Structured document |

The Claude Code execution produced a more detailed artifact set, including BIZ-007 AI Opportunity Assessment, BIZ-008 Scope and Boundaries, journey diagrams and validation records. The formal package above was the earlier recommended minimum; the implementation expanded it.

## **34\. How Task 1 connects to Tasks 2–15**

| Task / group | How it uses Task 1 |
| :---- | :---- |
| Task 2 — Business Architecture and Capability Modelling | Converts business intent into capabilities, stakeholders, value streams and a business architecture blueprint. |
| Task 3 — Operational Blueprint, Requirements and Decision Modelling | Describes onboarding operations, processes, requirements and decisions. |
| Task 4 — Enterprise and Solution Architecture | Maps business capabilities to enterprise and solution architecture. |
| Task 5 — Rules, Analytics and AI Decision Framework | Determines which activities need rules, analytics, AI or human judgement. |
| Task 6 — Structured Specifications and UISpec Contract | Converts approved requirements into structured specifications. |
| Tasks 7–9 — Harness and agentic engineering | Establish repository architecture, engineering harness and agentic workflow. |
| Tasks 10–12 — AI-native application implementation | Build the application and runtime AI capabilities. |
| Tasks 13–15 — Evaluation and production readiness | Evaluate, improve, govern and prepare the application for production. |

The chain to preserve throughout the project is:

**Business intent → Business architecture → Operational models → Solution architecture → Specifications → AI-native implementation → Verification → Business outcomes**

## **35\. Task 1 completion criteria**

| Criterion | Status at initial business discussion |
| :---- | :---- |
| Initial business direction selected | Complete |
| Business context established | Drafted |
| Initial problem statement drafted | Complete |
| Stakeholder groups identified | Drafted |
| Business intent articulated | Drafted |
| Value hypotheses defined | Proposed |
| Initial assumptions and constraints recorded | Drafted |
| Business and technical success measures proposed | Proposed |
| Industry and operating context confirmed | Initially pending; banking later selected |
| Business case reviewed and approved | Pending |

After banking was selected, the business context and case were refined. Actual bank baselines, financial validation and jurisdiction-specific compliance validation remained pending.

## **36\. Task 1 completion status after Claude execution**

| Area | Status |
| :---- | :---- |
| Industry and business domain | Banking and financial services selected; customer onboarding. |
| Business context and problem | Drafted in BIZ-001. |
| Business case and value model | Drafted in BIZ-002. |
| Stakeholders | 20 roles reported in BIZ-003. |
| Objectives and KPIs | 8 objectives and 25 KPIs reported in BIZ-004. |
| Assumptions, constraints and risks | 10 hypotheses, 14 assumptions, 9 constraints, 17 risks, 8 dependencies, 13 decisions and 16 questions reported in BIZ-005. |
| Customer journey | 13 stages; diagrams embedded in BIZ-006 and separate .mmd files. |
| AI opportunity assessment | 13 activities classified, 9 AI opportunities, 5 rejected/deferred uses reported in BIZ-007. |
| Scope and boundaries | 13 provisional capabilities, 13 in-scope and 13 out-of-scope items, 10 AI boundary rules reported in BIZ-008. |
| Validation | 87/87 automated checks reported passing. |
| External validation- | Pending. |

# **PART E — Claude Code implementation**

## **37\. How the prompt was intended to be used**

The optimised prompt was designed for Claude Code in a terminal. The operator first creates and opens a dedicated, empty project directory, then runs Claude Code from that directory. The prompt instructs Claude to inspect the workspace, maintain isolation, create documentation artifacts, validate them and stop after Task 1\.

The exact prompt below is reproduced as supplied earlier in the discussion.

Create a directory using powershell and invoke claude

mkdir ai-native-customer-onboarding

cd ai-native-customer-onboarding

claude 

## **38\. Exact Task 1 Claude Code prompt**

| \# CLAUDE CODE EXECUTION PROMPT \# TASK 01 — BUSINESS PROBLEM, INTENT AND VALUE MODEL   \#\# 1\. YOUR ROLE   Act as a Senior Enterprise Business Architect, Banking Domain Analyst, Business Analyst and AI-Native Engineering Architect.   You are responsible for executing Task 01 of a new, independent AI-Native Customer Onboarding Application project.   Do not merely explain what needs to be done. Perform the work, create the actual project artifacts, validate them and report the results.   Work systematically and maintain enterprise-grade documentation standards.   \---   \#\# 2\. PROJECT IDENTITY   Project name: AI-Native Customer Onboarding Application   Industry: Banking and Financial Services   Business domain: Customer Onboarding   Initial customer segment: Individual retail banking customers (provisional assumption).   Engineering approach: Business-first, model-driven, AI-native engineering.   Project objective:   Establish a business-driven foundation for a customer onboarding application that combines structured workflows, deterministic business rules, AI-powered interpretation and decision support, human oversight and governed execution.   Do not assume a specific bank, country or regulatory jurisdiction.   Record jurisdiction-specific regulatory requirements as pending validation.   \---   \#\# 3\. CRITICAL PROJECT ISOLATION RULE   This is a completely NEW and INDEPENDENT project.   There is an earlier AI-native application project containing 15 completed tasks. That project must remain entirely untouched.   You MUST:   \- Work exclusively within the current dedicated project directory. \- Never modify files outside the current project directory. \- Never access or modify the previous project's source code, Git history, checkpoints, task records or artifacts. \- Never overwrite existing files without explicit approval. \- Never copy previous project implementation artifacts into this project. \- Maintain independent documentation, specifications and checkpoints.   Before doing any work:   1\. Inspect the current working directory. 2\. Confirm its location. 3\. Inspect whether it contains existing project files. 4\. Check whether it belongs to an existing Git repository. 5\. Confirm that it is a dedicated workspace for this new project.   If the current directory is inside the previous project, or its identity is uncertain, STOP and explain the issue before making changes.   Do not delete, move or clean up existing files.   \---   \#\# 4\. EXECUTION PROTOCOL   Execute this task in the following stages.   \#\#\# Stage 1 — Workspace verification   \- Inspect the working directory. \- Confirm project isolation. \- Establish the project documentation structure. \- Create a project-level README.md. \- Create a task-level execution record.   Do not initialise a new Git repository unless explicitly authorised.   \#\#\# Stage 2 — Business discovery and analysis   Analyse the banking customer onboarding domain.   Investigate the following business areas:   \- Customer onboarding lifecycle. \- Customer information capture. \- Document collection and interpretation. \- Identity verification. \- Customer due diligence. \- Applicable screening processes. \- Risk assessment. \- Exception handling. \- Human review and approval. \- Account creation and activation. \- Customer communication and status visibility.   Identify potential operational challenges, dependencies, information flows and business opportunities.   Distinguish clearly between:   \- Confirmed project decisions. \- Business assumptions. \- Hypotheses requiring validation. \- Illustrative examples. \- Outstanding questions.   Do not present assumed banking practices as universal facts.   \#\#\# Stage 3 — Business problem and intent definition   Create:   1\. Business context. 2\. Business problem statement. 3\. Root-cause hypotheses. 4\. Business consequences. 5\. Business opportunity. 6\. Business vision. 7\. Business intent. 8\. Value proposition.   The business problem must explain why the application is required, not prescribe technology prematurely.   \#\#\# Stage 4 — Stakeholder and business objective modelling   Identify the relevant stakeholders, their responsibilities, business needs and decision authority.   Develop measurable business objectives covering:   \- Customer experience. \- Operational efficiency. \- Information accuracy. \- Onboarding turnaround time. \- First-time-right processing. \- Exception management. \- Risk and compliance control effectiveness. \- Management visibility.   Create a KPI catalogue with:   \- KPI ID. \- KPI name. \- Definition. \- Calculation formula. \- Unit of measurement. \- Business objective. \- Potential data source. \- Baseline status. \- Target status. \- Measurement frequency.   Do not invent actual bank performance baselines or approved targets.   \#\#\# Stage 5 — Customer onboarding journey   Model the high-level current-state and proposed future-state customer journeys.   Include the following potential stages:   1\. Application initiation. 2\. Customer information capture. 3\. Document submission. 4\. Document interpretation and extraction. 5\. Information validation. 6\. Identity verification. 7\. Customer due diligence. 8\. Applicable screening. 9\. Risk assessment. 10\. Exception handling and human review. 11\. Eligibility and approval. 12\. Account creation and activation. 13\. Customer notification.   Produce readable Mermaid diagrams.   Clearly label the current-state model as provisional where actual bank processes are not available.   \#\#\# Stage 6 — AI opportunity and decision assessment   Evaluate each major onboarding activity and classify the appropriate approach:   \- Deterministic business rules. \- Conventional analytics. \- AI/ML. \- Generative AI. \- Human judgement. \- Hybrid approach.   For each proposed AI opportunity, document:   \- Business problem addressed. \- Proposed AI capability. \- Expected business value. \- Required data. \- Reliability requirements. \- Potential failure modes. \- Human oversight. \- Deterministic validation or control. \- Auditability requirements.   Apply these principles:   \- Do not introduce AI without a justified business benefit. \- Do not treat model confidence as proof of correctness. \- Do not allow AI to bypass business rules or banking policies. \- Do not give agents unrestricted access to banking systems. \- Keep authorised approval and account activation within controlled workflows. \- Treat high-impact decisions with appropriate human accountability and governance.   \#\#\# Stage 7 — Scope, assumptions, constraints and risks   Define the initial in-scope and out-of-scope capabilities.   Potential initial scope:   \- Individual retail customer application intake. \- Customer information capture. \- Document upload and interpretation. \- Information validation. \- Onboarding workflow coordination. \- Due-diligence and screening workflow coordination. \- Risk assessment support. \- Exception management. \- Human approval workflow. \- Account activation coordination. \- Application status visibility. \- Operational reporting.   Potential exclusions:   \- Replacement of the core banking system. \- Replacement of the complete CRM ecosystem. \- Unrestricted autonomous customer approval. \- Autonomous regulatory decisions. \- Replacement of existing identity verification providers. \- Full enterprise-wide compliance platform. \- Unrestricted AI-agent access.   Create structured registers for:   \- Assumptions. \- Constraints. \- Risks. \- Dependencies. \- Open decisions.   Assign IDs to each item and indicate its validation status.   \#\#\# Stage 8 — Business case consolidation   Create a consolidated Business Case and Value Model.   It must connect:   Business Problem → Business Opportunity → Business Objectives → Required Capabilities → AI Opportunities → Expected Benefits → KPIs → Business Value.   Where financial data is unavailable, define a value calculation methodology rather than inventing monetary benefits.   \---   \#\# 5\. REQUIRED PROJECT ARTIFACTS   Create the following directory structure:   ai-native-customer-onboarding/   README.md   docs/     business/       BIZ-001-business-context-and-problem-statement.md       BIZ-002-business-case-and-value-model.md       BIZ-003-stakeholder-register.yaml       BIZ-004-business-objectives-and-kpi-catalogue.yaml       BIZ-005-assumptions-constraints-and-risks.yaml       BIZ-006-customer-onboarding-journey.md       BIZ-007-ai-opportunity-assessment.yaml       BIZ-008-scope-and-boundaries.yaml     diagrams/       current-state-journey.mmd       proposed-future-state-journey.mmd   validation/     task-01-validation-report.md     task-01-completion-record.md   If the current directory is already the project root, do not create another nested project directory.   Use Markdown for human-readable documentation.   Use YAML for structured, machine-readable business models.   Use Mermaid for process and journey diagrams.   Maintain consistent identifiers and cross-references across all artifacts.   \---   \#\# 6\. MODEL QUALITY AND TRACEABILITY   Establish traceability across the business artifacts.   At minimum, ensure:   \- Every business problem links to one or more objectives. \- Every objective has an associated KPI or measurement approach. \- Every proposed capability supports a business objective. \- Every AI opportunity addresses a defined business problem. \- Every material risk has an associated control or mitigation. \- Every assumption requiring validation is recorded. \- Every major scope decision is documented.   Use stable identifiers such as:   \- BP-001: Business Problem. \- BO-001: Business Objective. \- KPI-001: Performance Indicator. \- STK-001: Stakeholder. \- CAP-001: Business Capability (provisional reference only). \- AI-001: AI Opportunity. \- RSK-001: Risk. \- ASM-001: Assumption.   Do not create detailed Task 2 capability models yet. Only introduce provisional capability references where necessary for traceability.   \---   \#\# 7\. VALIDATION AND VERIFICATION   After generating the artifacts:   1\. Validate YAML syntax using available local tools. 2\. Validate Mermaid diagram structure as far as available tools permit. 3\. Check Markdown files for completeness. 4\. Check identifier consistency. 5\. Check cross-document traceability. 6\. Check that no unsupported regulatory claims have been introduced. 7\. Check that AI controls and human oversight are adequately documented. 8\. Check that all outstanding assumptions and decisions are visible.   Do not install additional software or packages without asking first.   Do not claim that a validation has passed unless it has actually been performed.   If a validation tool is unavailable, report that limitation explicitly.   \---   \#\# 8\. HUMAN REVIEW AND APPROVAL GATE   Do not assume that generating an artifact means that it is approved.   Use the following statuses:   \- DRAFT \- UNDER\_REVIEW \- VALIDATED \- APPROVED \- PENDING\_EXTERNAL\_CONFIRMATION   Identify the items that require business-owner, banking-domain, compliance or regulatory confirmation.   Produce a list of unresolved questions that must be answered before final business-case approval.   Do not fabricate stakeholder approval or external confirmation.   \---   \#\# 9\. TASK 1 ACCEPTANCE CRITERIA   Task 1 is ready for review only when:   \- Business context is documented. \- Business problem is clearly articulated. \- Business intent and value proposition are defined. \- Stakeholders are identified. \- Business objectives are documented. \- KPIs and measurement approaches are established. \- Customer onboarding journey is modelled. \- AI opportunities are assessed. \- Initial scope and boundaries are documented. \- Assumptions, constraints, risks and dependencies are registered. \- Structured artifacts are created. \- Validation checks are completed or limitations reported. \- Outstanding decisions are clearly identified. \- Readiness for Task 2 is assessed.   A successful execution does not mean that the business case has received formal approval.   \---   \#\# 10\. FINAL EXECUTION REPORT   At completion, provide a concise report in the terminal covering:   1\. Project workspace verification. 2\. Artifacts created. 3\. Business analysis completed. 4\. YAML and diagram validation results. 5\. Traceability assessment. 6\. Outstanding assumptions and decisions. 7\. Issues and limitations. 8\. Task 1 acceptance criteria status. 9\. Readiness recommendation for Task 2\.   Provide the actual file paths of all deliverables.   \---   \#\# 11\. EXECUTION BOUNDARIES   IMPORTANT:   \- Execute Task 1 only. \- Do not start Task 2\. \- Do not create application source code. \- Do not build frontend or backend components. \- Do not implement APIs or database schemas. \- Do not implement AI agents or model gateways. \- Do not prematurely design detailed technical architecture. \- Do not modify the previous project. \- Do not silently invent missing business information.   If a critical decision cannot be made safely, document it as an open decision rather than guessing.   Complete the task, present the artifacts and validation evidence, and STOP.   Wait for explicit human approval before proceeding to Task 2\. |
| :---- |

# **PART F — Claude Code execution report and review**

## **39\. Claude Code Task 1 execution report (as supplied)**

| Task 01 execution report   Task 01 is done and ready for your review. All 13 deliverables exist, all 87 automated checks pass, and every artifact is still DRAFT: nobody has reviewed or approved anything.   1\. Workspace verification   \- Location: C:\\Users\\LBALASURIYA\\Documents\\2026\\ai-native-customer-onboarding-banking. It was empty before I started. \- Git: the folder is not in any repository, and I did not create one. \- Isolation: it is not nested inside another project, and nothing outside it was read or changed. \- Project root: I used this folder directly, so there is no extra ai-native-customer-onboarding/ folder inside it. \- Helper scripts: the validation and diagram-embedding scripts are in the session scratchpad, not the project, so no code entered the project.   2\. Files created (all paths relative to the project root)   README.md — Status model, ID conventions, traceability chain. docs/business/BIZ-001-business-context-and-problem-statement.md — Context, discovery across all 11 areas, problem statement, BP-001 to BP-008, vision, intent, value proposition. docs/business/BIZ-002-business-case-and-value-model.md — Problem-to-value chain, BEN-001 to BEN-008, value formulas (no money figures), options OPT-0 to OPT-3. docs/business/BIZ-003-stakeholder-register.yaml — 20 stakeholder roles with responsibilities and decision rights. docs/business/BIZ-004-business-objectives-and-kpi-catalogue.yaml — 8 objectives and 25 KPIs; no baselines or targets invented. docs/business/BIZ-005-assumptions-constraints-and-risks.yaml — 10 hypotheses, 14 assumptions, 9 constraints, 17 risks, 8 dependencies, 13 decisions, 16 questions. docs/business/BIZ-006-customer-onboarding-journey.md — 13 journey stages with both diagrams embedded. docs/business/BIZ-007-ai-opportunity-assessment.yaml — 13 activities classified, 9 AI opportunities, 5 AI uses rejected or deferred. docs/business/BIZ-008-scope-and-boundaries.yaml — 13 provisional capabilities, 13 in-scope and 13 out-of-scope items, 10 AI boundary rules. docs/diagrams/current-state-journey.mmd — Current journey, labelled PROVISIONAL / ILLUSTRATIVE. docs/diagrams/proposed-future-state-journey.mmd — Proposed journey. validation/task-01-validation-report.md — Validation evidence. validation/task-01-completion-record.md — Execution record and open items.   3\. Key analysis positions   \- AI never decides. AI may extract, summarise, triage and draft. It cannot approve, activate an account or clear a screening alert. \- Confidence scores only route work. A high model score sends work onward; it is never treated as proof the output is correct. \- Not every problem needs AI. BP-008 (fragmented hand-offs) is solved by workflow and rules alone. \- The business case measures what AI adds. It is the difference between OPT-2 (workflow plus governed AI) and OPT-1 (workflow and rules, no AI). Each AI opportunity has to earn its own governance cost.   4\. Validation results   \- Automated checks: 87 of 87 pass. They cover YAML parsing, ID consistency, two-way trace links, KPI fields, Mermaid structure, required Markdown sections, a scan for named regulations or legal claims, AI control coverage and visibility of open items. \- Validator self-test: I seeded five defects into a scratch copy of the project, and the validator caught all five. \- Defects found and fixed during the run:   \- a YAML syntax error in BIZ-004;   \- a stage link between AI-007 and JS-11 that was recorded in only one direction;   \- edge labels in the diagrams that Mermaid could misread;   \- oversight wording for AI-004 and AI-007 that did not say a human decides.   5\. Traceability   All rules required by the brief pass. Every problem links to an objective, every objective has a KPI, every capability supports an objective, every AI opportunity addresses a problem, and every risk has a mitigation and an owner.   6\. Outstanding items   Decisions that block business-case approval: \- DEC-001 jurisdiction; \- DEC-002 to DEC-004 segment, products and channels; \- DEC-007 AI risk classification; \- DEC-009 KPI baselines and targets; \- DEC-013 approval authority.   Questions that block approval: \- OQ-001 sponsor endorsement; \- OQ-002 regulatory obligations; \- OQ-003 bank data confirming the problems; \- OQ-005 governance structure; \- OQ-006 AI governance framework; \- OQ-008 onboarding volumes; \- OQ-012 financial parameters.   Assumptions: none of the 14 has been validated yet.   The full list, with who must confirm each item, is in §5 of the completion record.   7\. Issues and limitations   \- Diagrams not rendered: no Mermaid tool is installed, so they are checked for structure only and are not confirmed to render. If you approve, I can run npx \-p @mermaid-js/mermaid-cli mmdc to render them. \- Current-state journey is generic: the journey and root-cause hypotheses describe typical industry practice, not a real bank, and need walkthroughs with the bank. \- Risk ratings are provisional: they were made without bank data. \- Keyword scan limits: the scan for regulatory claims can't catch implied claims, so Compliance still needs to review.   8\. Acceptance criteria   All 14 criteria are met in draft form. Two carry caveats: \- KPI baselines and targets are deliberately not established. \- Validation is complete except for Mermaid rendering.   9\. Recommendation for Task 2   I recommend starting Task 2 only once you have done three things: 1\. Accept BIZ-001, BIZ-007 and BIZ-008 as the working baseline. 2\. Accept or replace the working assumptions for segment, products and channels (DEC-002 to DEC-004). 3\. Confirm the AI boundary rules AIB-001 to AIB-010 as binding.   Final business-case approval stays blocked until the items in section 6 are resolved.   I have stopped here and need your explicit approval before starting Task 2\.   ✻ Churned for 17m 28s · done 11:10 AM   ※ recap: Task 01 is done: all business documents, journey diagrams and validation records exist as unapproved drafts, and all 87 automated checks pass. Next, review the drafts and say whether I can start Task 2\. (disable recaps in /config) |
| :---- |

## **40\. Review assessment**

Recommendation: accept Task 1 as the working business foundation and authorise Claude Code to begin Task 2 under explicit conditions. This is not formal approval of the final banking business case.

| Area | Review assessment |
| :---- | :---- |
| Project isolation | Satisfactory based on the execution report. |
| Business problem and intent | Ready for use as a working baseline. |
| Stakeholder modelling | Good reported coverage. |
| Objectives and KPIs | Good structure; baselines and targets remain pending. |
| Customer journey | Suitable provisional starting point; requires a bank walkthrough. |
| AI opportunity assessment | Strong separation of AI assistance and accountable decisions. |
| AI governance boundaries | AIB-001 to AIB-010 recommended as binding design constraints. |
| Scope and boundaries | Ready for initial business architecture modelling. |
| Traceability | Strong reported results across problems, objectives, KPIs, capabilities, AI opportunities and risks. |
| Automated validation | 87/87 reported passing; not independently rerun in this review. |
| Mermaid rendering | Outstanding; not a blocker to starting Task 2\. |
| Formal business-case approval | Pending external decisions and confirmations. |

## **41\. Three important design decisions**

### **41.1 AI does not make the final banking decision**

AI may extract information, interpret documents, summarise evidence, triage cases and draft recommendations. It does not approve customers, clear screening alerts or activate accounts. Those actions remain in authorised business workflows with required human accountability.

### **41.2 Measure the incremental value of AI**

The reported business case compares OPT-2 (workflow plus governed AI) with OPT-1 (workflow and rules without AI). This tests whether an AI opportunity creates enough additional value to justify data, validation, monitoring and governance costs.

### **41.3 Not every problem needs AI**

Fragmented hand-offs (BP-008) are identified as a problem that can be addressed through workflow and deterministic rules alone. This avoids adding AI where a simpler business-process solution is sufficient.

## **42\. Outstanding decisions and questions**

| Category | Open items |
| :---- | :---- |
| Decisions | DEC-001 jurisdiction; DEC-002 to DEC-004 segment/products/channels; DEC-007 AI risk classification; DEC-009 KPI baselines and targets; DEC-013 approval authority. |
| Questions | OQ-001 sponsor endorsement; OQ-002 regulatory obligations; OQ-003 bank data confirming problems; OQ-005 governance structure; OQ-006 AI governance framework; OQ-008 onboarding volumes; OQ-012 financial parameters. |
| Assumptions | None of the 14 assumptions has been validated, according to the execution report. |

These items remain open. Task 2 may proceed with clearly labelled provisional assumptions, but it must not silently convert them into confirmed business requirements.

## **43\. Working-baseline acceptance versus formal approval**

Working-baseline acceptance means the Task 1 artifacts are sufficiently coherent to serve as inputs to the next modelling task. Formal business-case approval requires the authorised business sponsor and stakeholders to confirm the business need, scope, value, regulatory context, governance and financial parameters. The working baseline can be accepted while formal business-case approval remains pending.

## **44\. Recommended Task 1 review decisions**

| Item | Recommended decision |
| :---- | :---- |
| BIZ-001 | Accept as working baseline. |
| BIZ-007 | Accept as provisional AI opportunity assessment. |
| BIZ-008 | Accept as initial scope and boundaries baseline. |
| DEC-002 | Retain individual retail customers as a provisional segment assumption. |
| DEC-003 | Keep product selection open. |
| DEC-004 | Keep channel selection open. |
| AIB-001 to AIB-010 | Accept as binding design constraints for Task 2\. |
| Jurisdiction, regulatory obligations, KPI baselines and targets | Keep pending. |

## **45\. Mermaid rendering limitation**

The execution report says the diagrams were structurally checked but not rendered because Mermaid CLI was unavailable. Rendering and visual inspection are recommended before treating the diagrams as fully validated, but this is not a blocker to beginning Task 2\.

# **PART G — Task 2 hand-off** 

#  **Upcoming in  \- Task\_02\_Beginner\_Guide\_Complete\_with\_Files\_and\_Claude\_Report.**

## **46\. What Task 2 should accomplish**

Task 2 is Business Architecture and Capability Modelling. It translates the Task 1 business foundation into a structured view of what the bank needs to be able to do to deliver customer onboarding. It remains business architecture, not detailed software implementation.

### **46.1 What is a business capability?**

A business capability describes what an organisation must be able to do, regardless of which people, processes, data or technologies are eventually used to deliver it.

* Business capability example: Customer Identity Management.  
* Potential solution capability: Document Extraction.  
* Technical implementation example: calling an AI model to extract fields from an uploaded document.

These concepts must not be mixed. Task 2 focuses on business capabilities and their relationships. More detailed operational process and decision modelling belongs primarily in Task 3\.

### **46.2 Expected Task 2 outputs**

* Business capability map with Level 1, Level 2 and useful Level 3 capabilities.  
* Customer onboarding value stream, from initiation through activation.  
* Capability-to-business-objective and capability-to-problem mappings.  
* Stakeholder-to-capability mapping.  
* Capability ownership and accountability.  
* Capability relationships and dependencies.  
* Business architecture blueprint.  
* Traceability to Task 1 artifacts and identifiers.  
* Validation report and completion record.

## **47\. Exact Task 2 authorisation prompt**

| \# TASK 01 REVIEW DECISION AND AUTHORISATION   I have reviewed the Task 01 execution report.   I APPROVE TASK 01 AS THE WORKING BUSINESS FOUNDATION for the new independent AI-Native Customer Onboarding Application project.   This is not formal approval of the final banking business case. All outstanding external decisions, assumptions and regulatory confirmations must remain visible and retain their current statuses.   \#\# Approved working baseline   Accept the following artifacts as the initial inputs to Task 02:   \- BIZ-001: Business Context and Problem Statement. \- BIZ-007: AI Opportunity Assessment. \- BIZ-008: Scope and Boundaries.   Accept AIB-001 to AIB-010 as binding design constraints for subsequent business and solution modelling.   \#\# Provisional assumptions   Retain the following as provisional assumptions, not confirmed business decisions:   \- Individual retail banking customers as the initial segment. \- Banking products remain subject to selection. \- Customer onboarding channels remain subject to selection. \- Current-state onboarding processes remain illustrative until validated with a real banking institution.   Do not silently convert these assumptions into approved business requirements.   \#\# Outstanding decisions   Keep the following unresolved:   \- Banking jurisdiction and regulatory obligations. \- Customer segment, products and channels. \- AI risk classification and governance framework. \- KPI baselines and performance targets. \- Business sponsor and approval authority. \- Actual banking operational data and financial parameters.   Do not invent answers to these questions.   \#\# AUTHORISATION   I explicitly authorise Claude Code to begin:   TASK 02 — BUSINESS ARCHITECTURE AND CAPABILITY MODELLING.   Use the approved Task 01 working baseline as the source of truth.   Task 02 must:   1\. Identify and structure the business capabilities required for the customer onboarding domain. 2\. Develop a hierarchical business capability map. 3\. Define the customer onboarding value stream. 4\. Map capabilities to Task 01 business objectives and problems. 5\. Identify stakeholders, capability ownership and accountability. 6\. Identify capability relationships and dependencies. 7\. Develop the business architecture blueprint. 8\. Maintain traceability to Task 01 artifacts. 9\. Validate all structured outputs and report unresolved assumptions. 10\. Create a Task 02 completion and validation report.   Maintain the distinction between business capabilities, operational processes, solution capabilities and technical implementation components.   Do not start Task 03\.   Do not modify the previous independent AI-native application project.   Do not change approved Task 01 artifacts without recording a proposed change and its rationale.   At the end, stop and present the Task 02 deliverables for human review and approval.   \*\*Final instruction: Proceed with Task 02 under these conditions.\*\* |
| :---- |

## **48\. Recommended task-by-task governance cycle**

* Understand the business or technical problem.  
* Design the required models and specifications.  
* Create the task artifacts in the independent project workspace.  
* Validate the artifacts and traceability.  
* Review assumptions, risks and unresolved decisions.  
* Record evidence and the completion report.  
* Obtain human approval before proceeding to the next task.

**Project Instructions → Task Specification → Agent Execution → Validation → Human Approval → Next Task**

## **49\. Consolidated Task 1 status**

| Item | Status |
| :---- | :---- |
| Task 1 execution | Reported complete. |
| Task 1 deliverables | 13 reported created. |
| Automated checks | 87/87 reported passing. |
| Artifact approval status | DRAFT in Claude's report. |
| Working business foundation | Recommended for acceptance. |
| Formal business-case approval | Pending external decisions and confirmations. |
| Task 2 | Authorised by the review decision, subject to conditions. |
| Task 3 | Not authorised / not started. |

## **50\. Closing principle**

**We are not starting by building an AI banking application. We are starting by understanding and modelling the banking business problem, then engineering the application that solves it.**