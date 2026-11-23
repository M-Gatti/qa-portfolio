# Story clarification report

✅ **Applied in practice** · The format I use to send QA questions about a user story to product, business and developers before testing. Example is fictional.
[Português](../pt-br/relatorio-de-duvidas.md)

**Why:** ambiguous rules are the cheapest bugs to fix, because they are fixed in a sentence, not in code. One organized message also respects people's time more than ten loose questions.

---

## Format
> **[Story ID] Story title**
> Hi everyone, while reviewing this story for testing I found some points I'd like to confirm. Answers can go directly under each item.
>
> **<Rule or acceptance criterion reference>**
> **Observation:** what the story says (quoted or summarized) and what is missing or conflicting.
> **Question:** one direct question, answerable with a short reply. When possible, offer options.

### Rules
1. **Group by rule or criterion**, in the story's order.
2. **One question per item.** Two questions become two items.
3. **Quote the source** (criterion, rule, prototype screen), so nobody has to search.
4. **Offer options** when you can: "A or B?" gets answered faster than "how should it work?".
5. **No opinion on the solution.** The goal is to confirm behavior, not to redesign it.
6. **Record the answers** in the story, so they become part of the test basis.

---

## Example (fictional: TrilhaFit)
> **[BK-111] Waitlist promotion**
> Hi everyone, while reviewing this story for testing I found some points I'd like to confirm.
>
> **AC 2: "When a spot opens, the first member on the waitlist is booked automatically."**
> **Observation:** the story doesn't say what happens if the first member has reached their plan's booking limit.
> **Question:** in that case, should the spot go to the next member on the list, or should the first member keep their position?
>
> **AC 3: "The member receives a notification."**
> **Observation:** the prototype shows a push notification; the text does not mention e-mail.
> **Question:** push only, or push and e-mail?
>
> **Rule R4: late cancellation (less than 12 h)**
> **Observation:** a promotion can happen less than 12 h before class.
> **Question:** if a member promoted late cancels, does the late-cancellation rule apply to them?
