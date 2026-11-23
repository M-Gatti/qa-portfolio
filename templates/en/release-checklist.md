# Release checklist

✅ **Applied in practice** · Based on how I took part in coordinating releases in Agile SaaS squads. Generic version; adapt to the team.
[Português](../pt-br/checklist-de-release.md)

Scale it to the release: a hotfix may need only the smoke section; a major release needs all of it.

---

## Before the release
**Scope**
- [ ] Every story in the release is Done, or moved out with the PO's agreement
- [ ] Release notes list what goes out (stories, fixes, known issues)
- [ ] No open Critical/High bugs, or each one accepted in writing with its risk

**Regression**
- [ ] Regression run on staging, prioritized by risk
- [ ] Main flows checked on every supported platform: login, the core flow, permissions per profile
- [ ] Areas touched by the release retested

**Acceptance**
- [ ] Acceptance (UAT) done with the PO or business, when applicable
- [ ] Known limitations communicated

**Environment**
- [ ] Staging configuration matches production (feature flags, versions)
- [ ] Test data will not reach production

## Go / No-Go
| Condition | ✅ / ❌ |
|---|---|
| No open Critical bugs | |
| High bugs fixed or accepted with documented risk | |
| Regression passed | |
| Acceptance signed off | |
| Rollback plan known | |
| Team informed of the release window | |

Any ❌ → the decision goes to the PO and the tech lead, with the risk written down.

## After the release
**Smoke in production**
- [ ] App opens and login works on each platform
- [ ] Core flow works end to end
- [ ] No critical errors in console or logs
- [ ] Permissions behave per profile

**Follow-up**
- [ ] Errors and user reports watched in the first 24 to 48 hours
- [ ] Any production issue reported and triaged at once
- [ ] Short retro: what escaped, and which test would have caught it
