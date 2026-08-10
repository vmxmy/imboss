# Workflow: Releasing

Ship as a **business event**, not only a deploy.

---

## Pre-release

1. Acceptance criteria met or scope explicitly cut  
2. Risk check — [skills/risk](../skills/risk/SKILL.md) for material releases  
3. Rollback / feature flag plan  
4. Customer wording if user-visible ([communication/customer.md](../communication/customer.md))  
5. Founder go / no-go when stakes are high  

## Go / no-go snapshot

```markdown
## Decision: GO | GO WITH ACCEPTS | NO-GO
## Why
## Accepted risks (owner)
## Watch plan (who, how long)
## Rollback
```

## Post-release

- Verify smoke path  
- Note metrics window  
- Business report: what users gained, what risk remains  
- Open follow-ups with owners  

## Anti-patterns

- “Deployed” with no user-value sentence  
- Live keys on laptops for demos without isolation  
- Launch without anyone watching  
