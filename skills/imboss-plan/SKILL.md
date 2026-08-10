---
name: imboss-plan
description: >
  Plan engineering work like an AI CTO. Use for roadmaps, sprint plans,
  sequencing, capacity cuts, launch plans, and “what should we build next”.
  Triggers: imboss plan, roadmap, sprint plan, prioritize, sequence work,
  capacity, launch plan, what to build next.
---

# imboss-plan

Turn goals and constraints into a **sequenced, risk-aware plan** non-technical builders can approve and agents can execute.

## Inputs to gather (ask only if missing and material)

- Outcome / success metric  
- Hard deadline or event (launch, demo, fundraising)  
- Constraints (team size, budget, stack, compliance)  
- Non-goals  
- Known risks or dependencies  

## Process

1. Restate the **business outcome** in one sentence  
2. List candidate work; group by outcome, not by tech layer alone  
3. Sequence with critical path and parallel tracks  
4. Cut scope until the plan fits capacity **or** flag the gap  
5. Attach risks + mitigations ([risk-management.md](../../risk-management.md))  
6. List decisions needed and next actions  

Load [decision-framework.md](../../decision-framework.md) when the plan hinges on a fork.

## Output format

```markdown
# Plan: <name>

## Outcome
...

## Recommendation (summary)
...

## Scope
### In
### Out (explicit non-goals)

## Sequenced work
| Phase | Deliverable | Owner | Target | Dependencies |
|-------|-------------|-------|--------|--------------|
| 0 | | | | |
| 1 | | | | |

## Critical path
...

## Capacity / cut list
What we drop first if time runs out:
1. ...

## Risks
| Risk | Score | Mitigation | Owner |
|------|-------|------------|-------|
| | | | |

## Decisions needed
| Decision | Options | Recommend | By when |
|----------|---------|-----------|---------|
| | | | |

## Next actions
1. ...
```

For multi-quarter views, also fill [templates/roadmap.md](../../templates/roadmap.md).

## Rules

- Prefer **thin vertical slices** that produce user-visible learning  
- Dates are ranges + confidence unless the user supplies a fixed date  
- Never invent team capacity; if unknown, state assumptions  
- One recommendation for the default path  

## Anti-patterns

- 40-item backlog with no sequence  
- All P0 everything  
- Plan with no cut list  
- Architecture novel with no business phase gate  
