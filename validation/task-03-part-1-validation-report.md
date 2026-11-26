# Task 03 Part 1 Validation Report

Version: 0.2
Status: DRAFT. Validation shows structure and references only. It does not show that the processes match how any client actually works.
Executed: 2026-11-26, by Claude Code, from `docs/prompts/task-03-operational-blueprint-prompt.md` (revised), replacing the version 0.1 run of 2026-11-20

## 1. Summary

All 39 internal checks pass, including 13 new checks for the revised prompt: capability names, one step per capability, the capability operations view, business domains, capability links on exceptions, and the dispute and fraud-indicator categories. The validator caught every seeded defect. `js-yaml` parsed all three operations files, and the process diagram rendered.

## 2. Internal checks

| # | Check | Result | Detail |
| :-- | :-- | :-- | :-- |
| 1 | YAML parses (PyYAML): docs/operations/OPS-002-operational-process-model.yaml | PASS |  |
| 2 | YAML parses (PyYAML): docs/operations/OPS-003-exception-and-human-review-pathways.yaml | PASS |  |
| 3 | YAML parses (PyYAML): docs/operations/OPS-009-task-03-register.yaml | PASS |  |
| 4 | Every earlier-artifact identifier referenced in OPS-002 and OPS-003 exists | PASS |  |
| 5 | Every process has all required fields populated | PASS |  |
| 6 | Processes cover VS-01 to VS-06 | PASS | ['VS-01', 'VS-02', 'VS-03', 'VS-04', 'VS-05', 'VS-06'] |
| 7 | Every ARC-001 capability is used by at least one process | PASS |  |
| 8 | Process objectives, KPIs and stages agree with ARC-003 for the listed capabilities | PASS |  |
| 9 | Every objective BO-001 to BO-008 is served by a process | PASS | ['BO-001', 'BO-002', 'BO-003', 'BO-004', 'BO-005', 'BO-006', 'BO-007', 'BO-008'] |
| 10 | Every KPI is linked to at least one process (reported, not required) | PASS | not linked:  |
| 11 | Every story PA-01 to PA-16 maps to a process | PASS |  |
| 12 | Every role is from BIZ-003 | PASS |  |
| 13 | Every step has a valid classification | PASS |  |
| 14 | Every AI-supported step names an accepted AI opportunity and AIB-002 | PASS |  |
| 15 | No reserved human decision is performed by the system | PASS |  |
| 16 | Every exception referenced by a step exists in OPS-003 | PASS |  |
| 17 | Every exception refers to a real process and step | PASS |  |
| 18 | Every exception is linked from a step of its process (EXC-11 is a process-level rule) | PASS |  |
| 19 | Every process has at least one exception pathway | PASS |  |
| 20 | Every exception has the required fields | PASS |  |
| 21 | Every unresolved authority names its open decision | PASS |  |
| 22 | Every fully unresolved decision presents options | PASS |  |
| 23 | Every capability name matches ARC-001 (steps, domains, exceptions, capability view) | PASS |  |
| 24 | Every process names a business domain (a Level 1 capability) | PASS |  |
| 25 | Every step names the capability it exercises | PASS |  |
| 26 | Every ARC-001 capability has a capability operations entry | PASS |  |
| 27 | Every Level 2 and Level 3 capability has at least one step of its own | PASS |  |
| 28 | Capability coverage notes agree with the steps | PASS |  |
| 29 | Every capability entry describes its operation and points to real steps | PASS |  |
| 30 | Every exception names its capability | PASS |  |
| 31 | Dispute and fraud-indicator exception categories are present | PASS | ['Conflicting information', 'Escalation and referral', 'Failed verification', 'Incomplete submission', 'Missing information', 'Process failure', 'Request requiring human judgement', 'Stakeholder dispute', 'Suspected fraud or risk indicator', 'Unavailable information source'] |
| 32 | Every also_applies_to reference is a real step that links back | PASS |  |
| 33 | Every decision point sits on a real step | PASS |  |
| 34 | Every human intervention point is a real step | PASS |  |
| 35 | No technology, product or vendor names | PASS |  |
| 36 | No named regulations or legal claims | PASS |  |
| 37 | No invented numeric thresholds (only the problem-statement targets) | PASS |  |
| 38 | No Task 01, Task 02 or baseline file changed (git status) | PASS |  |
| 39 | Overview diagram names all six processes | PASS | ['PRC-01', 'PRC-02', 'PRC-03', 'PRC-04', 'PRC-05', 'PRC-06'] |

## 3. Validator self-test

Defects were seeded into copies of the files, and the files were then restored.

| Run | Seeded defect | Detected by |
| :-- | :-- | :-- |
| 0.1 | An exception pointing to a non-existent process (PRC-09) | Exception refers to a real process and step |
| 0.1 | An invented role (STK-099) | Role is from BIZ-003; identifier exists |
| 0.1 | A technology term in a step (database) | No technology, product or vendor names |
| 0.2 | A wrong capability name on a step | Capability name matches ARC-001 |
| 0.2 | The tax validation capability merged into a shared step | Every Level 2 and Level 3 capability has a step of its own |
| 0.2 | An exception with no capability link | Every exception names its capability |

## 4. Package tools

| Tool | Scope | Result |
| :-- | :-- | :-- |
| `npx js-yaml@4.1.0` | OPS-002, OPS-003, OPS-009 version 0.2 | All parsed without error |
| `npx @mermaid-js/mermaid-cli@11.4.2` | `docs/diagrams/ops-002-process-overview.mmd` | Rendered without error |

No package was added to the repository.

## 5. Limitations

- The checks confirm well-formed files, existing identifiers, coverage and the absence of flagged words. They cannot confirm that a step, role or capability description is correct for a real client.
- The capability descriptions were written from the Task 01 and Task 02 artifacts and the backlog; a check confirms each is present and long enough, not that it is accurate.
- The technology, regulation and number scans are keyword-based.
- The generator and validator scripts are in the session scratchpad, not the repository.
