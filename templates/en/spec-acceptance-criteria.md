# Spec with acceptance criteria

✅ **Applied in practice** in my own projects: every automation in my personal AI-assisted work setup starts from a spec like this. Example is fictional.
[Português](../pt-br/spec-com-criterios-de-aceite.md)

A spec answers *what done looks like* before anyone builds anything. Acceptance criteria are written so that each one **passes or fails**, with no room for "it looks good".

---

## Template
```markdown
# NNNN: <short name>

- Status: draft | approved | in progress | delivered | discarded
- Date: YYYY-MM-DD
- Owner: <name>

## Problem
What hurts today, in 2 to 4 lines. Who feels it and how often.

## Goal
The expected result, in one sentence.

## Acceptance criteria
- [ ] <verifiable criterion>
- [ ] <verifiable criterion>

## Out of scope
What will not be done now, so the scope does not grow along the way.

## Constraints
Cost, where it runs, sensitive data, deadlines.

## How to verify
The test, command, real sample or checklist that proves each criterion.

## Decisions and history
- YYYY-MM-DD: ...
```

## Writing good criteria
| Weak | Strong |
|---|---|
| "The list loads fast" | "The class list shows the first 20 classes in under 2 s on staging, 4G profile" |
| "Errors are handled" | "If the booking API returns 409, the app shows 'This spot was just taken' and keeps the member on the class screen" |
| "Works on mobile" | "Works on Android 13+ and iOS 16+, checked on at least one real device each" |

For behavior, **Given / When / Then** keeps criteria testable:
```gherkin
Given a class with 1 spot left
When a Basic member books 1 spot
Then the booking is confirmed
And the class shows "Full" to other members
```

---

## Example (fictional: TrilhaFit)
**0007: Weekly class reminder**
- **Goal:** members with bookings next week receive one summary e-mail on Sunday.
- **Acceptance criteria**
  - [ ] E-mail sent on Sunday between 18:00 and 19:00, member's time zone
  - [ ] Only members with at least one *Confirmed* booking in the next 7 days receive it
  - [ ] Lists class, day, time and location; no other personal data
  - [ ] Members who opted out of e-mails receive nothing
- **Out of scope:** push notifications, SMS.
- **How to verify:** run the job on staging with 5 seed accounts covering each criterion; compare recipients with the expected list.
