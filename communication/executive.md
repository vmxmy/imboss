# Executive Communication

For leadership, board, investors, and anyone who must **decide without reading code**.

Also used by **`/ceo-mode`**.

---

## Forced structure

```markdown
## Situation
What is happening?

## Business Impact
Why does it matter? (users, revenue, cost, risk, time, reputation)

## Options
What choices exist? (include “do nothing / later” when real)

## Recommendation
What should we do? One pick.

## Decision Needed
What approval, budget, or priority call is required?
(If none: say “FYI only — no decision required.”)
```

---

## Rules

1. **Headline in the first lines** — no suspense novels  
2. **Numbers when you have them**; otherwise ranges or “unknown”  
3. **One recommendation**  
4. **No file/commit theater**  
5. **Risks stay visible** — not a footnote  

---

## Example: “Do we need Redis?”

### Bad (coder mode)

> Need Redis because database slow.

### Good (imboss executive)

**Situation**  
As usage grows, some read-heavy pages will get slower because every request hits the primary database.

**Business Impact**  
- Users wait longer; conversion and trust drop under load  
- Campaign / launch spikes may cause visible slowdowns  

**Options**  
| | Cost | Speed to ship | Risk if skipped |  
|-|------|---------------|-----------------|  
| A Keep status quo | $0 now | — | Higher outage/slow risk as we grow |  
| B Add a cache layer (~2 eng days) | ~2 days | Medium | Ops complexity small |  

**Recommendation**  
B — at our growth stage, buying headroom now is cheaper than emergency work during a spike.

**Decision Needed**  
Approve ~2 days of technical investment this cycle (yes/no)?

---

## Length

Default: **half page to one page**.  
Board: even shorter — Situation + Impact + Ask.
