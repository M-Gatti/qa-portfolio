# Risk matrix (risk-based testing)

📚 **Study reference** · Based on CTFL v4.0, section 5.2 (risk management). Example is fictional.
[Português](../pt-br/matriz-de-risco.md)

Risk-based testing spends test effort where failure would hurt most. **Risk level = likelihood × impact.**

---

## Scales
| Score | Likelihood | Impact |
|---|---|---|
| 1 | Unlikely: simple, stable, well-known code | Minor: cosmetic, easy workaround |
| 2 | Possible: new code or moderate complexity | Moderate: feature degraded, workaround exists |
| 3 | Likely: complex, changed often, integrations, history of bugs | Severe: main flow blocked, money, data or trust at stake |

## Matrix
| | Impact 1 | Impact 2 | Impact 3 |
|---|---|---|---|
| **Likelihood 3** | 3 · Medium | 6 · High | 9 · High |
| **Likelihood 2** | 2 · Low | 4 · Medium | 6 · High |
| **Likelihood 1** | 1 · Low | 2 · Low | 3 · Medium |

## What the level changes
| Level | Test response |
|---|---|
| High (6 to 9) | Several techniques, negative cases, all platforms, exploratory session, early in the sprint, in regression |
| Medium (3 to 4) | Main techniques, main platforms, in regression if the area changes often |
| Low (1 to 2) | Happy path and smoke |

## Register
| ID | Risk (what could go wrong) | L | I | Level | Response | Owner | Status |
|---|---|---|---|---|---|---|---|

---

## Example (fictional: TrilhaFit, release 2.3)
| ID | Risk | L | I | Level | Response |
|---|---|---|---|---|---|
| R1 | Two members get the last spot at the same time | 2 | 3 | 6 · High | Concurrency tests on booking API; exploratory session; in regression |
| R2 | Credit-back rule applied wrong on cancellation | 2 | 3 | 6 · High | Decision table, all 4 rules tested on every platform |
| R3 | Waitlist notification not sent | 3 | 2 | 6 · High | State transition cases; check push on Android and iOS |
| R4 | Class list sorting wrong on small screens | 2 | 1 | 2 · Low | Smoke on one small device |

Review the register when scope changes or a risk materializes. A risk that keeps producing bugs gets its likelihood raised.
