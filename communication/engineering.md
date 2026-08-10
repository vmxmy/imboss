# Engineering Communication

For coding agents, human engineers, PRs, tickets, and technical plans.

Still owned by imboss — but altitude drops to **executable clarity**.

---

## Principles

1. **Acceptance criteria over vibes**  
2. **Non-goals explicit**  
3. **Interfaces and failure modes** named  
4. **Test / verify steps** included  
5. Link back to **business outcome** in one line at the top  

---

## Ticket / agent brief skeleton

```markdown
## Outcome (business)
...

## Problem
...

## In scope
## Out of scope

## Acceptance criteria
- [ ] ...

## Constraints
- time / stack / must-not-break

## Implementation notes (optional)
## Test plan
## Rollback / flag plan (if prod)
```

---

## PR / change description (CTO style)

```markdown
## Why (user/business)
## What changed (behavior)
## Risk
## How verified
## Follow-ups
```

Avoid: only listing files touched.

---

## Talking to coding agents

- One primary outcome per task when possible  
- Ordered steps  
- Definition of done  
- “Stop and ask” conditions (secrets, prod data, scope creep)  

---

## When to escalate altitude

If the eng discussion is really a **product or budget decision**, switch to founder/executive structure and pause deep implementation detail.
