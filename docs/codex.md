# Install imboss on Codex (OpenAI)

**Goal:** Codex follows imboss as the technical leadership layer above code generation.

---

## Option A — Project instructions (recommended)

### 1. Clone

```bash
git clone https://github.com/vmxmy/imboss.git ~/imboss
```

### 2. Add to your product repo

Create `AGENTS.md` (or append if it exists) at the project root:

```markdown
# imboss — AI CTO

You are the AI CTO for a non-technical founder. Follow the imboss operating system:

1. Read and obey: `~/imboss/SKILL.md` (or `./vendor/imboss/SKILL.md` if vendored).
2. Before large implementation, answer the five questions in `core/cto-operating-model.md`.
3. Prefer CEO language: Situation → Business Impact → Options → Recommendation → Decision Needed.
4. Do not lead status with commits/files unless asked.
5. Sub-skills live under `skills/` (ceo-mode, decide, risk, report, explain, negotiate).

When the user says `/ceo-mode`, force executive structure only.
```

### 3. Vendor into the repo (portable for CI / other machines)

```bash
cd /path/to/your-product
git clone https://github.com/vmxmy/imboss.git vendor/imboss
# add vendor/imboss to git, or use submodule
```

Point `AGENTS.md` at `./vendor/imboss/SKILL.md`.

---

## Option B — Global personal instructions

If your Codex setup supports a global instruction file, paste a short pointer:

```text
Default technical leadership persona: imboss.
Skill root: /Users/<you>/imboss
Always load SKILL.md; use /ceo-mode for executive decisions.
```

(Exact global path depends on your Codex client version.)

---

## Verify

```text
/ceo-mode 微信登录还是手机号登录？
```

or:

```text
imboss report: summarize this week for my cofounder (no commit list)
```

---

## Update

```bash
cd ~/imboss && git pull
# or: cd vendor/imboss && git pull
```

---

## Uninstall

Remove imboss sections from `AGENTS.md` and delete `vendor/imboss` if present.

More: [../README.md](../README.md) · [../core/cto-operating-model.md](../core/cto-operating-model.md)
