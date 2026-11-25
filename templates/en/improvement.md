# Improvement template

📚 **Study reference** · For things that are **not bugs** (the product behaves as specified) but could be better: usability, clarity, accessibility, performance perception. Example is fictional.
[Português](../pt-br/melhoria.md)

**Bug or improvement?** If the behavior contradicts a story, rule or prototype, it is a [bug](bug-report.md). If it matches the spec but hurts the user, it is an improvement. When in doubt, ask.

---

## Template
| Field | What goes there |
|---|---|
| **Title** | `[Area] Current situation → proposed change` |
| **Where** | Screen, flow, platform |
| **Current behavior** | What happens today (it matches the spec) |
| **Problem for the user** | Who is affected and how; evidence if any (recording, support tickets, observation during tests) |
| **Suggestion** | One proposal, not a redesign. Options are welcome |
| **Expected benefit** | What gets better and how we would notice |
| **Effort hint** | Small / medium / large, if known |
| **Related** | Story, screen in the prototype |

The PO decides if and when. QA's role is to bring the observation with evidence.

---

## Example (fictional: TrilhaFit)
**Title:** [Booking] Spot limit only shown after the error → show the limit next to the counter

| Field | Value |
|---|---|
| Where | Class details, booking counter, all platforms |
| Current behavior | Member can raise the counter to 5; on *Book*, the app shows "Maximum of 4 spots per booking" (matches BK-104 R1) |
| Problem for the user | The limit appears only after the attempt. In exploratory sessions, the first try with guests usually hit this message |
| Suggestion | Disable "+" at 4 and show "Up to 4 spots" under the counter |
| Expected benefit | Fewer failed attempts; same rule, clearer |
| Effort hint | Small |
| Related | BK-104, prototype v4 screen "Class details" |
