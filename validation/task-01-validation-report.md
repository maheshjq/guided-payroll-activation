# Task 01 Validation Report

Task: Task 01, Business Problem, Intent and Value Model
Status: DRAFT
Executed: 2026-11-13

## 1. Summary

45 automated checks were run against the Task 01 artifacts. All 45 pass on the final run. The validator was self-tested against six deliberately seeded defects and caught all six. Two limitations apply: YAML was validated with a strict-subset parser rather than a reference YAML library, and the Mermaid diagrams were checked for structure but not rendered. Neither tool could be installed without approval.

A passing validation shows internal consistency and traceability. It is not a business approval and does not confirm that any business content is correct.

## 2. Tools

| Purpose | Tool | Availability |
| :-- | :-- | :-- |
| Script runtime | Node.js v26.13.0 | Available |
| YAML parsing | Python with PyYAML; Node js-yaml or yaml | Not available. Python is only a Windows Store stub; no Node YAML library is installed. |
| YAML parsing, substitute | Strict-subset parser written for this task | Used. Rejects tabs, odd indentation, duplicate keys, unquoted `: ` or ` #`, scalars starting with YAML indicator characters, and nested flow collections. |
| Mermaid rendering | mermaid-cli (`mmdc`) | Not available. Not installed, by instruction. |
| Mermaid structure, substitute | Structural checks in the validator | Used |
| Baseline integrity | git | Available |

The validator is `validate.cjs` in the session scratchpad, outside the repository, so no code entered the project.

## 3. Results

| ID | Check | Result | Evidence |
| :-- | :-- | :-- | :-- |
| C01 | All required Task 01 artifacts exist | PASS | 11 artifact files present |
| C02 | YAML strict-subset parse, five files | PASS | BIZ-003, BIZ-004, BIZ-005, BIZ-007 and BIZ-008 parsed |
| C03 | Artifact metadata and DRAFT status, five YAML files | PASS | Each `artifact_id` matches its file name; each status is DRAFT |
| C04 | Every ID defined exactly once | PASS | 220 IDs, each defined once |
| C05 | Each ID prefix defined only in its canonical artifact | PASS | All 20 prefixes in their canonical artifacts |
| C06 | IDs sequential and consistently zero-padded | PASS | No gaps in any prefix |
| C07 | Expected counts | PASS | BN 5, CAP 7, JS 13, KPI 22, BO 8, AIB 12 |
| C08 | Every referenced ID resolves | PASS | All internal IDs resolve; 22 external EPIC and PA IDs verified against the baseline files |
| C09 | Two-way: objective and business problem | PASS | 12 links consistent |
| C10 | Two-way: objective and bottleneck | PASS | 16 links consistent |
| C11 | Two-way: objective and KPI | PASS | 24 links consistent |
| C12 | Two-way: objective and capability | PASS | 17 links consistent |
| C13 | Two-way: bottleneck and journey stage | PASS | 15 links consistent |
| C14 | Two-way: AI opportunity and journey stage | PASS | 9 links consistent |
| C15 | Every bottleneck and business problem links to an objective | PASS | All 10 linked |
| C16 | Every objective has a KPI | PASS | 8 of 8 |
| C17 | Every capability supports an objective and names its source | PASS | 7 of 7 |
| C18 | Every AI opportunity addresses a business problem | PASS | 9 of 9, including rejected uses |
| C19 | Every risk has a mitigation and an owner role in the stakeholder register | PASS | 13 of 13 |
| C20 | Every assumption has a validation status, method and confirming role | PASS | 14 of 14, all UNVALIDATED |
| C21 | Every scope decision names its source | PASS | 11 in scope, 18 out of scope |
| C22 | Every journey stage maps to one epic | PASS | 13 of 13 |
| C23 | KPI catalogue complete; baselines and targets PENDING; only KPI-001 to KPI-003 carry a stated target | PASS | 22 KPIs, 11 required fields each |
| C24 | AI controls and human oversight; all eight prompt principles covered | PASS | 9 AI entries, 12 rules, 8 principles covered |
| C25 | No named regulation, statute or jurisdiction | PASS | 11 files scanned |
| C26 | No unqualified compliance, certification, immutability or guarantee claim | PASS | Every occurrence negated or listed as out of scope |
| C27 | No monetary figure, and no percentage other than 65, 75 and 99.8 | PASS | None found |
| C28 | Mermaid structure, current state | PASS | 15 nodes; 30 edge endpoints, all defined |
| C28 | Mermaid structure, future state | PASS | 20 nodes; 34 edge endpoints, all defined |
| C29 | Embedded diagrams identical to the `.mmd` files | PASS | 2 of 2 identical |
| C30 | Required Markdown sections and DRAFT status, four files | PASS | BIZ-001, BIZ-002, BIZ-006 and the folder README |
| C31 | Every decision and question OPEN and listed in the completion record | PASS | 23 decisions and 12 questions |
| C32 | No baseline, root README or CLAUDE.md file modified | PASS | `git status` clean for 14 protected files |
| C33 | Only new untracked files, and only under the three Task 01 folders | PASS | 12 new files at the time of the run, none elsewhere |

Total: 45 checks, 45 pass, 0 fail. Rows C02, C03, C28 and C30 each cover several files and are counted once per file in the total.

C33 ran before this report existed, so it counted 12 files; this report is the 13th. It sits in `validation/`, which C33 permits.

## 4. Defects found and fixed during the run

The first run returned 42 passes and 3 failures.

| Check | Defect | Fix |
| :-- | :-- | :-- |
| C04 | The program targets table in BIZ-002 began its rows with KPI-001 to KPI-003, which redefined IDs owned by BIZ-004 | Moved the KPI ID to the second column and pointed to BIZ-004 for the definitions |
| C24 | The oversight text for AI-004 said "would require explicit human approval" without stating that a person reviews and decides | Reworded to state that a person must review and explicitly approve, and decides whether any change is made |
| C31 | The completion record did not yet exist | Expected on the first run; resolved when the record was written |

One factual error was also found by manual review: the completion record first said that several epics cite the blueprint as the source of the program targets. A check of the epic files showed that only epic-01 does. PCR-002 was corrected.

## 5. Validator self-test

Six defects were seeded into a scratch copy of the artifacts, and the validator was run against that copy with the git checks skipped.

| Seeded defect | Caught by |
| :-- | :-- |
| Unquoted colon in a YAML value in BIZ-003 | C02 |
| One-way link: KPI-002 removed from BO-002 only | C11 |
| Reference to an undefined decision, DEC-099, in BIZ-001 | C08 |
| A named regulation inserted into BIZ-006 | C25 |
| An unbalanced bracket in the current-state diagram | C28, and C29 through the embedded-copy mismatch |
| An invented 50 percent target on KPI-004 | C23 and C27 |

All six were caught. The broken stakeholder file also produced expected knock-on failures in C08 and C19.

## 6. Checks the validator cannot perform

- Whether the business content is correct. That requires review by the product team, payroll-domain experts and compliance.
- Whether a statement implies a statutory obligation without naming one. Keyword scanning cannot detect this.
- Whether the diagrams render. A Mermaid renderer is needed.
- Full YAML 1.2 conformance. A reference parser is needed.

## 7. Recommended follow-up checks, after approval

1. Run `npx js-yaml` on each YAML file to confirm conformance with a reference parser.
2. Run `npx -p @mermaid-js/mermaid-cli mmdc` on both diagrams and inspect the rendered output.
3. Have the compliance owner review BIZ-001, BIZ-005 and BIZ-007 for implied statutory claims.
