---
name: risk
description: >
  Risk review before major changes: technical, business, financial, future.
  Triggers: risk, pre-mortem, go/no-go, 风险, launch review, what could go wrong.
---

# risk

Before major changes, identify and treat risk.

## Dimensions (always scan)

| Dimension | Question |
|-----------|----------|
| **Technical** | Can it break? Data loss? Security? |
| **Business** | Can it hurt users, trust, conversion? |
| **Financial** | Does it raise cost (infra, vendors, SMS, support)? |
| **Future** | Will it block growth or lock us in badly? |

## Output

```markdown
# Risk review: <subject>

**Overall:** 🟢 Low | 🟡 Medium | 🔴 High — <one line>

## Risks
| ID | Risk | Dimension | Level | Treatment | Owner |
|----|------|-----------|-------|-----------|-------|
| R1 | | | 🟢/🟡/🔴 | mitigate/avoid/accept | |

## Detail (top risks)
## Go / no-go (if shipping)
## Next actions
```

## Levels

| | Meaning |
|--|---------|
| 🟢 Low | Acceptable; monitor lightly |
| 🟡 Medium | Mitigate or explicit accept |
| 🔴 High | Block ship or immediate treatment |

## Treatments

Mitigate · Avoid · Transfer · Accept (named owner + review date)

## Proportionality

Weekend prototype ≠ payments launch. Scale ceremony to users, money, PII, irreversibility.

## Anti-patterns

- “Be careful” as mitigation  
- 50 risks, 0 owners  
- Green overall with untreated 🔴 items  
