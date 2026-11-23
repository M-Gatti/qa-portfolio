# Test plan template

📚 **Study reference** · Structure based on the CTFL v4.0 syllabus (section 5.1.1, test plan content) and on the ISO/IEC/IEEE 29119-3 test plan document.
[Português](../pt-br/plano-de-teste.md)

A test plan answers one question: *how are we going to give the team enough information to decide whether this can ship?*
Keep it short. A plan nobody reads is worse than a one-page plan everybody follows.

> Example values in *italics* use **TrilhaFit**, a fictional gym class booking app.

---

## 1. Context
| Field | Fill in |
|---|---|
| Product / feature | *TrilhaFit: class booking and waitlist (release 2.3)* |
| Version of this plan | *1.0, 2026-11-23* |
| Owner | *QA name* |
| Test basis | *User stories BK-101 to BK-118, prototype v4, booking business rules v2* |
| Platforms | *Web (Chrome, Safari), Android 13+, iOS 16+* |

## 2. Scope
**In scope:** *booking, cancelling, waitlist promotion, booking limits per plan.*
**Out of scope:** *payments (covered by the payments team), admin panel.*

## 3. Objectives
What the testing must show. Write them so someone can say "met" or "not met".
- *Every acceptance criterion of BK-101 to BK-118 has at least one executed test.*
- *No open defect of severity Critical or High at release.*

## 4. Assumptions and constraints
- *Staging has the same booking rules as production.*
- *Only one iOS physical device available; other versions via cloud devices.*

## 5. Stakeholders and communication
| Who | Needs | Channel / frequency |
|---|---|---|
| *Product owner* | *Release readiness* | *Test summary at the end of each sprint* |
| *Developers* | *Defects with evidence* | *Board, as found* |

## 6. Risks
Product risks drive *what* to test more deeply; project risks threaten *the plan itself*. Score each one (likelihood × impact, 1 to 3).

| ID | Risk | Type | L | I | Score | Response |
|---|---|---|---|---|---|---|
| R1 | *Two users get the last spot at the same time* | Product | 2 | 3 | 6 | *Concurrency tests on booking; exploratory session* |
| R2 | *Prototype changes after test design* | Project | 2 | 2 | 4 | *Review cases at sprint mid-point* |

## 7. Test approach
| Item | Decision |
|---|---|
| Test levels | *System testing and acceptance testing (with the PO)* |
| Test types | *Functional, regression of booking flows, basic usability, API checks on booking endpoints* |
| Techniques | *Equivalence partitioning and boundary values for limits, decision table for cancellation rules, state transition for booking status, exploratory sessions for waitlist* |
| Test data | *One test account per plan type (Basic, Plus, Premium) and per role (member, instructor)* |
| Environment | *Staging, real devices plus cloud devices* |
| Independence | *Tested by QA, not by the developer of the story* |

## 8. Entry and exit criteria
**Entry (ready to test):** *story has acceptance criteria, build deployed to staging, test data available.*
**Exit (done testing):** *all planned tests executed, no open Critical/High defects, Medium defects accepted by the PO in writing.*

## 9. Deliverables
*Test cases in the test management tool, defect reports, test summary report.*

## 10. Metrics
*Executed vs planned tests, defects by severity and status, acceptance criteria covered.*

## 11. Schedule
| Activity | When |
|---|---|
| *Test analysis and design* | *Days 1 to 3 of the sprint* |
| *Execution and retest* | *As stories reach "Ready for QA"* |
| *Regression and summary* | *Last 2 days of the sprint* |

---

### Notes
- The syllabus treats the plan as a living document: update it when scope or risk changes, and record what changed.
- If the team is small, sections 5, 9 and 10 can be a single line each.
