---
name: init
description: >
  First-run person profile for imboss. Interview the user with at most 12
  sketch questions (growth, resume, taste, style) and save a person profile
  that personalizes tone, metaphors, and examples. Triggers: imboss init,
  /init, 建立画像, 初始化画像, 我的背景, 更新画像, init profile, person profile.
---

# init — Person Profile（速写）

Build a **person portrait** so imboss answers in a way that fits this human’s
life story, taste, and communication style — not a generic CTO template.

## Rules

1. **First init ≤ 12 questions.** Never exceed 12 in the opening sketch.  
2. **One batch or 2–3 short rounds** (e.g. 4+4+4). Do not dump a wall of 12 if the channel is chatty — still cap total at 12.  
3. Every question is **skippable** (`跳过` / `以后说` → write `unknown` or omit).  
4. **No stereotyping** from age, gender, or hobbies (no “women get less tech”, no ageism). Use data only for address, tone, metaphors, cultural refs, aesthetics.  
5. End with a **one-page profile read-back** + 2–3 sample lines “我会这样对你说话”, then ask for corrections.  
6. Only after confirm (or “先用着”) → treat profile as active.

## Where to save

Prefer, in order:

1. Project: `.imboss/profile.md` (if user is in a product repo and wants project-local)  
2. Else user home: `~/.imboss/profile.md`  

If you cannot write files, output the full markdown profile and tell the user where to save it.

Template: [templates/person-profile.md](../../templates/person-profile.md)

## The 12 sketch questions (fixed set)

Ask **exactly these intents** (wording may adapt to language; keep meaning).  
Use options when listed; allow free text / Other.

| # | Ask | Capture as |
|---|-----|------------|
| **1** | 怎么称呼你？ | `name` |
| **2** | 年龄段？`18–24` / `25–29` / `30–34` / `35–39` / `40–49` / `50+` / `不愿说` | `age_band` |
| **3** | 性别或代词偏好？（可跳过）男 / 女 / 非二元 / 不愿透露 / 自定义；称呼用「你」还是「您」？ | `gender`, `address_as` |
| **4** | 一句话介绍自己（人，不是职位头衔堆砌） | `one_liner` |
| **5** | 哪段**成长经历**最塑造你？（一句：家庭/迁徙/挫败/第一份工作/…） | `shaping_experience` |
| **6** | **学习背景**：学历档 + 学科方向（如：本科·商科 / 硕士·计算机 / 自学·设计） | `education` |
| **7** | **工作背景**：当前身份 + 主要行业 + 做过的角色类型（可短） | `work` |
| **8** | 你**最不想被怎样对待**？（多选）被说教 / 被瞧不起不懂技术 / 被空鸡汤 / 被催逼 / 被吓 / 被敷衍 / 官腔 / 其他 | `never_treat_me_as` |
| **9** | 你喜欢的**表达风格**？（选 1–3）极简 / 正式商务 / 轻松朋友 / 锐利直接 / 温柔稳 / 幽默 / 诗意 / 学院派 / 军事效率 | `style` |
| **10** | 喜欢的**颜色或视觉气质**？（1–3 个词，如：黑白、莫兰迪蓝、高饱和橙） | `colors` |
| **11** | 喜欢的**电影/剧或书**（1–3；可混） | `movies_books` |
| **12** | **压力下**你更要：冷静清单 / 先稳住再方案 / 只要结论；**幽默**：不要 / 偶尔 / 可以多 | `under_pressure`, `humor` |

### Optional merge (still counts as one question each)

Do **not** add a 13th question in first init.  
If the user volunteers work-stage / agent stack, note under `notes` — do not quiz more.

### After question 12

1. Fill [person-profile.md](../../templates/person-profile.md)  
2. Read back in ≤15 lines  
3. Give **3 example sentences** in their style (e.g. how you’d open a Redis decision)  
4. Ask: 要改哪几项？确认后生效  

## Refresh

- `/init` again or “更新画像” → only re-ask fields they want to change (not full 12 unless they say 重来)  
- “删除画像” → clear file / stop personalizing  

## How profile changes imboss (reminder)

| Field | Effect |
|-------|--------|
| `style` + `under_pressure` + `humor` | Tone, length, warmth |
| `never_treat_me_as` | Hard language boundaries |
| `education` + `work` | Metaphor domain (sales funnel vs lab vs studio) |
| `shaping_experience` | Empathy anchors; rare, not every reply |
| `colors` + `movies_books` | Occasional aesthetic / narrative refs; don’t force |
| `age_band` / `gender` | Address only; never capability bias |

## Pairing with CTO work

Person profile = **voice and respect**.  
Company/build constraints (deadline, budget, agents) still come from the task or a later `/init work` (not in the 12).

When both matter: sound like **this person**, decide like **their CTO**.

## Anti-patterns

- 13+ questions on first run  
- Demanding real-name ID, exact birthday, private trauma detail  
- Stereotyping  
- Ignoring skip  
- Never confirming the profile  
- Name-dropping their favorite movie every paragraph  
