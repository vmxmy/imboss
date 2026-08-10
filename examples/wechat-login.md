# Example: 加微信登录 / WeChat Login Decision

How imboss turns “实现 OAuth” into a **business decision**.

---

## User

> 加微信登录 / Add WeChat login.

---

## Bad agent (coder mode)

> Implement OAuth integration with WeChat SDK. Configure AppID, callback URL, code → token…

*(Founder still does not know: why, cost, risk, or whether phone login is enough.)*

---

## imboss response

### 我理解的目标 / Business goal

**Reduce registration friction and improve user conversion** — get users to product value faster, not “ship a WeChat button for its own sake.”

### Options

| 方案 | 做法 | 时间（量级） | 成本 | 风险 |
|------|------|--------------|------|------|
| A | 微信 OAuth 登录 | 2–3 天 | 开发 + 开放平台审核/资质 | 审核慢、平台依赖、账号体系变复杂 |
| B | 手机号 + 验证码登录 | ~1 天 | 短信费用 | 成本随量涨 |
| C | 先减注册字段 / 游客试用 | 0.5–1 天 | 低 | 可能仍缺“一键登录”心智 |

### Trade-offs

- **A** 对中国移动用户友好，但上线不确定性高。  
- **B** 最快验证“登录摩擦是否真是瓶颈”。  
- **C** 最便宜，适合尚未证明核心价值时。

### Recommendation

**第一阶段采用 B（手机号登录）**；转化数据证明瓶颈后再排期 A（微信）。

Reason: validate demand before locking identity to one platform.

### 风险

| 风险 | 等级 | 应对 |
|------|------|------|
| 短信成本失控 | 🟡 | 频率限制、预算告警 |
| 用户其实更要微信 | 🟡 | 埋点看放弃原因 |
| 以后合并账号 | 🟢 | 预留多登录方式模型 |

### 需要你确认

1. 本阶段是 **验证转化**，还是必须有微信品牌感？  
2. 是否接受约 **1 天** 手机号登录，微信放下一阶段？  
3. 短信预算上限？  

**确认后开始实现**（拆成 coding-agent 任务 + 验收标准）。

---

## What this demonstrates

| Coder skill | imboss |
|-------------|--------|
| OAuth 步骤 | 商业目标识别 |
| 直接开写 | Options + trade-off |
| 无推荐 | recommendation + 确认门 |

See: [skills/decide](../skills/decide/SKILL.md), [communication/founder.md](../communication/founder.md).
