# Exploratory test charter

📚 **Study reference** · Exploratory testing itself is part of my practice; this session-based format (charter, timebox, debrief) is what I am adopting from the CTFL v4.0 syllabus (4.4.2). Example is fictional.
[Português](../pt-br/charter-exploratorio.md)

---

## Template
| Field | Fill in |
|---|---|
| **Charter** | Explore *<target>* with *<resources / conditions>* to discover *<kind of information>* |
| **Tester / date** | |
| **Timebox** | 45, 60 or 90 minutes |
| **Build / environment / platform** | |
| **Setup** | Accounts, data, devices needed |
| **Areas** | What is in and out of this session |
| **Notes** | Running log: what I tried, what I saw (timestamped if possible) |
| **Bugs** | IDs of bugs opened |
| **Questions** | Things to ask the PO or developers |
| **Ideas** | New scripted cases or new charters |
| **Time split** | % testing / % bug investigation / % setup |

## Debrief (5 to 10 minutes)
1. What did I cover? What did I not get to?
2. What did I find (bugs, questions)?
3. Is this area risky enough for another session?

---

## Example (fictional: TrilhaFit)
| Field | Value |
|---|---|
| Charter | Explore **guest bookings** with **plan changes in the middle of the flow** to discover **limit and credit inconsistencies** |
| Timebox | 60 min |
| Build / env | 2.3.0 (412), staging, Android 14 and web |
| Setup | *bruno.plus* with 2 active bookings; admin access to change plans |
| Notes | 10:05 Booked 3 spots on Plus. 10:12 Downgraded to Basic during checkout: booking kept 3 spots (Basic limit is 2?). 10:20 Same on web: blocked correctly. |
| Bugs | BUG-131 (Android keeps old plan limit during checkout) |
| Questions | Does a downgrade apply to existing bookings or only new ones? |
| Ideas | Scripted case for downgrade during checkout on each platform |
| Time split | 60 / 30 / 10 |
