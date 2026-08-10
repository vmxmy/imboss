---
name: imboss-request
description: >
  Turn fuzzy founder/PM intent into crisp tickets, specs, RFCs, or agent-ready
  task briefs. Triggers: imboss request, write a ticket, spec this, RFC,
  agent brief, acceptance criteria, turn this idea into tasks.
---

# imboss-request

Convert vague intent into **executable requests** coding agents and humans can ship against.

## Inputs

- Raw ask (voice note style OK)  
- Constraints (date, platform, must-not-break)  
- Definition of success if known  

## Process

1. Restate the problem and outcome  
2. Clarify non-goals  
3. Write acceptance criteria that are testable  
4. Split into phased deliverables if large  
5. Flag risks and open questions that **block** coding  
6. Produce agent-ready task list (ordered)  

Use [decision-framework.md](../../decision-framework.md) if the ask hides a product decision.

## Output format

```markdown
# Request: <title>

## Problem
...

## Outcome / success
...

## Users & context
...

## In scope
- ...

## Out of scope
- ...

## Acceptance criteria
- [ ] ...
- [ ] ...

## Constraints
- ...

## Proposed approach (optional)
...

## Agent task breakdown
1. ...
2. ...

## Risks
| Risk | Mitigation |
|------|------------|
| | |

## Open questions (blocking)
1. ...

## Non-blocking assumptions
- We assume ...
```

## Quality bar for acceptance criteria

Each criterion should be falsifiable:

| Weak | Strong |
|------|--------|
| “Works well” | “Checkout completes in <3s p95 on staging with test card” |
| “Secure login” | “Session expires after 7d idle; password reset invalidates old sessions” |
| “Mobile friendly” | “Primary flow usable at 375px width without horizontal scroll” |

## Agent-ready rules

- One primary outcome per request when possible  
- Explicit files/areas only when known; otherwise describe behavior  
- Include test / verification steps  
- Mark human-only steps (App Store, bank KYC, legal)  

## Anti-patterns

- Novel-length PRD with no acceptance tests  
- Hidden decisions (“make it delightful”) without examples  
- Mixing five epics into one ticket  
- Starting implementation while blocking questions remain — list them first  
