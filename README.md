# imboss

**The AI CTO Operating System for Non-Technical Builders**

> Empower agent coding with business communication, technical translation, risk management, and executive reporting.

`imboss` is not a single prompt. It is a **unified personality and operating layer** that turns coding agents into an AI CTO — someone who can ship code *and* speak founder, board, and team language.

---

## Why imboss

Most agent skills optimize for **writing code**. Non-technical builders need more:

| Gap | What imboss fills |
|-----|-------------------|
| Tech ↔ business | Translate PRDs, tickets, and architecture into plain language |
| Decision quality | Force options, tradeoffs, recommendation, and residual risk |
| Risk blindness | Surface security, delivery, and product risks before they explode |
| Reporting chaos | Weekly, executive, and incident reports that busy people can scan |
| Vague asks | Turn fuzzy founder intent into crisp agent-ready requests |

If Claude Code / Cursor / Codex / Copilot write the code, **imboss owns the judgment layer**.

---

## What it is

A portable **Agent Skill pack** you can drop into:

- **Claude Code** — project or user skills
- **Cursor** — rules / skills
- **Codex** — instructions / skills
- **GitHub Copilot** — agent skills
- Any agent that loads markdown skill files

Same voice. Same decision framework. Same report templates.

---

## Quick start

### 1. Clone

```bash
git clone https://github.com/<you>/imboss.git
```

### 2. Install into your agent

**Claude Code** (example):

```bash
# Project-scoped
cp -r imboss/.claude-skills/* .claude/skills/   # or map SKILL.md paths as you prefer

# Or symlink the whole skill tree
ln -s /path/to/imboss ~/.claude/skills/imboss
```

**Cursor / Codex / Copilot**: point rules or skill roots at this repo (or copy `SKILL.md` + `skills/*`).

### 3. Invoke

Natural language triggers work well:

- “用 imboss 帮我规划这周工程重点”
- “imboss: explain this architecture to a non-tech cofounder”
- “Write an executive summary of what we shipped”
- “Turn this founder request into a technical ticket”
- “Risk-check this launch plan”

Or call a sub-skill directly: `imboss-plan`, `imboss-report`, `imboss-explain`, `imboss-request`, `imboss-risk`.

---

## Repository layout

```
imboss/
├── README.md
├── LICENSE
├── SKILL.md                    # Root skill — AI CTO persona + routing
├── principles.md               # Operating principles
├── communication.md            # How imboss speaks
├── reporting.md                # Reporting doctrine
├── decision-framework.md       # How decisions get made
├── risk-management.md          # Risk taxonomy & process
├── technical-translation.md    # Business ↔ tech translation
│
├── skills/
│   ├── imboss-plan/            # Plan work like a CTO
│   ├── imboss-report/          # Weekly / exec / incident reports
│   ├── imboss-explain/         # Explain tech to non-tech
│   ├── imboss-request/         # Crisp tickets & RFCs from intent
│   └── imboss-risk/            # Risk review & mitigation
│
├── templates/
│   ├── weekly-report.md
│   ├── executive-summary.md
│   ├── decision-request.md
│   ├── incident-report.md
│   └── roadmap.md
│
└── examples/
    ├── before-after.md
    ├── founder-mode.md
    └── manager-report.md
```

---

## Core modules

| File | Role |
|------|------|
| [SKILL.md](./SKILL.md) | Persona, when to use, sub-skill routing |
| [principles.md](./principles.md) | Non-negotiables of the AI CTO |
| [communication.md](./communication.md) | Tone, structure, audience modes |
| [reporting.md](./reporting.md) | What good reporting looks like |
| [decision-framework.md](./decision-framework.md) | Options → tradeoffs → decide |
| [risk-management.md](./risk-management.md) | Identify, score, mitigate, accept |
| [technical-translation.md](./technical-translation.md) | Jargon out, business in |

---

## Sub-skills

| Skill | Intent |
|-------|--------|
| `imboss-plan` | Prioritize, sequence, estimate, and de-risk a plan |
| `imboss-report` | Weekly, executive, or incident report from raw notes |
| `imboss-explain` | Explain technical topics to founders / PMs / board |
| `imboss-request` | Convert fuzzy asks into agent-ready specs |
| `imboss-risk` | Pre-mortem, launch review, security/delivery risk |

---

## Design principles (preview)

1. **Business outcome first** — code is a means, not the headline.
2. **One recommendation** — options are fine; fence-sitting is not.
3. **Risks are first-class** — never bury them under “next steps”.
4. **Audience-aware** — founder, eng, board get different altitudes.
5. **Actionable defaults** — every doc ends with owners and next moves.
6. **No theater** — no fake certainty, no status padding, no jargon for status.

Full list: [principles.md](./principles.md).

---

## Positioning

```
imboss — The AI CTO Operating System for Non-Technical Builders
```

Not “another coding skill”. A **judgment and communication OS** that sits on top of coding agents so non-technical builders can run product engineering with executive clarity.

---

## Version

**v0.1** — first public skill pack (docs, sub-skills, templates, examples).

---

## License

[MIT](./LICENSE)

---

## Contributing

PRs welcome for templates, examples, and agent-specific install notes. Keep the persona sharp: **AI CTO, not AI intern**.
