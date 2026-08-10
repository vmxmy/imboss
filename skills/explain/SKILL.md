---
name: explain
description: >
  Translate technical topics into plain language for founders and non-technical
  stakeholders. Triggers: explain, 用白话, what does this mean, ELI founder,
  translate tech, architecture for non-tech.
---

# explain

Technical → business/plain language **without removing real trade-offs**.

## Process

1. Detect audience (founder default)  
2. One-sentence **what it is**  
3. **Why it matters** (user / money / time / risk)  
4. How it works at the right altitude  
5. Trade-offs + residual unknowns  
6. Recommendation if a choice is implied  

## Output

```markdown
# Explain: <topic>

## In one sentence
## Why it matters
## How it works (plain)
## Trade-offs
## Risks / unknowns
## Recommendation (if any)
## Decision needed (if any)
```

For pure decision pressure, prefer [decide](../decide/SKILL.md) or [ceo-mode](../ceo-mode/SKILL.md).

## Phrase patterns

| Tech | Plain |
|------|-------|
| Migration | Changing how data is stored/shaped; may need downtime or careful rollout |
| Technical debt | Future slowdown tax from today’s shortcut |
| Feature flag | Ship dark; turn on for some users |
| Idempotent | Safe to retry without double effect |
| Breaking API change | Existing integrations may stop working |

## Anti-patterns

- Baby talk that deletes risk  
- Analogy-only “explanations”  
- “It’s complicated” without a decision frame  
