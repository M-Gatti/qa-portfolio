# QA task template

✅ **Applied in practice** · How I record QA work items on the board (Jira, Azure DevOps): test design, execution, test data setup, documentation. Example is fictional.
[Português](../pt-br/task.md)

A task makes QA work **visible on the board**. If testing a story takes a day, the board should show it.

---

## Template
| Field | What goes there |
|---|---|
| **Title** | `[QA] Verb + object + story`, e.g. "[QA] Test BK-111 waitlist promotion" |
| **Parent** | The story it belongs to |
| **Type of work** | Test design · Execution · Retest · Test data · Documentation · Regression |
| **Description** | What will be done, in 2 or 3 lines |
| **Done when** | Concrete exit: cases written and linked, executed on all platforms, results and evidence attached |
| **Platforms** | Web / Android / iOS |
| **Estimate** | Hours or points, per team convention |
| **Blockers** | If blocked: reason and owner (see [Fail vs Blocked](../../flows/en/fail-vs-blocked.md)) |

---

## Example (fictional: TrilhaFit)
| Field | Value |
|---|---|
| Title | [QA] Test BK-111 waitlist promotion |
| Parent | BK-111 |
| Type of work | Test design + execution |
| Description | Write cases for AC1 to AC4 (state transition + decision table for late cancellation), run on web, Android and iOS |
| Done when | Cases linked to BK-111 in the test repository; all executed; bugs opened with recordings; questions sent to the PO |
| Platforms | Web, Android, iOS |
| Estimate | 6 h |
| Blockers | None |
