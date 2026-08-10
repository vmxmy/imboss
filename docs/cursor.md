# Install imboss on Cursor

**Goal:** Cursor Agent / rules load imboss as your AI CTO layer.

---

## Option A — Project Rules (recommended for a product repo)

### 1. Clone once

```bash
git clone https://github.com/vmxmy/imboss.git ~/imboss
```

### 2. Point the project at imboss

Create or edit `.cursor/rules/imboss.mdc` in **your product** repo:

```markdown
---
description: imboss AI CTO Operating System — technical leadership for non-technical builders
globs:
alwaysApply: true
---

# imboss

You operate as **imboss** (AI CTO). Read and follow:

@~/imboss/SKILL.md

When material engineering work is proposed, apply the five questions in:

@~/imboss/core/cto-operating-model.md

For CEO language, use `/ceo-mode` structure from:

@~/imboss/skills/ceo-mode/SKILL.md
@~/imboss/communication/executive.md

Never lead status with commits/files unless asked. Lead with goals, value, risk, decision.
```

If `@~/imboss/...` paths do not resolve in your Cursor version, paste the contents of `SKILL.md` into the rule body, or copy the skill pack into the project:

```bash
cp -R ~/imboss .cursor/imboss
# then reference @.cursor/imboss/SKILL.md in the rule
```

### 3. Restart Cursor chat / Agent

---

## Option B — One-folder copy into project

```bash
cd /path/to/your-product
git clone https://github.com/vmxmy/imboss.git .cursor/imboss
```

Add `.cursor/rules/imboss.mdc` with `alwaysApply: true` and:

```markdown
Follow .cursor/imboss/SKILL.md as your AI CTO operating system.
```

---

## Verify

In Agent chat:

```text
/ceo-mode Should we add Redis before the launch next week?
```

Expect a decision brief, not only infra code.

---

## Update

```bash
cd ~/imboss && git pull
# or: cd .cursor/imboss && git pull
```

---

## Uninstall

Delete `.cursor/rules/imboss.mdc` and any copied `.cursor/imboss` folder.

---

## Founder tip

Keep **one product repo** + imboss as rules. Talk outcomes (“demo by Friday”, “cut scope”). Use imboss for plan/report; let Cursor Agent implement only after you confirm the recommendation.

More: [../README.md](../README.md)
