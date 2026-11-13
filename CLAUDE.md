# CLAUDE.md

Guidance for working in this repository.

## What this repository is

Product discovery documentation for improving bulk guided activation of employee profiles in a payroll management system. It contains documents and diagrams only, with no application code, build, or tests. Most content is an AI-generated draft that a human team still needs to review.

Start with `README.md`, which lists every document in reading order.

## Source of truth

- `Problem statement.md` is the verified source for the problem, bottlenecks, impact, and the three target metrics. Do not change it without being asked.
- `Business Model Canvas to Business Architecture Blueprint.md` frames the value, capabilities, and boundaries.
- `product-backlog.md` and `epic-01` to `epic-06` hold the epics and user stories. The epic files expand the backlog and must stay consistent with it.
- `requirements-document-map.md` shows how the documents and epics relate.
- `tech-stack.md` holds the proposed Google Cloud stack, security posture, and Mermaid diagrams.
- `docs/solution-architecture.svg` is the detailed architecture diagram, linked from `tech-stack.md` and `README.md`.
- `presentation-walkthrough.md` is the speaker script and story for presenting the solution.

## Project rules to keep consistent

- There are six epics, in this order: prepare batch, map data and resolve context, validate and simulate, process asynchronously and partially activate, remediate exceptions, review results and history.
- Priorities are P0 (foundational for a usable first release), P1 (important follow-on), and P2 (optional discovery). They are recommendations, not commitments.
- Out of scope: migration of historical payroll data, such as prior pay runs and year-to-date balances.
- Target metrics are 65% faster activation, 75% fewer support touchpoints per 1,000 activations, and a 99.8% first-time-right rate. Baselines are not yet agreed, so call them targets.
- AI only suggests, mainly for mappings in Epic 2. People approve, and deterministic rules decide validity. Never describe AI as approving or activating records.
- Validation errors must isolate to the failing record. A bad record never blocks the whole batch, and corrected records are revalidated on their own.
- Selected stack: Google Cloud, React with TypeScript and Axios, Python FastAPI on Cloud Run, Pub/Sub, Cloud SQL or AlloyDB, BigQuery, and Vertex AI with Gemini. Security uses VPC Service Controls, customer-managed keys, and Sensitive Data Protection.

## Writing style

- Professional, concise, active voice. No emojis or slang.
- Plain prose with simple headings. Avoid heavy markdown and avoid bold or italics unless asked.
- For analysis, open with a one or two sentence summary. Order recommendations by priority, highest first.
- Do not invent proprietary data, client names, or figures. Mark placeholders and illustrative examples clearly.

## Diagrams

- Mermaid diagrams live in `tech-stack.md` and `requirements-document-map.md`. Keep them valid and keep them consistent with the SVG.
- `docs/solution-architecture.svg` is a standalone, generated file with no external references. If you change it, keep it valid XML and check it by rendering it in a browser before committing.
- When the architecture changes, update the SVG, the Mermaid diagrams, and the stack sections of `tech-stack.md` together.

## Git

- Work on the branch you were assigned and push to it. Do not open a pull request unless asked.
- Write clear, descriptive commit messages.
