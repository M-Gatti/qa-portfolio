# Test data and privacy checklist (LGPD)

📚 **Study reference** · Built from studying Brazil's data protection law (LGPD, Law 13.709/2018) and applying it to QA routines. It is a testing aid, **not legal advice**; the company's DPO and legal team have the final word.
[Português](../pt-br/massa-de-teste-e-privacidade.md)

Two sides of privacy for QA:
1. **How I handle data while testing** (test data, evidence, bug reports).
2. **What I test in the product** (features that exist because of the law).

---

## Part 1: Handling data while testing
**Test data**
- [ ] Prefer **synthetic data** (invented names, generated valid-format documents, `example.com` e-mails)
- [ ] Production data in test environments only if **anonymized** and with a documented reason. Under LGPD art. 12, anonymized data is not personal data, unless the anonymization can be reversed with reasonable effort
- [ ] Only the fields the test needs (principle of **necessity**, art. 6, III)
- [ ] Test accounts belong to the team, not to real people; no personal account used for testing
- [ ] Test data removed or reset when the test cycle ends

**Evidence and reports**
- [ ] Screenshots and recordings show test accounts only; anything real is blurred before attaching
- [ ] No passwords, tokens or full document numbers in bug reports, comments or chat
- [ ] Evidence stored in the team's tool (board, test management), not on personal devices or personal cloud
- [ ] Logs and API responses attached only with personal fields masked

## Part 2: What to test in the product
| Area | Test ideas | LGPD reference |
|---|---|---|
| Consent | Consent is optional where it should be; can be withdrawn as easily as given; product respects withdrawal | Art. 8 |
| Data subject rights | User can see, correct, export and request deletion of their data; deletion really removes or anonymizes | Art. 18 |
| Access control | Each profile sees only what it needs; direct URL or API calls do not bypass permissions | Art. 6, VII and art. 46 |
| Sensitive data | Health, biometric or similar data has stricter access and is not shown where not needed | Art. 5, II and art. 11 |
| Transparency | Privacy notice is reachable and matches what the product actually collects | Art. 6, VI and art. 9 |
| Minimization | Forms ask only for what the feature uses; optional fields are really optional | Art. 6, III |
| Retention | Data is removed or anonymized when the stated purpose ends | Art. 15 and 16 |

## Example (fictional: TrilhaFit)
- **Test data:** members *ana.basic*, *bruno.plus*, *carla.premium*, e-mails `@example.com`, CPF-format numbers from a generator, no real photos.
- **Test case:** *[Privacy] Member requests account deletion: personal data removed, booking history kept only as anonymized statistics.*
- **Access test:** an instructor opens `/members/{id}` of a member who is not in their class → access denied (403), no data in the response.
