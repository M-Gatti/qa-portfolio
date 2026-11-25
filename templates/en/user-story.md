# User story (PBI) template

✅ **Applied in practice** for reviewing stories before testing (the checklist below).
📚 **Study reference** for writing stories from scratch: that is usually the PO's job; the format follows common Agile practice and the CTFL v4.0 syllabus (4.5, collaboration-based test approaches).
[Português](../pt-br/historia-de-usuario.md)

---

## Template
```markdown
# [ID] <short title: who + what>

**As a** <type of user>
**I want** <action>
**So that** <benefit>

## Context
Why now, link to prototype, related stories.

## Business rules
- R1: ...
- R2: ...

## Acceptance criteria
- AC1: Given <state>, when <action>, then <observable result>
- AC2: ...

## Out of scope
What this story does not cover.

## Platforms and profiles
Web / Android / iOS · which user profiles are affected.

## Open questions
Filled during refinement; answers recorded here.
```

## QA review checklist (before the story is "ready")
- [ ] Every acceptance criterion has an **observable** result
- [ ] Rules have **limits and exceptions** written (minimum, maximum, what happens at the edge)
- [ ] **Negative paths** are described (errors, empty states, no permission)
- [ ] Prototype and text **agree**
- [ ] **Profiles and platforms** are explicit
- [ ] Dependencies (other stories, APIs, data) are listed
- [ ] Small enough to test inside the sprint

---

## Example (fictional: TrilhaFit)
**[BK-104] Member books spots in a class**

**As a** member **I want** to book 1 to 4 spots in a class **so that** I can train with guests.

**Business rules**
- R1: 1 to 4 spots per booking.
- R2: a booking cannot exceed the spots left in the class.
- R3: Basic members can hold at most 2 active bookings.

**Acceptance criteria**
- AC1: Given a class with spots left, when the member books 1 to 4 spots, then the booking appears in *My classes* as *Confirmed*.
- AC2: Given the class reaches capacity, then other members see "Full" and *Join waitlist*.
- AC3: Given a Basic member with 2 active bookings, when they try to book again, then the app shows "Your plan allows 2 active bookings".

**Out of scope:** payment for guests. **Platforms:** web, Android, iOS. **Profiles:** member (Basic, Plus, Premium).
