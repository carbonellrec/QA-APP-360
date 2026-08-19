# QA-APP-360 · Requirements Consistency Verification

Repository containing the cross-consistency verification reports between Functional Requirements (RF), Business Rules (RN), Use Cases (CU), and Acceptance Criteria (CA) for the APP-360 project.

The objective is to ensure that the requirements documentation is fully aligned before customer delivery and the start of testing, identifying conflicts between documents, traceability gaps, and points requiring business decisions.

## Scope Covered

| Module | Requirements | Use Cases |
| :--- | :--- | :--- |
| Agency Management | RF-044 | CU-030 |
| Agency Registration | RF-045 | CU-031 |
| Agent Management | RF-046 | CU-032 |
| Commercial Ops – Agency & Agent | RF-047 | CU-033 |
| Commissioning & Payout | RF-048 | CU-034 |
| Refund Queue (Admin) | RF-049 | CU-035 |
| Institutional CMS | RF-050 | CU-036 |
| Home CMS & Curation | RF-051 | CU-037 |
| Initial Screen per Profile | RF-056 | CU-039 |
| Business Partners | RF-057 | CU-040 |

## Methodology

Each report cross-references the content of RF, RN, CU, and CA related to the same module and classifies each finding into four categories:

- ✓ **Consistent** — behavior is described coherently across documents.
- ■ **Attention Point** — behavior is not contradictory but is incomplete, ambiguous, or lacks coverage in CA.
- ✗ **Inconsistency** — documents describe the same behavior in conflicting ways.
- 💡 **Suggestion** — clarity or test coverage improvement, with no immediate functional impact.

Findings are prioritized as **P1 (Critical — fix before delivery)**, **P2 (Important — next review)**, and **P3 (Improvement — optional)**.

## Reports

| File | Modules | Date | ✓ | ■ | ✗ | 💡 |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| `relatorio-verificacao-rfs-cus.pdf` | RF-044–RF-057 / CU-030–CU-040 (Overview) | 06/22/2026 | 8 | 11 | 5 | 6 |
| `verificacao-rf044-rf047.pdf` | RF-044 · RF-045 · RF-046 · RF-047 | 06/27/2026 | 8 | 6 | 4 | – |
| `verificacao-rf048-rf049-cu034-cu035.pdf` | RF-048 · RF-049 / CU-034 · CU-035 | 06/27/2026 | 11 | 4 | 2 | 3 |
| `verificacao-rf050-rf051-cu036-cu037.pdf` | RF-050 · RF-051 / CU-036 · CU-037 | 06/28/2026 | 15 | 3 | 1 | 2 |

The last three reports are the re-verification, module by module, of the points raised in the 06/22/2026 general report.

## Critical Inconsistencies (P1)

- **RF-045 vs. RF-044** — "Active" status in manual registration (RF-045.40) needed a note differentiating it from the self-registration approval flow (RF-044.26 → "Awaiting Contract"). Text in RF-045.40, RN-045.04, CA-045.04, and CA-045.19 was incomplete/contradictory regarding "backoffice access".
- **RF-047.26 → RF-049** — partial cancellation post-24h is sent to the refund queue, but RF-049 was modeled for entire orders, lacking granularity per individual ticket.
- **RF-049.33 → RF-048** — refund approval in the queue does not define the impact on agency/agent commission (gap between modules).
- **RF-052** — "Visit Reminder" classified as Opt-in with a 15-minute SLA may be inappropriate for the context (time-sensitive reminder); needs client validation.
- **RF-056** — Menu table does not list modules available for the Agent profile.
- **RF-057 / RF-045** — terminology divergence ("Agency Substatus" vs. "Operation Substatus") between documents describing the same concept.
- **RF-051 / RN-051** — no SLA defined for Google review cache expiration in case of consecutive synchronization failures.

The complete list of findings, with exact references to RF/RN/CU/CA and correction suggestions, is in each individual report.

## How to Contribute / Next Steps

1. Prioritize resolving **P1** items listed in each report before delivery.
2. When correcting a requirement, update the corresponding cross-reference in the other documents pointed out as inconsistent.
3. Generate a new verification round after corrections and version the updated report in this folder.

---
*Reports generated based on cross-analysis of APP-360 project requirements documents, use cases, and acceptance criteria.*
