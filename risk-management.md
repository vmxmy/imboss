# Risk Management

How imboss identifies, scores, mitigates, and accepts risk. Pair with [skills/imboss-risk](./skills/imboss-risk/SKILL.md).

---

## Mindset

Risk management is not fear. It is **priced uncertainty**.

- Name risks early  
- Size them honestly  
- Mitigate, transfer, avoid, or **accept with owner**  
- Never “hope” as a strategy  

---

## Risk taxonomy (default)

Use categories so nothing obvious is missed:

| Category | Examples |
|----------|----------|
| **Product** | Wrong problem, confusing UX, bad adoption |
| **Delivery** | Schedule slip, dependency failure, scope creep |
| **Technical** | Architecture dead-end, data loss, perf cliff |
| **Security** | Auth holes, secret leak, supply chain |
| **Privacy / compliance** | PII handling, region rules, audit gaps |
| **Operational** | On-call gaps, missing runbooks, single owner |
| **Business** | Burn, pricing, competitor, channel loss |
| **People** | Key-person risk, burnout, hiring miss |
| **Reputation** | Public incident, trust break, press risk |

Not every category applies every time. Empty categories can be marked N/A.

---

## Risk register format

```markdown
| ID | Risk | Category | Likelihood | Impact | Score | Mitigation | Owner | Status |
|----|------|----------|------------|--------|-------|------------|-------|--------|
| R1 | ... | Security | H | H | 9 | ... | Alice | Open |
```

### Scoring (simple 1–3)

| Level | Likelihood | Impact |
|-------|------------|--------|
| 1 Low | Unlikely this cycle | Minor inconvenience |
| 2 Med | Plausible | User-visible pain or material delay |
| 3 High | Probable or already happening | Data loss, money loss, severe delay, legal |

**Score** = Likelihood × Impact (1–9).  
**Focus** on scores ≥ 6 first, then ≥ 4 that are cheap to mitigate.

Adjust scale if the company already has one; consistency beats purity.

---

## Treatments

| Treatment | Meaning |
|-----------|---------|
| **Mitigate** | Reduce likelihood or impact |
| **Avoid** | Change plan so risk disappears |
| **Transfer** | Insurance, vendor SLA, contract |
| **Accept** | Live with it; named owner; review date |

Acceptance without an owner is denial.

---

## Pre-mortem

Before major launches or bets, run a short pre-mortem:

> “It is [launch + 6 weeks]. We failed. What went wrong?”

Generate 5–10 failure stories, convert to risks, add mitigations.  
Timebox: 15–30 minutes of thinking for small launches; longer for high stakes.

---

## Go / no-go checklist (shipping)

Minimum bar for user-facing or money-touching releases:

- [ ] Rollback / disable path exists  
- [ ] Critical path monitored or manually watchable  
- [ ] Secrets and permissions reviewed  
- [ ] Data migration is reversible or backed up  
- [ ] Support / founders know customer wording  
- [ ] Open score ≥ 6 risks have treatment  
- [ ] Owner awake for launch window (or explicit accept)  

If any box fails, say **no-go** or **go with named accepted risks**.

---

## Incident linkage

When risk becomes reality:

1. Contain  
2. Communicate  
3. Fix  
4. Write [incident report](./templates/incident-report.md)  
5. Convert learnings into new register items / tests / runbooks  

---

## Proportionality

Do not run enterprise risk theater for a weekend prototype with no users.

Scale process with:

- number of users  
- money / PII involved  
- irreversibility  
- public visibility  

A hobby feature can accept more product risk. A payments feature cannot accept silent security risk.

---

## Anti-patterns

| Anti-pattern | Fix |
|--------------|-----|
| Risk list of 50 items, none owned | Top 5 with owners |
| Only technical risks | Use full taxonomy |
| Green status + ignored high risks | Status must reflect risk |
| Mitigations that are just “be careful” | Make mitigations testable |
| Risk review once, never updated | Revisit on plan change |

---

## Skill routing

Use [skills/imboss-risk](./skills/imboss-risk/SKILL.md) for dedicated reviews.  
Plans and reports should embed a short **Risks** section by default ([principles.md](./principles.md) §3).
