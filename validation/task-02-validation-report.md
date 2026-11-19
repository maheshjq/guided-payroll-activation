# Task 02 Validation Report

Task: Task 02, Business Architecture and Capability Modelling
Status: DRAFT
Executed: 2026-11-19

## 1. Summary

46 automated checks were run against the Task 02 artifacts and their links to Task 01. All 46 pass on the final run. The validator was self-tested against nine seeded defects and caught all nine. A regression run of the Task 01 validator still passes.

The two validation tools authorised in Part A of the prompt, `npx js-yaml` and the Mermaid CLI, did not run, because the session's permission system blocked npx. YAML was therefore checked with the strict-subset parser from Task 01, and Mermaid diagrams for structure only.

A passing validation shows internal consistency and traceability. It is not a business approval.

## 2. Tools

| Purpose | Tool | Result |
| :-- | :-- | :-- |
| Reference YAML parse | `npx js-yaml`, authorised in Part A | NOT RUN. The first npx call was denied by the Claude Code permission system. No workaround was attempted. |
| Mermaid rendering | `npx -p @mermaid-js/mermaid-cli mmdc`, authorised in Part A | NOT RUN, for the same reason |
| YAML, substitute | Strict-subset parser from Task 01 | Used; rejects tabs, odd indentation, duplicate keys, unquoted colons and ambiguous scalars |
| Mermaid, substitute | Structural checks: declaration, balanced brackets and quotes, subgraphs, every edge endpoint defined | Used |
| Consistency | Node.js v26.13.0 running the Task 02 validator | Used |
| Baseline integrity | git | Used |

The generator and the validator are in the session scratchpad, outside the repository.

## 3. Results

| ID | Check | Result | Evidence |
| :-- | :-- | :-- | :-- |
| T01 | Required Task 02 artifacts exist | PASS | 10 files |
| T02 | YAML strict-subset parse, five files | PASS | ARC-001, ARC-003, ARC-004, ARC-005, ARC-007 |
| T03 | Metadata, DRAFT status and TASK-02, five files | PASS | All five |
| T04 | Single definition across Task 01 and Task 02 | PASS | 301 IDs; the only exception is CAP-001 to CAP-007 in BIZ-008 and ARC-001, recorded in PCR-007 |
| T05 | New prefixes in their canonical artifact, sequential and padded | PASS | CAP 38, CD 21, PCR 13, VS 6, VSB 1, BR 9 |
| T06 | Every referenced ID resolves | PASS | 10 files scanned; epics and stories checked against the baseline |
| T07 | Hierarchy consistent | PASS | Level 1: 9, Level 2: 25, Level 3: 4 |
| T08 | Every capability fully described and sourced | PASS | 38 of 38 |
| T09 | CAP-001 to CAP-007 unchanged from BIZ-008 | PASS | 7 of 7 |
| T10 | Their objective links match BIZ-004 and BIZ-008 in both directions | PASS | 7 of 7 |
| T11 | Every capability supports an objective or a recorded constraint | PASS | Constraint-only: CAP-009, CAP-033, CAP-034, all in PCR-009 |
| T12 | Every objective, bottleneck, KPI, epic and story is supported | PASS | 8, 5, 22, 6 and 16 covered |
| T13 | Two-way: capability trace and coverage sections | PASS | 297 links |
| T14 | Child objectives within parent; problems match BIZ-004 | PASS | 38 of 38 |
| T15 | Stories and journey stages belong to the capability's epics | PASS | All 16 stories located in the backlog |
| T16 | Capabilities without a story are recorded as proposed changes | PASS | CAP-012, CAP-030, CAP-031 |
| T17 | Two-way: capability and value stream stage | PASS | 39 links; 6 stages and 1 boundary |
| T18 | Each journey stage in exactly one value stream stage or boundary | PASS | 13 of 13 |
| T19 | Ownership complete and valid | PASS | 38 assignments, all ASSUMPTION; 9 rely on inferred roles |
| T20 | Task 01 stakeholder links preserved | PASS | All preserved |
| T21 | Dependencies valid and acyclic except the feedback loop | PASS | 21 dependencies, 1 feedback loop, 5 shared capabilities |
| T22 | AI entries consistent with BIZ-007 | PASS | All 9 placed, each carrying its boundary rules |
| T23 | AI mentioned only with an AI boundary rule | PASS | All Markdown sections |
| T24 | Technology-neutral | PASS | No product, platform or infrastructure name |
| T25 | No named regulation or jurisdiction | PASS | None |
| T26 | No unqualified compliance, immutability or guarantee claim | PASS | None |
| T27 | No monetary figure; no percentage beyond the three targets | PASS | None |
| T28 | Mermaid structure, three diagrams | PASS | Capability map 38 nodes; value stream 8 nodes; dependencies 9 nodes |
| T29 | Embedded diagrams identical to the .mmd files | PASS | 3 of 3 |
| T30 | Counts stated in ARC-006 match the data | PASS | Capabilities, levels, dependencies, shared capabilities, and the CD, PCR and BR ranges |
| T31 | Required Markdown sections and DRAFT status | PASS | ARC-002 and ARC-006 |
| T32 | Proposed changes carried forward and complete | PASS | 13; PCR-001 recorded as applied outside Task 02 |
| T33 | Every Task 01 decision and question is in the completion record | PASS | 35 items |
| T34 | No tracked file modified | PASS | git status clean for every tracked file |
| T35 | New files only in the Task 02 locations | PASS | 11 at the time of the run; this report is the 12th |

Total: 46 checks, 46 pass, 0 fail. T02, T03, T28 and T31 each run once per file.

Task 01 regression: the Task 01 validator was re-run against the same repository with its git checks skipped, because those checks assume that only Task 01 folders exist; T34 covers git for both tasks. Result: 44 of 44 pass.

## 4. Defects found and fixed during the run

The first run returned 43 passes and 3 failures. All three were investigated.

| Check | Finding | Fix |
| :-- | :-- | :-- |
| T04 | Validator defect: the known-duplicate exception compared definition locations in a fixed order and missed all seven CAP duplicates | Compare sorted locations |
| T04 | Validator defect: tables in ARC-002 and ARC-006 that list existing IDs in their first column, such as ownership by STK and decision points by DEC, were treated as new definitions | In ARC Markdown, only the prefixes each document owns count as definitions: VS and VSB in ARC-002, BR in ARC-006 |
| T24 | Validator defect: the case-insensitive technology scan matched "rest on constraint" as REST | Product and acronym names are matched case-sensitively; generic terms such as database stay case-insensitive |
| T33 | The completion record did not yet exist | Expected on the first run |

None of the first-run failures was an artifact defect. One factual error was found by checking the record against the validator: the completion record first said that eleven ownership assignments rely on inferred roles. The validator counts nine, and the record was corrected.

## 5. Validator self-test

Defects were seeded into scratch copies of the repository, and the validator was run against them with the git checks skipped.

| Seeded defect | Caught by |
| :-- | :-- |
| Unquoted colon in an ARC-004 value | T02, with knock-on failures in T03 and T19 |
| Capability removed from coverage sections in ARC-003 | T13. The seeding removed more links than intended, and every removed link was reported. |
| Unknown role STK-099 as an owner | T06 |
| A platform name inserted into ARC-006 | T24 |
| Malformed dependency endpoint | T21, as an unknown capability |
| A required boundary rule removed from a capability with an AI opportunity | T22 |
| A Level 3 capability moved to the wrong parent | T07 and T14 |
| A capability count in ARC-006 changed from 38 to 37 | T30 |
| A clean dependency cycle, CAP-002 to CAP-004 to CAP-003 to CAP-002, seeded separately | T21, as a cycle outside a feedback loop |

All nine were caught. The cycle was seeded separately because the first attempt produced a malformed endpoint rather than a cycle. That first attempt is the fifth row of the table.

## 6. Checks the validator cannot perform

- Whether the capabilities, rules and ownership are right for the business. That requires review by the product team and the payroll or compliance owner.
- Whether a statement implies a technology choice, or a statutory obligation, without naming one.
- Whether the diagrams render, and full YAML 1.2 conformance. Both need the tools that were blocked.

## 7. Recommended follow-up

1. Allow `npx` in the Claude Code permission settings, then run `npx js-yaml` on every Task 01 and Task 02 YAML file and `npx -p @mermaid-js/mermaid-cli mmdc` on all five diagrams, writing the rendered images to the session scratchpad.
2. Have the payroll or compliance owner review BR-001 to BR-009 and the ownership of CAP-020, CAP-023, CAP-031 and CAP-032.
