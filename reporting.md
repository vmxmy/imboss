# Reporting Doctrine

How imboss turns raw work into reports people actually read. Templates live in `templates/`.

---

## Purpose of reporting

Reports exist to:

1. Align stakeholders on **truth**  
2. Surface **risks and decisions** early  
3. Create a **memory** of what happened and why  

They do not exist to perform busyness.

---

## Report types

| Type | Cadence | Primary audience | Template |
|------|---------|------------------|----------|
| Weekly report | Weekly | Founder / eng lead | [weekly-report.md](./templates/weekly-report.md) |
| Executive summary | Ad hoc / milestone | Founder / board | [executive-summary.md](./templates/executive-summary.md) |
| Decision request | When stuck | Decision owner | [decision-request.md](./templates/decision-request.md) |
| Incident report | After severity events | All stakeholders | [incident-report.md](./templates/incident-report.md) |
| Roadmap | Monthly / quarterly | Founder / product | [roadmap.md](./templates/roadmap.md) |

---

## Universal report rules

### 1. Status color with reason

Always pair color with a one-line why:

- **Green** — plan holds; no material risk unmanaged  
- **Yellow** — recoverable slip or risk; plan exists  
- **Red** — outcome at risk; needs decision or help  

### 2. Outcomes over activity

Bad: “Held 12 meetings, opened 40 PRs.”  
Good: “Checkout conversion experiment live for 10% traffic; early +2.1% relative (n small).”

### 3. Separate done / doing / blocked

Never mix shipped work with hopeful work.

### 4. Explicit asks

If you need a decision, money, hire, or priority trade, put it in **Asks** — not implied between lines.

### 5. Forward look

Every periodic report answers: what happens next period if we do nothing vs if we follow the plan.

---

## Weekly report recipe

1. Status + one-line narrative  
2. Wins (outcomes)  
3. Progress vs plan  
4. Metrics that moved (or “no new data”)  
5. Risks / incidents  
6. Asks / decisions  
7. Next week top 3  

Max length for founder weekly: **one page** unless incident-heavy.

---

## Executive summary recipe

1. Context in 2–3 sentences  
2. Recommendation or result  
3. Evidence (3–5 bullets max)  
4. Material risks  
5. Decision / resource ask  
6. Appendix only if needed  

---

## Incident report recipe

1. Summary (user impact first)  
2. Timeline (UTC or local, consistent)  
3. Root cause (or working theory)  
4. Blast radius  
5. Fix / mitigation  
6. Prevention actions with owners  
7. Communication log (who was told what when)  

Severity language should match company policy if one exists; otherwise define S1–S4 briefly.

---

## Metrics hygiene

- Prefer **leading + lagging** pairs when useful  
- Always note **window and sample size**  
- No vanity metrics without a decision attached  
- “TBD” is better than a made-up number  

---

## Anti-patterns

| Anti-pattern | Fix |
|--------------|-----|
| Wall of tasks | Group by outcome / initiative |
| Only good news | Add risks and misses |
| No dates | Add target or confidence |
| Copy-paste Jira dump | Curate; link out |
| Same report every week | Refresh narrative and risks |

---

## Skill routing

Use [skills/imboss-report](./skills/imboss-report/SKILL.md) to generate reports from notes, git history, or chat logs. Apply this doctrine while filling templates.
