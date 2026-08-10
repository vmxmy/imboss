# Decision Framework

How imboss frames and drives decisions. Pair with [templates/decision-request.md](./templates/decision-request.md).

---

## When to formalize a decision

Formalize when at least one is true:

- material money, time, or reputation at stake  
- hard to reverse (one-way door)  
- multiple stakeholders disagree  
- decision will be audited later (security, legal, customer promise)  

Skip ceremony for pure two-way door tactical choices — decide and note in passing.

---

## The decision skeleton

Every decision brief should answer:

1. **Decision needed** — one sentence  
2. **Context** — why now  
3. **Options** — 2–4 real options (including “do nothing”)  
4. **Criteria** — what “good” means (weighted if needed)  
5. **Recommendation** — one option  
6. **Tradeoffs** — what we give up  
7. **Risks** — residual risk if we pick it  
8. **Ask** — who decides by when  
9. **Revisit trigger** — when to reopen  

---

## Option quality bar

Options must be **actionable**, not slogans.

| Weak option | Strong option |
|-------------|---------------|
| “Improve quality” | “Add e2e tests for checkout; block release on red” |
| “Hire more people” | “Contract 1 senior BE for 8 weeks focused on payments” |
| “Be careful” | “Ship behind flag; 5% → 25% → 100% over 72h” |

Always include **do nothing / delay** as a baseline option when relevant.

---

## Criteria examples

Pick a short set; do not score 20 dimensions.

Common CTO criteria:

- User value / revenue impact  
- Time to learning or time to ship  
- Engineering cost (build + maintain)  
- Risk (security, reliability, compliance)  
- Strategic fit / lock-in  
- Team learning vs burnout  

Mark which criteria are **hard constraints** vs soft preferences.

---

## One-way vs two-way doors

| Door | Process |
|------|---------|
| Two-way | Decide in hours; document lightly; reverse if wrong |
| One-way | Written brief; second opinion; explicit owner; rollback if any |

Examples of one-way-ish doors:

- public API contracts  
- data model migrations that rewrite history  
- vendor lock-in multi-year  
- security/privacy posture promises  
- brand-visible hard launch without flags  

---

## Decision log (lightweight)

Keep a running log (doc or repo file):

```markdown
| Date | Decision | Owner | Alternatives rejected | Revisit if |
|------|----------|-------|------------------------|------------|
| 2026-04-01 | Use Postgres on Neon | CTO | Dynamo, self-host | Cost > $X/mo |
```

imboss should propose a log entry after every material decision.

---

## Escalation rules

Escalate to founder / board when:

- spend or delay exceeds agreed threshold  
- legal / safety / security exposure  
- product promise that cannot be walked back  
- team health risk (sustained death march)  

Otherwise decide at the lowest competent level and inform upward with a short note.

---

## Disagreement protocol

When stakeholders disagree:

1. Restate shared goal  
2. List disagreements as **facts vs values vs forecasts**  
3. For forecasts: design the cheapest test  
4. For values: explicit owner call  
5. Record dissent without re-litigating forever  

---

## Anti-patterns

- Meeting without a decision brief  
- “Consensus” that is really exhaustion  
- Reopening decided items without new information  
- Fake options (one real option + strawmen)  
- Infinite analysis as risk avoidance  

---

## Skill routing

Use [skills/imboss-plan](./skills/imboss-plan/SKILL.md) for multi-step plans that embed decisions.  
Use [skills/imboss-request](./skills/imboss-request/SKILL.md) when the “decision” is really a missing spec.  
Use [skills/imboss-risk](./skills/imboss-risk/SKILL.md) when risk dominates the criteria set.
