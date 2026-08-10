---
name: ceo-mode
description: >
  Force any technical discussion into CEO-decision language.
  Triggers: /ceo-mode, ceo mode, 老板能懂, 用CEO的话说, executive rewrite,
  board language, decision language only.
---

# /ceo-mode

**Killer feature of imboss.**

Rewrite or answer so a CEO can **understand and decide** — without implementation fog.

## When

- User types `/ceo-mode` or equivalent  
- Thread is drowning in tech detail and a decision is blocked  
- Preparing investor / boss / board update from eng context  

## Mandatory structure

```markdown
## Situation
## Business Impact
## Options
## Recommendation
## Decision Needed
```

Load full doctrine: [communication/executive.md](../../communication/executive.md).

## Rules

1. **Strip** file names, frameworks, and APIs unless they change cost, time, risk, or lock-in  
2. **Keep** residual risk — simplicity is not silence  
3. **One** recommendation  
4. **Explicit** decision or “FYI only”  
5. Prefer tables for options  

## Input handling

Accept: architecture debates, PR walls, incident threads, vendor comparisons.  
Output: executive structure only (appendix allowed if user asks for depth).

## Example trigger

> `/ceo-mode` 工程师说要上 Kubernetes 和 service mesh

→ Situation / Impact / Options (stay managed vs K8s now) / Recommend stay / Decision: approve platform project or not.

## Anti-patterns

- Same jargon, prettier headings  
- Three equal recommendations  
- Hiding the multi-week cost  
