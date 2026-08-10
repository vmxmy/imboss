# Technical Translation

Bridge between engineering reality and non-technical stakeholders. Pair with [communication.md](./communication.md) and [skills/imboss-explain](./skills/imboss-explain/SKILL.md).

---

## Goal

Preserve **truth and tradeoffs** while dropping unnecessary jargon.

Bad translation: dumbed-down slogans that hide risk.  
Good translation: plain language that still supports a decision.

---

## Translation method

For any technical statement:

1. **What it is** — in everyday words  
2. **Why it matters** — user / money / time / risk  
3. **What changes** — if we do it / don’t  
4. **Cost shape** — time, complexity, ops burden  
5. **Risk** — what can go wrong  

Example:

> **Tech:** “We need an idempotency key on the payment intent endpoint.”  
> **Business:** “If the user double-taps Pay, or the network retries, we might charge them twice. A one-time request ID lets us safely ignore duplicates. About 1–2 days of eng work; high severity if we skip it before launch.”

---

## Phrasebook

### Architecture & systems

| Tech | Plain language |
|------|----------------|
| Monolith | One main app codebase handling many features |
| Microservices | Many small services; more flexibility, more ops cost |
| API | A contract so systems can talk without sharing internals |
| Webhook | They call us when something happens on their side |
| Queue / async job | Work done in the background so the user isn’t waiting |
| Cache | Temporary fast memory; can be stale or wrong if mishandled |
| CDN | Copies static files near users for speed |
| Load balancer | Traffic director across machines |
| Horizontal scale | Add more machines |
| Vertical scale | Use a bigger machine |

### Data

| Tech | Plain language |
|------|----------------|
| Schema migration | Changing the database structure |
| Breaking migration | Change that can break old app versions |
| Backup / restore | Copy of data + ability to bring it back |
| Eventual consistency | Different screens may briefly disagree, then catch up |
| OLTP vs analytics DB | Live transactions DB vs reporting DB |
| PII | Personal data we must protect carefully |
| Encryption at rest / in transit | Protected on disk / protected on the wire |

### Delivery & quality

| Tech | Plain language |
|------|----------------|
| CI | Automated checks on every change |
| CD | Automated path toward production |
| Feature flag | Switch features on/off without full redeploy |
| Canary / staged rollout | Ship to a few users first |
| Rollback | Undo a release |
| Hotfix | Emergency fix in production |
| Tech debt | Shortcuts that slow future work if unpaid |
| Flaky test | Test that fails randomly; undermines trust |
| SLA / SLO | Promised / targeted reliability level |
| Observability | Ability to see health, errors, and user impact |

### Security

| Tech | Plain language |
|------|----------------|
| Authn | Proving who you are |
| Authz | What you’re allowed to do |
| Secret / env var | Password-like config that must not be in git |
| Least privilege | Only the access needed for the job |
| RCE / XSS / SQLi | Classes of attacks that let bad actors run code or steal data — translate by **impact**, not acronym soup |
| Dependency CVE | Known hole in a library we use |
| Audit log | Who did what, when |

### Product engineering

| Tech | Plain language |
|------|----------------|
| MVP | Smallest version that tests the real bet |
| Acceptance criteria | Checklist for “done” everyone can verify |
| Edge case | Rare path that still breaks trust if ignored |
| Rate limit | Cap how often an action can happen |
| Idempotent | Safe to retry |
| Backward compatible | Old clients keep working |

---

## Explain patterns

### ELI-founder (default)

- No class diagrams unless asked  
- Use analogies sparingly (one max)  
- Always attach decision impact  

### ELI-board

- One paragraph max per topic  
- Numbers and risks over mechanisms  
- “What we need from the board” if anything  

### ELI-support

- Customer-visible symptoms  
- Safe workarounds  
- What not to promise  

### Deep-dive (eng / curious founder)

- Interfaces, sequence, failure modes  
- Still start with the business frame  

---

## Diagrams

Prefer simple boxes:

```text
[User] → [App] → [Payments provider]
              ↘ [Database]
```

Avoid UML theater for non-tech audiences. If a diagram needs a legend longer than the diagram, rewrite in prose.

---

## Honesty constraints

When translating:

- Do **not** remove material risks to “sound simple”  
- Do **not** invent certainty (“100% safe”)  
- Do **not** use metaphor as proof  
- Do mark unknowns: “We have not load-tested past 1k concurrent users.”  

---

## Common founder questions (answer shapes)

**“How long will it take?”**  
→ Range + confidence + what would change the estimate + what’s cuttable.

**“Is this scalable?”**  
→ Scalable for what load, at what cost, with what rewrite horizon.

**“Can we just use X tool?”**  
→ Fit, lock-in, cost curve, exit cost, security posture.

**“Why rewrite?”**  
→ Pain today, cost of rewrite, cost of not rewriting, phased option.

**“Is it secure?”**  
→ Against which threats; what’s done; what’s residual; what’s next.

---

## Skill routing

Use [skills/imboss-explain](./skills/imboss-explain/SKILL.md) for full explainers.  
Use this phrasebook inside reports and plans so language stays consistent.
