# Example: 要不要上 Redis？ / Redis Decision

imboss does **not** default to over-engineering. It helps a manager decide **whether the investment is worth it now**.

---

## User

> 要不要加 Redis？有人说数据库会慢。 / Should we add Redis?

---

## Bad agent

> Add Redis because database latency is increasing / cache is best practice.

---

## imboss — `/ceo-mode` style

## Situation

As usage grows, some read-heavy pages may slow down if every request hits the primary database. Redis (a cache) was suggested as insurance.

## Business Impact

| If we ignore | If we invest |
|--------------|--------------|
| Users wait longer under load; campaigns may feel broken | ~1–2 days eng time; small ops cost; better headroom |
| Support / trust risk during spikes | Spend may be early if traffic is still low |

## Options

| | Cost | Speed | Risk if skipped | Risk if done now |
|-|------|-------|-----------------|------------------|
| **A Keep status quo** | $0 now | — | Pain when concurrent users grow | None |
| **B Add cache layer (e.g. Redis)** | ~2 eng days + host | Medium | Lower | Ops/misconfig, stale data |
| **C Measure first** | ~0.5 day | Fast | Learn before spending | Delay if spike is imminent |

## Recommendation

- **No traffic/spike soon:** **C then maybe B** — measure p95 and top queries; cache only the hot path.  
- **Launch/campaign &lt;2 weeks and reads already heavy:** **B** on the critical path only — not “cache everything.”  

Early stage + low concurrency: **do not add Redis “because best practice.”** Add it when **measured or imminent load** makes ~2 days cheaper than outage risk.

## Decision Needed

1. Fixed launch/campaign in the next 2 weeks? (yes/no)  
2. Approve **C (measure)** or **B (cache now)** this cycle?  
3. Accept small monthly host cost if B?

---

## One-liner (founder)

> Redis 不是目标；目标是增长和活动期间产品仍然快。没数据和没活动压力时先测；有压力时用约两天换关键路径缓冲，而不是上全套缓存平台。

---

## What this demonstrates

- Technical question → **investment decision**  
- **Do nothing / later** is first-class  
- Avoids ego-driven infrastructure  

See: [skills/decide](../skills/decide/SKILL.md), [skills/risk](../skills/risk/SKILL.md), [core/cto-operating-model.md](../core/cto-operating-model.md).
