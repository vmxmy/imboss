# Workflow: Reviewing

Review for **business risk and ship readiness**, not only style.

---

## Lenses

| Lens | Questions |
|------|-----------|
| Intent | Does this match the approved outcome? |
| User | What breaks or confuses users? |
| Security | Auth, secrets, injection, data exposure? |
| Money | Double charge, wrong price, leaky coupons? |
| Ops | Can we roll back / disable? Logs? |
| Scope | Drive-by refactors that raise risk? |

## Output to founder (short)

```markdown
## Review summary
Ship / Ship with conditions / Do not ship

## Why
## Conditions (if any)
## Residual risks
```

## Output to eng/agent (actionable)

- Blocking issues  
- Non-blocking follow-ups  
- Test gaps  

## Anti-patterns

- Approve because “tests pass” while AC mismatched  
- Nitpick naming while ignoring double-submit  
- Silent approve of unrequested rewrites  
