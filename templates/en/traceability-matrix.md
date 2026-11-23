# Requirements traceability matrix

📚 **Study reference** · Linking each case to its story is part of my practice; this full matrix format (requirement ↔ cases ↔ results ↔ defects) is built from the CTFL v4.0 syllabus (1.4.4, traceability) and common industry practice. Example is fictional.
[Português](../pt-br/matriz-de-rastreabilidade.md)

A traceability matrix answers three questions at a glance:
1. **Is every requirement tested?** (a row with no cases is a gap)
2. **What does this failure affect?** (from a defect back to the requirement)
3. **What do I rerun if this changes?** (from the requirement to its cases)

---

## Template
| Requirement / criterion | Description | Risk | Test cases | Last result | Defects | Coverage |
|---|---|---|---|---|---|---|
| *ID* | *short text* | *H/M/L* | *TC IDs* | *Pass / Fail / Blocked / Not run* | *bug IDs* | *Covered / Partial / Not covered* |

### Rules
- One row per **acceptance criterion or rule**, not per story: a story with five criteria has five rows.
- A row is **Covered** only if all its cases ran and passed; **Partial** if some ran or some failed.
- Keep it in the test management tool when possible; a spreadsheet goes stale fast.

---

## Example (fictional: TrilhaFit, release 2.3)
| Requirement | Description | Risk | Test cases | Last result | Defects | Coverage |
|---|---|---|---|---|---|---|
| BK-104 AC1 | Book 1 to 4 spots | H | TC-0101 to TC-0106 | Pass | | Covered |
| BK-104 AC2 | Class shows "Full" at capacity | H | TC-0107, TC-0108 | Pass | | Covered |
| BK-108 R1 | Credit back on cancellation (4 rules) | H | TC-0150 to TC-0153 | Fail | BUG-140 | Partial |
| BK-111 AC2 | Automatic waitlist promotion | H | TC-0230, TC-0232 | Pass | | Covered |
| BK-111 AC3 | Notification on promotion | M | TC-0231 | Fail | BUG-129 | Partial |
| BK-115 AC1 | Instructor sees own classes only | H | | Not run | | **Not covered** |

**Reading it:** BK-115 has no cases yet, and it is high risk, so it is the first thing to fix. BK-108 and BK-111 have open defects that block release per the exit criteria.

## Summary line for the test report
*6 criteria · 3 covered · 2 partial (2 open defects) · 1 not covered.*
