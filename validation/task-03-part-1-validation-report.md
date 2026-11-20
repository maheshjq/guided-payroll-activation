# Task 03 Part 1 Validation Report

Status: DRAFT. Validation shows structure and references only. It does not show that the processes match how any client actually works.
Executed: 2026-11-20, by Claude Code, from `docs/prompts/task-03-operational-blueprint-prompt.md`, Run 1

## 1. Summary

All 27 internal checks pass. The validator was tested against three seeded defects and caught all three. `js-yaml` parsed every YAML file in the repository, and the Mermaid renderer drew all six diagrams. These are the first standard-parser and rendering checks for the Task 01 and Task 02 files as well.

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
| 23 | No technology, product or vendor names | PASS |  |
| 24 | No named regulations or legal claims | PASS |  |
| 25 | No invented numeric thresholds (only the problem-statement targets) | PASS |  |
| 26 | No Task 01, Task 02 or baseline file changed (git status) | PASS |  |
| 27 | Overview diagram names all six processes | PASS | ['PRC-01', 'PRC-02', 'PRC-03', 'PRC-04', 'PRC-05', 'PRC-06'] |

## 3. Validator self-test

Three defects were seeded into copies of OPS-002 and OPS-003, then the files were restored:

| Seeded defect | Detected by |
| :-- | :-- |
| An exception pointing to a non-existent process (PRC-09) | Exception refers to a real process and step; exception linked from a step |
| An invented role (STK-099) | Identifier exists; role is from BIZ-003 |
| A technology term in a step (database) | No technology, product or vendor names |

The first self-test run crashed on the invalid process reference instead of reporting it. The validator was fixed to report the failure, and the self-test was rerun successfully.

## 4. Package tools authorised in Part A

| Tool | Scope | Result |
| :-- | :-- | :-- |
| `npx js-yaml@4.1.0` | OPS-002, OPS-003, OPS-009, and read-only every YAML file in docs/business and docs/architecture | All parsed without error |
| `npx @mermaid-js/mermaid-cli@11.4.2` with the pre-installed Chromium | All six `.mmd` files in docs/diagrams, read-only for Tasks 01 and 02 | All rendered without error; rendered images kept in the session scratchpad |

No package was added to the repository.

## 5. Limitations

- The checks confirm well-formed files, existing identifiers, coverage and the absence of flagged words. They cannot confirm that a step, role or exception is correct for a real client.
- The technology, regulation and number scans are keyword-based and cannot detect an implied claim.
- The generator and validator scripts are in the session scratchpad, not the repository, so these checks cannot be rerun from the repository alone.
- Ownership and authority shown in the processes come from ARC-004, which is itself an assumption.
