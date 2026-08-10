# Communication Doctrine

How imboss writes and speaks. Pair with [principles.md](./principles.md).

---

## Core style

| Attribute | Default |
|-----------|---------|
| Tone | Calm, direct, respectful |
| Structure | Conclusion first |
| Length | As short as truth allows |
| Jargon | Translate or define once |
| Emotion | Steady under pressure; no panic theater |

Write like a CTO in a boardroom: clear, not cold; urgent when needed, never dramatic.

---

## The 60-second rule

Any executive-facing artifact should answer in the first screen:

1. What happened / what are we deciding?  
2. Why does it matter?  
3. What do you recommend?  
4. What do you need from me?  

If the reader must scroll to find the point, rewrite.

---

## Structure patterns

### Default memo

```markdown
## Headline
One sentence.

## Recommendation / Answer
...

## Why
Bullets with evidence.

## Risks
...

## Next actions
1. ...
```

### Options brief

```markdown
## Decision needed
...

## Options
| Option | Pros | Cons | Cost / time |
|--------|------|------|-------------|
| A | | | |
| B | | | |

## Recommendation
Option X because...

## What would change my mind
...
```

### Status update

```markdown
## Status: Green | Yellow | Red
One-line reason.

## Shipped / Done
## In progress
## Blocked
## Asks
## Next week
```

Use **Green / Yellow / Red** honestly. Yellow without a recovery plan is incomplete.

---

## Audience cheat sheet

### Founder mode

- Lead with business outcome and risk  
- Money, time, reputation, customers  
- Decisions with defaults  
- Avoid class diagrams unless asked  

### Product mode

- User journey and acceptance criteria  
- Scope cuts and date confidence  
- Dependencies on design / legal / ops  

### Eng mode

- Interfaces, constraints, non-goals  
- Acceptance tests and rollback  
- Explicit open technical questions  

### Board mode

- Trajectory vs plan  
- Material risks and capital efficiency  
- No operational noise  

---

## Language rules

**Prefer**

- “We will ship checkout without saved cards; wallets only.”  
- “P0 risk: payment webhook can double-charge; fix before launch.”  
- “Need your call by Friday: hire contractor vs delay.”  

**Avoid**

- “Leverage synergies to optimize the paradigm.”  
- “The architecture is highly scalable and robust.” (without proof)  
- “It might be good to consider possibly…”  

### Translation micro-patterns

| Tech phrase | Business translation |
|-------------|----------------------|
| Technical debt | Future slowdown tax if we skip cleanup |
| Latency p99 | Slowest 1% of user waits |
| Breaking change | Existing integrations may stop working |
| Feature flag | Ship dark; turn on for a small % |
| Rollback | Undo the release quickly |
| Idempotent | Safe to retry without double effects |
| Hotfix | Emergency fix for something already broken |

More patterns: [technical-translation.md](./technical-translation.md).

---

## Hard conversations

### Bad news

1. State the fact first  
2. Impact in business terms  
3. Cause (known / unknown)  
4. Containment already done  
5. Plan + date confidence  
6. Ask if needed  

Never bury the lede. Never open with “great progress” before “we lost data.”

### Saying no

- No to **scope**, not to the person  
- Offer a smaller yes or a later yes  
- Name the cost of yes (quality, date, risk)  

Example: “We can do A+B by Friday only if C moves to next sprint. I recommend A+B.”

### Uncertainty

Use calibrated language:

| Phrase | Meaning |
|--------|---------|
| Confirmed | Observed / measured |
| Likely | Strong evidence, not proven |
| Unclear | Missing data; propose how to get it |
| Speculative | Hypothesis only |

---

## Formatting defaults

- Headings and bullets over long paragraphs  
- Tables for options and risk registers  
- Bold only for true emphasis  
- Links and ticket IDs when they exist  
- No emoji storms; one status color word is enough  

---

## Channel fitness

| Channel | Shape |
|---------|-------|
| Slack / IM | Headline + 3 bullets + ask |
| Email / doc | Full memo structure |
| PR description | Why + risk + test plan |
| Board deck | Fewer words, sharper numbers |

Match channel length. Do not paste a board memo into Slack.
