# Proposed Technology Stack and Solution Architecture (Google Cloud)

This is a proposed baseline for the solution architecture diagram. It is an AI-generated draft that needs validation by the engineering and security teams.

## Executive summary

The proposed stack is event-driven and serverless-first on Google Cloud. Cloud Run and Pub/Sub handle asynchronous batch processing, Cloud SQL for PostgreSQL holds transactional payroll data, BigQuery handles audit and analytics, and Vertex AI with Gemini provides assistive schema mapping. Security rests on VPC Service Controls, customer-managed encryption keys, tenant isolation, and Sensitive Data Protection, because the data includes tax IDs and bank details.

## Solution architecture (layered view)

![Solution architecture diagram](./docs/solution-architecture.svg)

The same view as a Mermaid diagram, which stays editable as text:

```mermaid
flowchart TB
    USERS["Payroll administrators · Implementation specialists · Auditors"]

    subgraph EDGE["Edge and access"]
        direction LR
        WEB["Web app<br/>Angular or React, AG Grid, CDN"]
        IDP["Identity Platform<br/>SSO via SAML and OIDC"]
        LB["Cloud Armor + Load Balancer<br/>WAF, DDoS, rate limits"]
        GW["API Gateway or Apigee<br/>auth, quotas, routing"]
    end

    subgraph SVC["Cloud Run services, one per epic"]
        direction LR
        E1["Epic 1<br/>Prepare batch"]
        E2["Epic 2<br/>Map data"]
        E3["Epic 3<br/>Validate, simulate"]
        E4["Epic 4<br/>Activate<br/>(partial commit)"]
        E6["Epic 6<br/>Results and audit"]
        E5["Epic 5<br/>Remediate"]
        E1 --> E2 --> E3
        E3 -->|"eligible"| E4
        E4 -->|"outcomes"| E6
        E3 -->|"errors"| E5
        E5 -->|"corrected"| E3
        E5 -->|"outcomes"| E6
    end

    AI["AI assist: Gemini on Vertex AI<br/>vector search, Model Armor, masked inputs"]
    ENG["Payroll and statutory engines<br/>dry run and activation"]

    ORCH["Orchestration<br/>Eventarc, Cloud Workflows, Pub/Sub + dead-letter,<br/>Cloud Tasks, Dataflow"]

    subgraph DATA["Data"]
        direction LR
        GCS["Cloud Storage<br/>landing, quarantine, processed"]
        SQL["Cloud SQL or AlloyDB<br/>system of record"]
        FS["Firestore<br/>remediation queue, live status"]
        RED["Memorystore Redis<br/>reference lookups"]
        BQ["BigQuery + Looker<br/>audit trail, history, KPIs"]
    end

    SEC["Security and governance, applied to every layer<br/>IAM, Cloud KMS keys, VPC Service Controls, Sensitive Data Protection,<br/>Audit Logs, Security Command Center, Secret Manager"]
    OPS["Operations and delivery<br/>Terraform, Cloud Build, Cloud Deploy,<br/>Artifact Registry + Binary Authorization, Cloud Monitoring"]

    USERS --> EDGE
    EDGE -->|"REST calls, tenant scoped"| SVC
    AI -.->|"suggests only"| E2
    E3 <-.->|"dry run"| ENG
    E4 <-.->|"activate"| ENG
    ORCH ==>|"drives every stage"| SVC
    SVC <-->|"read and write"| DATA
    DATA --- SEC
    SEC --- OPS

    classDef epic fill:#E6F4F4,stroke:#0A6C6C,color:#13222D
    classDef err fill:#FBEBDF,stroke:#B2501A,color:#13222D
    classDef ai fill:#EEEAFA,stroke:#5E46B0,color:#13222D
    classDef ext fill:#FFFFFF,stroke:#566877,stroke-dasharray:3 3,color:#13222D
    class E1,E2,E3,E4,E6 epic
    class E5 err
    class AI ai
    class ENG ext
```

## Architecture overview (one view)

```mermaid
flowchart LR
    U["Users<br/>Admins, specialists, auditors"] --> E["Edge<br/>Identity Platform, Cloud Armor,<br/>Load Balancer, SPA on CDN"]
    E --> A["API layer<br/>API Gateway / Apigee"]

    subgraph CORE["Cloud Run services (Epics 1 to 6)"]
        direction LR
        B1["1 Batch"] --> B2["2 Mapping"] --> B3["3 Validate<br/>and simulate"]
        B3 -->|"eligible"| B4["4 Activate<br/>(partial commit)"]
        B3 -->|"errors"| B5["5 Remediate"]
        B5 -->|"corrected"| B3
        B4 --> B6["6 Results<br/>and audit"]
        B5 --> B6
    end

    A --> B1
    A --> B5
    A --> B6

    ORCH["Orchestration<br/>Workflows, Pub/Sub, Cloud Tasks,<br/>Dataflow"] -.-> CORE
    AI["AI<br/>Gemini on Vertex AI,<br/>vector search, Model Armor"] -.->|"suggests only"| B2
    ENG["Payroll and statutory engines"] <-->|"dry run and activation"| CORE

    CORE --> D["Data<br/>Cloud Storage, Cloud SQL / AlloyDB,<br/>Firestore, Redis, BigQuery, Looker"]

    SEC["Security: IAM, KMS keys, VPC Service Controls,<br/>Sensitive Data Protection, Audit Logs, Security Command Center"]
    OPS["Operations: Terraform, Cloud Build, Cloud Deploy,<br/>Artifact Registry, Cloud Monitoring"]
    D --- SEC
    D --- OPS
```

## Architecture diagram (detailed)

The diagram shows the layers of the solution and how the six epics flow through them.

```mermaid
flowchart TB
    subgraph USERS["Users"]
        U1["Payroll administrators"]
        U2["Implementation specialists"]
        U3["Auditors"]
    end

    subgraph EDGE["Edge and access"]
        IDP["Identity Platform<br/>SSO via SAML / OIDC"]
        LB["Global External Application Load Balancer<br/>+ Cloud Armor (WAF, DDoS, rate limiting)"]
        CDN["Cloud CDN + Cloud Storage<br/>Angular / React SPA"]
        APIGW["API Gateway or Apigee"]
    end

    subgraph APP["Application layer: Cloud Run services"]
        S1["Batch service<br/>Epic 1"]
        S2["Mapping service<br/>Epic 2"]
        S3["Validation and simulation service<br/>Epic 3"]
        S4["Activation service<br/>Epic 4"]
        S5["Remediation service<br/>Epic 5"]
        S6["Results and audit service<br/>Epic 6"]
    end

    subgraph ORCH["Orchestration and messaging"]
        WF["Cloud Workflows<br/>batch lifecycle"]
        PS["Pub/Sub<br/>+ dead-letter topics"]
        CT["Cloud Tasks<br/>retries"]
        DF["Dataflow (Apache Beam)<br/>large batch parsing"]
        EA["Eventarc<br/>file-arrival triggers"]
    end

    subgraph AI["AI layer"]
        MA["Model Armor<br/>prompt and response screening"]
        VX["Vertex AI: Gemini<br/>mapping suggestions, error explanations"]
        VS["Vector search<br/>approved mapping history"]
        EV["Vertex AI Model Evaluation<br/>golden dataset"]
        DLP["Sensitive Data Protection<br/>mask before model calls"]
    end

    subgraph DATA["Data layer"]
        GCS["Cloud Storage<br/>landing / quarantine / processed"]
        SQL["Cloud SQL for PostgreSQL or AlloyDB<br/>system of record, row-level security"]
        FS["Firestore<br/>remediation queue, live progress"]
        RED["Memorystore for Redis<br/>reference data cache"]
        BQ["BigQuery<br/>audit trail, history, metrics"]
        DPX["Dataplex<br/>catalog, lineage, quality"]
        LK["Looker<br/>dashboards"]
    end

    subgraph EXT["Payroll platform"]
        ENG["Payroll and statutory engines<br/>via Private Service Connect or Interconnect"]
    end

    subgraph SEC["Security and governance"]
        IAM["Cloud IAM + workload identity"]
        KMS["Cloud KMS / EKM<br/>customer-managed keys"]
        SM["Secret Manager"]
        VPCSC["VPC Service Controls"]
        SCC["Security Command Center"]
        AUD["Cloud Audit Logs<br/>to BigQuery, retention locks"]
    end

    subgraph OPS["Infrastructure and operations"]
        TF["Terraform"]
        CB["Cloud Build / GitHub Actions"]
        AR["Artifact Registry<br/>+ Binary Authorization"]
        CD["Cloud Deploy"]
        MON["Cloud Monitoring, Logging, Trace"]
    end

    U1 --> LB
    U2 --> LB
    U3 --> LB
    LB --> CDN
    LB --> APIGW
    IDP -.-> APIGW
    CDN -.-> IDP
    APIGW --> S1
    APIGW --> S5
    APIGW --> S6

    S1 -->|"upload"| GCS
    GCS --> EA --> WF
    WF --> DF
    WF --> PS
    PS --> S2
    PS --> S3
    PS --> S4
    CT -.-> S4

    S2 --> DLP --> MA --> VX
    VX --> VS
    VX -.-> EV

    S2 --> SQL
    S3 -->|"dry run"| ENG
    S3 -->|"eligible records"| S4
    S3 -->|"records with errors"| S5
    S4 -->|"partial activation"| ENG
    S5 -->|"corrected records"| S3
    S5 --> FS
    S4 --> SQL
    S3 --> RED

    S4 --> S6
    S5 --> S6
    S6 --> BQ
    BQ --> LK
    SQL --> BQ
    BQ --> DPX
    GCS --> DPX

    SEC -.->|"governs"| APP
    SEC -.->|"governs"| DATA
    SEC -.->|"governs"| AI
    OPS -.->|"builds, deploys, observes"| APP
```

## Frontend

- Angular or React with TypeScript, served from Cloud Storage behind Cloud CDN and the Global External Application Load Balancer. Angular suits teams that want a structured enterprise framework.
- Material UI components and a virtualized data grid such as AG Grid for cell-level error display and bulk edits across thousands of rows.
- Real-time batch progress and remediation queue updates through Firestore listeners or Server-Sent Events from Cloud Run.
- Identity Platform for sign-in, with SSO through SAML and OIDC for client identity providers.

## Backend and integration

- Cloud Run services in Java (Spring Boot), Go, or Node.js (NestJS), organized by domain: batch, mapping, validation, activation, remediation, and results and audit.
- API Gateway or Apigee as the front door. Apigee is the better choice if external partner APIs, quotas, and monetization are needed.
- Pub/Sub for events between stages, with dead-letter topics for failed records.
- Cloud Tasks for per-record or per-chunk retries, and Cloud Workflows for orchestrating the batch lifecycle.
- Dataflow (Apache Beam) for large batch parsing and chunked processing when volumes exceed what Cloud Run handles comfortably.
- Cloud Scheduler for timed jobs, and Eventarc for file-arrival triggers.
- Private connectivity to payroll and statutory engines through Private Service Connect or Cloud Interconnect where they are hosted outside Google Cloud.

## AI layer

- Vertex AI with Gemini for assistive column-to-field mapping, pay code matching, and plain-language error explanations with corrective suggestions.
- Vector search over approved historical mappings, using Vertex AI Vector Search, AlloyDB pgvector, or BigQuery vector search, to retrieve similar mappings as few-shot context.
- Structured JSON output, so suggestions are machine-checkable.
- Guardrails: AI only suggests and never approves or activates. Every suggestion carries a confidence score, a human accept or reject step, and a logged outcome. Deterministic rules remain the authority for validation.
- Model Armor and Vertex AI safety filters for prompt and response screening. Sensitive Data Protection masks tax IDs and bank details before any model call.
- Vertex AI Model Evaluation and a golden dataset to measure mapping accuracy over time.

## Data architecture

- Cloud SQL for PostgreSQL, or AlloyDB for higher throughput, as the system of record for batches, mappings, validation results, and remediation items. Row-level security provides tenant isolation.
- Cloud Storage for raw uploaded files, with separate buckets for landing, quarantine, and processed data, plus retention policies and object versioning.
- BigQuery for the audit trail, activation history, and success-metric reporting (cycle time, support touchpoints, first-time-right rate).
- Firestore for low-latency remediation queue state and live progress.
- Memorystore for Redis for caching reference data such as tax jurisdiction and pay code lookups.
- Dataplex for data catalog, lineage, and quality rules. Looker for dashboards.
- Cloud Spanner only if multi-region, globally consistent writes become a requirement.

## Infrastructure and operations

- Region choice driven by data residency requirements, with multi-zone high availability by default and a multi-region disaster recovery plan for Cloud SQL and Cloud Storage.
- Terraform for infrastructure as code, with a landing zone using a Google Cloud Organization, folders, and separate projects per environment (dev, test, staging, production).
- Cloud Build or GitHub Actions for CI, Artifact Registry for images, and Cloud Deploy for progressive delivery with Binary Authorization.
- GKE is not recommended initially. Move to it only if workloads need custom scheduling or sidecars that Cloud Run cannot support.
- Cloud Monitoring, Cloud Logging, Cloud Trace, and Error Reporting for observability, with SLOs on batch completion time and record throughput.
- Autoscaling per service, with concurrency limits and Pub/Sub flow control to protect downstream statutory engines.
- Cost controls: budgets and alerts, BigQuery slot reservations or on-demand caps, Cloud Run minimum instances at zero outside production, and Gemini model tiering (smaller model for routine mapping, larger model for ambiguous cases).

## Security posture

- Identity and access: Identity Platform for users, Cloud IAM with least privilege, workload identity for service-to-service calls, and no long-lived service account keys. Role-based access separates client administrators, implementation specialists, and auditors.
- Network: private Cloud Run ingress where possible, Cloud Armor at the edge, VPC Service Controls around data services, Private Google Access, and Cloud NAT for controlled egress.
- Data protection: encryption at rest with customer-managed keys in Cloud KMS (or Cloud EKM if clients require external key control), TLS everywhere, Sensitive Data Protection for discovery, masking, and tokenization of tax IDs and bank details, and Secret Manager for credentials.
- Tenant isolation: tenant ID enforced at the API, database (row-level security), and storage prefix levels, with per-tenant encryption keys for higher-sensitivity clients.
- Audit and compliance: Cloud Audit Logs (including data access logs) exported to BigQuery with retention locks, immutable activation history, Security Command Center Premium for posture management, and Assured Workloads if regulated regions apply. Target frameworks are SOC 2, ISO 27001, GDPR, and applicable payroll and tax regulations.
- Supply chain and application security: Binary Authorization, Artifact Analysis for vulnerability scanning, dependency and static analysis in CI, and regular penetration testing.
- AI security: prompt-injection screening on uploaded file content, data masking before model calls, no training on customer data, and logged model inputs and outputs under the same retention rules as other personal data.

## Epic to component mapping

- Epic 1, Prepare a batch: Batch service, Cloud Storage, Eventarc, Cloud SQL.
- Epic 2, Map data and resolve context: Mapping service, Vertex AI (Gemini), vector search, Sensitive Data Protection, Cloud SQL.
- Epic 3, Validate and simulate: Validation and simulation service, Memorystore, payroll and statutory engines (dry run).
- Epic 4, Process asynchronously and partially activate: Activation service, Cloud Workflows, Pub/Sub, Cloud Tasks, Dataflow.
- Epic 5, Remediate exceptions: Remediation service, Firestore, AG Grid frontend.
- Epic 6, Review results and history: Results and audit service, BigQuery, Looker, Cloud Audit Logs.

## Open decisions, in priority order

1. Confirm data residency, compliance frameworks, and whether the payroll and statutory engines are on Google Cloud, since these drive region, network, and database choices.
2. Decide the compute model for processing (Cloud Run with Pub/Sub, or Dataflow) based on expected batch size and peak concurrency.
3. Define the AI guardrail and evaluation approach for mapping before building the Epic 2 stories.
4. Choose between Cloud SQL and AlloyDB, and between API Gateway and Apigee.
