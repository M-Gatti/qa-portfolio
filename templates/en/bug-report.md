# Bug report template

✅ **Applied in practice** · The format I use to report defects on Jira and Azure DevOps boards. The example is fictional.
[Português](../pt-br/bug-report.md)

A good bug report lets a developer reproduce the problem **without talking to me first**.

---

## Fields
| Field | What goes there |
|---|---|
| **Title** | `[Area] What happens + when it happens`. No "doesn't work", no "error" alone |
| **Environment** | Environment (staging, production), build/version, platform, device and OS, browser |
| **Account / role** | Which test account and profile (without passwords) |
| **Preconditions** | State needed before step 1 |
| **Steps to reproduce** | Numbered, one action each, starting from a known screen |
| **Expected result** | What should happen, with the source: story, acceptance criterion, rule, prototype |
| **Actual result** | What happened, exactly. Copy messages word for word |
| **Frequency** | Always, intermittent (x of y attempts), once |
| **Severity** | Impact on the product (see below) |
| **Priority** | Urgency for the team. Usually set with the PO, not only by QA |
| **Evidence** | Screen recording, screenshot, request/response, logs |
| **Related items** | Story, test case, similar bugs |

### Severity
| Level | Meaning |
|---|---|
| Critical | Main flow blocked, data loss or security issue, no workaround |
| High | Important feature broken; workaround is hard or not acceptable to users |
| Medium | Feature partially broken; reasonable workaround exists |
| Low | Cosmetic, text, alignment; no functional impact |

**Severity ≠ priority.** A typo on the login screen is Low severity and may still be high priority before a launch.

## Before opening
- Reproduce it at least twice and note the frequency.
- Check if it is already reported.
- Confirm the expected result against the story or rule, not against what *I* think it should do. If the rule is unclear, ask first: that is a question, not a bug.

---

## Example (fictional: TrilhaFit)

**Title:** [Waitlist] Member is promoted from the waitlist but receives no notification when the class is in less than 2 hours

| Field | Value |
|---|---|
| Environment | Staging, build 2.3.0 (412), Android 14, Pixel 7 |
| Account / role | *carla.premium* (Premium member) |
| Severity / Priority | High / to be defined with PO |
| Frequency | Always (3 of 3 attempts) |
| Related | Story BK-111, case TC-0231 |

**Preconditions:** *Yoga, today 18:00* is full. *carla.premium* is #1 on the waitlist. Current time is 16:30.

**Steps to reproduce**
1. Log in on the web as *davi.basic*, who has a confirmed booking in *Yoga, today 18:00*
2. Cancel the booking
3. On the Android device, check notifications for *carla.premium*
4. Open *My classes* in the app as *carla.premium*

**Expected result:** *carla.premium* receives the push notification "A spot opened up: you're booked for Yoga at 18:00" (BK-111, acceptance criterion 3: notification on every promotion, no time restriction).
**Actual result:** No notification arrives. In *My classes* the booking shows as *Confirmed*. When the class starts in more than 2 hours, the notification arrives normally.

**Evidence:** screen recording of steps 2 to 4; response of `POST /bookings/{id}/cancel` with status 200.

**Notes:** the 2-hour window matches the "late cancellation" rule; the promotion may be reusing that condition to skip the notification.
