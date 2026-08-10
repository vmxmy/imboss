# Example: Executive / founder weekly report

CTO → CEO language. Not a commit log.

Template: [templates/weekly-business-report.md](../templates/weekly-business-report.md)

---

## User

> 给老板汇报一下这周

### Raw notes (eng dump)

> merged 12 PRs, upgraded deps, refactored auth module, started dashboard widgets, talked about Redis, fixed flaky test, added Stripe webhook handler WIP…

---

## imboss output

# 项目进展报告 — 注册与付费 MVP — 2026-08-10

**状态：** 🟡 Yellow  
**一句话：** 付费主路径在测试环境已通；正式上线卡在“支付回调防重复”。

**周期：** 本周  
**读者：** 创始人 / 老板  

---

## Goal

Improve user activation after signup; this week’s focus is a **demoable paid loop**, not feature sprawl.

## Progress

**Completed**

- Staging: select plan → pay → unlock entitlement (test card demo)  
- Login session stability fix (internal testers no longer randomly logged out)  
- Registration flow + email verification experience improvements  

**In progress**

- Payment webhook idempotency (avoid double entitlement / wrong books) — ~80%  
- Admin dashboard: metric cards only; charts cut on purpose  

## Business Impact

- Investor/customer demo can tell a **money story**, not only Figma  
- Before live charges, accounting correctness risk remains — why status is Yellow  
- Dashboard delay does **not** block this week’s commercial validation  

## Risk

| 风险 | 等级 | 应对 | 负责人 |
|------|------|------|--------|
| 支付回调重复导致错账 | 🔴 | 上线前必须完成防重复；否则 NO-GO | 工程 |
| 正式密钥与演示环境混用 | 🟡 | 分环境；演示默认测试模式 | 创始人确认 |
| 第三方邮件投递策略未定 | 🟡 | 本周内选定供应商或暂缓扩量 | 创始人 |

## Next Step

1. Finish payment idempotency + replay drill  
2. Internal-only live flag for 48h  
3. Only then: dashboard charts / larger email experiment audience  

## Decision Needed

| 决策 | 选项 | 建议 | 需要谁 |
|------|------|------|--------|
| 本周五演示用测试支付还是真支付？ | 测试 / 真支付 | **测试支付** | 创始人 |
| 是否接受看板延后一周？ | 是 / 否 | **是** | 创始人 |
| 邮件实验是否扩大受众？ | 等初果 / 立刻扩大 | **等初果** | 创始人 |

---

## Contrast

| Eng dump | imboss report |
|----------|----------------|
| 12 PRs, refactor, deps | 付费闭环可演示 |
| Redis chat | 未进正文（无决策） |
| WIP webhook | 升级为 🔴 与上线门禁 |
| No ask | 明确 **Decision Needed** |

See: [skills/report](../skills/report/SKILL.md), [workflows/reporting.md](../workflows/reporting.md), [skills/ceo-mode](../skills/ceo-mode/SKILL.md).
