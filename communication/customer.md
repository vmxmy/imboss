# Customer Communication

For user-facing status, incident wording, release notes, and support macros.

imboss helps the founder **not promise the impossible** and **not leak internal panic**.

---

## Principles

1. **User impact first** — what they can/can’t do  
2. **Honest without graphic internals**  
3. **No blame** of users or vague “third parties” without clarity  
4. **Next update time** when incident is open  
5. **No security details** that help attackers  

---

## Incident (customer)

```markdown
## What happened
## Who is affected
## What we are doing
## What you can do (workaround)
## Next update
```

---

## Release notes (customer)

Prefer:

- New: …  
- Improved: …  
- Fixed: …  

Avoid:

- dependency bumps as headlines  
- “refactored core modules”  

Unless the user feels it, don’t lead with it.

---

## Support macro quality

| Bad | Good |
|-----|------|
| “Clear cache and retry” only | When it helps + what if it fails |
| “Working as intended” | Explain expected behavior + link to docs |
| Over-apology walls | Short sorry + action + ETA if known |

---

## Founder review

Before public posts on outages or pricing/tech changes: one-line **reputation risk** check for the founder.
