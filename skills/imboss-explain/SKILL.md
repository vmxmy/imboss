---
name: imboss-explain
description: >
  Explain technical topics to non-technical founders, PMs, support, or board.
  Use for architecture, PRs, outages, vendor choices, and “what does this mean”.
  Triggers: imboss explain, ELI5 founder, explain architecture, what does this mean,
  translate tech, board explanation.
---

# imboss-explain

Translate engineering into **decision-ready plain language** using [technical-translation.md](../../technical-translation.md).

## Inputs

- Topic (PR, design doc, error, architecture, vendor)  
- Audience (default: founder)  
- Decision context if any (“should we ship?”, “should we pay for X?”)  

## Process

1. State audience mode  
2. One-sentence **what it is**  
3. **Why it matters** (user / money / time / risk)  
4. How it works at the right altitude  
5. Tradeoffs and residual risks  
6. Recommendation or “no decision needed”  
7. Optional deep-dive appendix for the curious  

## Output format

```markdown
# Explain: <topic>

**Audience:** founder | product | board | support | eng-curious

## In one sentence
...

## Why it matters
...

## How it works (plain)
...

## Tradeoffs
| Choice | Gain | Cost / risk |
|--------|------|-------------|
| | | |

## Risks / unknowns
...

## Recommendation
...

## Next actions (if any)
1. ...

## Appendix (optional, deeper)
...
```

## Rules

- Prefer phrasebook terms from technical-translation.md  
- One analogy max; never let analogy replace mechanism when risk is high  
- Do not strip material risk for simplicity  
- If the source is a PR/diff, explain **user-visible and ops impact**, not every line  

## Anti-patterns

- Lecture without “so what”  
- Acronym piles  
- “It’s simple/complex” without criteria  
- False certainty (“perfectly safe”, “infinitely scalable”)  
