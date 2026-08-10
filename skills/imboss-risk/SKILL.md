---
name: imboss-risk
description: >
  Risk review, pre-mortem, launch go/no-go, and risk register updates.
  Triggers: imboss risk, pre-mortem, risk review, go/no-go, launch review,
  threat model light, what could go wrong.
---

# imboss-risk

Surface and treat risks before they become incidents. Follow [risk-management.md](../../risk-management.md).

## Modes

| Mode | When |
|------|------|
| **Register** | General plan / feature risk list |
| **Pre-mortem** | Before launch or big bet |
| **Go/no-go** | Ship decision window |
| **Post-incident feed** | Convert incident into new risks / mitigations |

## Process

1. Frame the subject (feature, launch, vendor, migration)  
2. Walk taxonomy categories (product, delivery, tech, security, privacy, ops, business, people, reputation)  
3. Score likelihood × impact (1–3 each)  
4. Sort by score; focus ≥ 6 then cheap ≥ 4  
5. Assign treatment + owner for each top risk  
6. State residual risk after mitigation  
7. For go/no-go: checklist + clear **GO / GO WITH ACCEPTS / NO-GO**  

## Output format

```markdown
# Risk review: <subject>

**Mode:** register | pre-mortem | go/no-go  
**Overall:** Green | Yellow | Red — <one line>

## Top risks
| ID | Risk | Cat | L | I | Score | Treatment | Owner | Status |
|----|------|-----|---|---|-------|-----------|-------|--------|
| R1 | | | | | | | | |

## Detail (top risks)
### R1 — <title>
- Scenario: ...
- Impact if realized: ...
- Mitigation: ...
- Residual risk: ...
- Detection: how we would notice

## Pre-mortem failures (if mode)
1. ...

## Go / no-go (if mode)
- [ ] Rollback path
- [ ] Monitoring / watch plan
- [ ] Secrets & permissions
- [ ] Data safety
- [ ] Comms ready
- [ ] High risks treated or accepted

**Decision:** GO | GO WITH ACCEPTS | NO-GO  
**Accepted risks:** ...  
**Owner of ship decision:** ...

## Next actions
1. ...
```

## Rules

- Prefer **testable** mitigations (“add idempotency key”) over “be careful”  
- Acceptance requires a named owner and review date  
- Proportionality: weekend prototype ≠ payments launch  
- Security/privacy on money or PII paths is never “skip silently”  

## Anti-patterns

- Infinite risk list, zero owners  
- Only eng risks  
- GO while score-9 risks are “TBD”  
- Risk theater that blocks all two-way-door learning  
