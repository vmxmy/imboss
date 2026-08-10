# imboss — AI CTO Operating System

**A technical leadership skill for non-technical builders using AI coding agents.**

中文：**面向 AI 原生创业者和非技术开发者的 AI CTO 操作系统。**

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](./LICENSE)
[![Version](https://img.shields.io/badge/version-0.1-blue.svg)](./CHANGELOG.md)

---

## Why imboss

Traditional software org:

```text
CEO
 │
CTO
 │
Engineering Team
 │
Code
```

AI-native org:

```text
CEO / Founder
 │
imboss Agent
 │
Coding Agents
 │
Code
```

**imboss is not:**

- a programmer  
- a PM  
- a secretary  
- a commit summarizer  

**imboss is:**

> a business-aware **CTO** — so a non-technical founder can run technical delivery through coding agents.

---

## What you get

| Responsibility | Meaning |
|----------------|---------|
| **Translate** | Technical → business language a founder can use |
| **Protect** | Risks, hidden costs, future locks |
| **Report** | CEO-grade progress (not file/commit dumps) |
| **Decide** | Options, trade-offs, one recommendation |
| **Execute** | Align → plan → coding agents → review → business report |

### Killer feature: `/ceo-mode`

Turn **any** technical thread into language a CEO can **understand and decide**:

```text
Situation → Business Impact → Options → Recommendation → Decision Needed
```

This is the sharpest difference between imboss and a generic coding skill.

---

## Quick start

### Install (Claude Code example)

```bash
git clone https://github.com/vmxmy/imboss.git
# Project skill
mkdir -p .claude/skills
ln -s /path/to/imboss .claude/skills/imboss
# or copy the repo into your skills directory
```

Cursor / Codex / Copilot: point rules or agent skills at this repo’s `SKILL.md` (and optional sub-skills under `skills/`).

### Invoke

```text
/ceo-mode 我们要不要上 Kubernetes？
imboss: 给老板写本周进展
帮我决策：微信登录 vs 手机号登录
上线前做一次 risk review
```

---

## Repository layout

```text
imboss/
├── README.md
├── SKILL.md                 # Agent entry
├── CHANGELOG.md
├── LICENSE
│
├── core/                    # Identity, principles, mindset, boundaries
├── communication/           # Executive / founder / eng / customer
├── workflows/               # Plan → code → review → release → incident → report
├── skills/                  # explain, report, decide, risk, negotiate, ceo-mode
└── templates/               # Business artifacts
```

Not a single mega-prompt: a **layered operating system** the agent loads by task.

---

## Example

**User:** 加微信登录  

**imboss:**

```text
我理解你的目标：减少注册流失，提高新用户转化。

方案1：微信 OAuth 登录
- 时间：2–3 天
- 风险：依赖微信平台与审核

方案2：手机号登录
- 时间：约 1 天
- 风险：短信成本

建议：第一阶段用手机号登录——更快验证商业价值；微信登录作为下一阶段。

确认后我开始实现。
```

More patterns live in skill files and templates.

---

## Roadmap

| Version | Focus |
|---------|--------|
| **v0.1** (now) | CTO personality: translate, report, decide, risk, `/ceo-mode` |
| **v0.2** | Project mgmt, budget, tech-debt ledger, hiring assist |
| **v0.3** | Multi-agent org (frontend / backend / QA / DevOps under imboss) |

---

## Design principles (preview)

1. Outcome over activity  
2. One recommendation  
3. Risks are first-class  
4. Audience-aware altitude  
5. No theater, no false ease  
6. Align before large agent coding  

Full text: [core/principles.md](./core/principles.md) · [core/boundaries.md](./core/boundaries.md)

---

## License

[MIT](./LICENSE)

---

## Contributing

PRs welcome for templates, workflow clarity, and agent-host install notes.  
Keep the bar: **AI CTO, not AI intern.**
