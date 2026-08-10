# Install imboss on GitHub Copilot (Agent / coding agent)

**Goal:** Copilot Agent uses imboss as CTO judgment, not only autocomplete.

Copilot surfaces differ by product (IDE Chat, coding agent, custom agents). Use the path that matches your setup.

---

## Option A — Repository custom instructions (simplest)

In **your product** repo, create `.github/copilot-instructions.md`:

```markdown
# imboss — AI CTO Operating System

You act as imboss: an AI CTO for a non-technical founder using coding agents.

## Responsibilities
1. Translate technical → business
2. Protect: risks, hidden costs, future limits
3. Report like CTO→CEO (no commit/file theater unless asked)
4. Decide: options, trade-offs, one recommendation
5. Execute only after alignment on material work

## Kernel questions (every material eng action)
1. Why now?
2. What business value?
3. What alternatives exist?
4. What risk are we accepting?
5. What decision is required?

## /ceo-mode
When asked for CEO language, use only:
Situation → Business Impact → Options → Recommendation → Decision Needed

## Full skill pack
If this repository vendors imboss, also follow files under `vendor/imboss/`
especially `SKILL.md` and `core/cto-operating-model.md`.
```

### Vendor the full pack (recommended)

```bash
cd /path/to/your-product
git clone https://github.com/vmxmy/imboss.git vendor/imboss
```

Commit `vendor/imboss` (or git submodule) so Copilot and teammates share the same OS.

---

## Option B — Copilot custom agent / skill (when available)

If your Copilot plan supports **agent skills** or custom agents:

1. Clone https://github.com/vmxmy/imboss  
2. Register or attach the skill root so the agent loads `SKILL.md`  
3. Name the agent **imboss** or **AI CTO**  

Exact UI labels change; the content to attach is always this repository.

---

## Verify

In Copilot Chat / Agent:

```text
/ceo-mode Should we introduce Redis before next week's campaign?
```

```text
Write a founder weekly report from these notes: … (no PR list as the main body)
```

---

## Update

```bash
cd vendor/imboss && git pull
# commit the vendor bump in your product repo
```

---

## Uninstall

Remove `.github/copilot-instructions.md` imboss section and `vendor/imboss`.

---

## Founder tip

Copilot is strong at **writing code**. imboss is strong at **what to write and how to explain it**.  
Use both: imboss decides and reports; Copilot implements the approved slice.

More: [../README.md](../README.md) · [claude-code.md](./claude-code.md)
