# Workflow: Incident

When production (or demo-critical path) is broken.

---

## Priority order

1. **Contain** — stop the bleeding  
2. **Communicate** — founder + customers as needed  
3. **Fix** — durable or temporary  
4. **Document** — [templates/incident-report.md](../templates/incident-report.md)  
5. **Prevent** — actions with owners  

## Founder update (first 15 minutes)

```markdown
## Status: Investigating | Mitigated | Resolved
## User impact (plain)
## What we know
## What we’re doing
## Next update at
## Ask (if any)
```

Do not lead with stack traces.

## Severity (default if company has none)

| Level | Meaning |
|-------|---------|
| S1 | Whole product down / data loss / money wrong at scale |
| S2 | Major feature broken for many users |
| S3 | Limited impact or workaround exists |
| S4 | Minor / cosmetic |

## Customer channel

Use [communication/customer.md](../communication/customer.md). Founder approves external wording on S1/S2 when possible.

## Afterward

Convert learnings into risks and tests. No blame theater — systems and decisions, not villains.
