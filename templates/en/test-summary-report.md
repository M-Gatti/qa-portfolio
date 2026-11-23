# Test summary report

📚 **Study reference** · Based on the test completion report in the CTFL v4.0 syllabus (5.3.2) and ISO/IEC/IEEE 29119-3. I report test results to the team in practice; this full report format is a study reference. Example is fictional.
[Português](../pt-br/relatorio-de-resumo-de-teste.md)

The report exists to support **one decision**: can this go out, and with which risks? Lead with the answer, then the evidence.

---

## Template
**1. Recommendation** · Go / Go with risks / No-go, in one or two sentences.

**2. Scope** · What was tested (stories, journeys, platforms, build) and what was not.

**3. Results**
| Metric | Value |
|---|---|
| Planned / executed cases | |
| Passed / failed / blocked / not run | |
| Acceptance criteria covered | (from the [traceability matrix](traceability-matrix.md)) |

**4. Defects**
| Severity | Found | Fixed | Open | Accepted by PO |
|---|---|---|---|---|

**5. Open risks** · Each open defect or untested area, its impact, and who accepted it.

**6. Deviations from the plan** · What changed and why (scope, environment, dates).

**7. Lessons** · One or two things to keep or change in the next cycle.

---

## Example (fictional: TrilhaFit, release 2.3)
**1. Recommendation:** **Go with risks.** Booking and waitlist are stable on all platforms. One High defect in notifications remains open, accepted by the PO with a workaround.

**2. Scope:** stories BK-101 to BK-118, build 2.3.0 (418), web, Android 13 and 14, iOS 16 and 17. Not tested: payments (other team), tablet layouts.

**3. Results**
| Metric | Value |
|---|---|
| Planned / executed cases | 142 / 138 |
| Passed / failed / blocked / not run | 131 / 4 / 3 / 4 |
| Acceptance criteria covered | 39 of 41 |

**4. Defects**
| Severity | Found | Fixed | Open | Accepted by PO |
|---|---|---|---|---|
| Critical | 1 | 1 | 0 | |
| High | 4 | 3 | 1 | 1 (BUG-129) |
| Medium | 7 | 5 | 2 | 2 |
| Low | 5 | 2 | 3 | 3 |

**5. Open risks:** BUG-129: members promoted from the waitlist less than 2 h before class get no push notification. Impact: may miss the class. Workaround: e-mail is sent. Accepted by the PO until 2.3.1.

**6. Deviations:** the exit criterion "no open High defects" from the [test plan](test-plan.md) was not met; the PO accepted BUG-129 in writing as an exception. 3 cases blocked by staging downtime on day 8; rerun on day 9. Tablet layouts moved to 2.4.

**7. Lessons:** waitlist rules generated most questions; next time, build the decision table during refinement.
