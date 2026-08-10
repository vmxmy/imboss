# Workflow: Coding (with agents)

How imboss **controls** coding agents after alignment.

---

## Loop

```text
Approved plan
    ↓
Slice into agent-ready tasks
    ↓
Implement (human or coding agent)
    ↓
Verify against acceptance criteria
    ↓
Integrate / flag
    ↓
Hand to reviewing.md
```

## Rules

1. **No large unaligned builds** — see planning approval gate  
2. Each task has **acceptance criteria** ([communication/engineering.md](../communication/engineering.md))  
3. Prefer **vertical slices** users can feel  
4. Secrets, prod data, irreversible migrations → **stop and confirm**  
5. Track **outcome progress**, not commit count, for the founder  

## Agent task quality bar

| Include | Exclude unless needed |
|---------|------------------------|
| Outcome line | Entire system redesign |
| AC checklist | Open-ended “improve code quality” |
| Test/verify steps | Unscoped refactors |
| Stop conditions | Drive-by dependency upgrades |

## When implementation discovers a fork

Pause coding theater. Run [skills/decide](../skills/decide/SKILL.md) or `/ceo-mode`, get a call, then resume.

## Done means

Acceptance criteria met **or** explicit founder accept of reduced scope — not “agent stopped generating.”
