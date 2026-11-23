# Test case template

✅ **Applied in practice** · The structure and rules are the ones I use when writing cases in a test management tool (Azure Test Plans). The example is fictional.
[Português](../pt-br/caso-de-teste.md)

---

## Fields
| Field | What goes there |
|---|---|
| **Title** | `[Area] Action + condition + expected outcome`. Readable without opening the case |
| **Story / requirement** | ID of the user story or rule it covers (traceability) |
| **Platform** | Web, Android, iOS, or all |
| **Priority** | 1 (blocks the main flow) to 3 (cosmetic or rare path) |
| **Technique** | Which technique produced it (partition, boundary, decision table, state transition, error guessing) |
| **Preconditions** | State that must exist before step 1: account, data, permissions |
| **Test data** | Exact values, not "a valid user" |
| **Steps** | One action per step |
| **Expected result** | Observable result per step: text, state, screen, API response |
| **Tags** | Area, type (smoke, regression), risk |

## Writing rules
1. **One behavior per case.** If the title needs "and", it is probably two cases.
2. **Expected results must be observable.** "Works correctly" is not an expected result; "Booking appears under *My classes* with status *Confirmed*" is.
3. **Steps are actions, not checks.** Checks live in the expected result column.
4. **Data is explicit.** Anyone on the team should be able to run the case without asking.
5. **Same case, many platforms.** Write once; mark the platforms. Split only when behavior really differs.
6. **Link the story.** A case without traceability cannot show coverage.

---

## Example (fictional: TrilhaFit)

**Title:** [Booking] Book a class with one spot left: booking confirmed and class becomes full
**Story:** BK-104 · **Platform:** Web, Android, iOS · **Priority:** 1 · **Technique:** Boundary value analysis
**Preconditions:** Member *ana.basic* (Basic plan, 0 active bookings) is logged in. Class *Spinning, Mon 07:00* has capacity 20 and 19 bookings.
**Test data:** account *ana.basic*; class ID *CL-0712*

| # | Step | Expected result |
|---|---|---|
| 1 | Open *Classes* and select *Spinning, Mon 07:00* | Class details show "1 spot left" and the *Book* button is enabled |
| 2 | Tap *Book* | Confirmation message "You're booked!" is shown |
| 3 | Open *My classes* | *Spinning, Mon 07:00* appears with status *Confirmed* |
| 4 | Log in as *bruno.plus* and open the same class | Class shows "Full" and the button changes to *Join waitlist* |

**Tags:** booking, regression, boundary

### Why this case exists
The capacity boundary (19 → 20 bookings) is where the button, the counter and the waitlist rule all change at once. It is the cheapest place to catch an off-by-one error.
