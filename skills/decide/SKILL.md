---
name: decide
description: >
  CTO decision framework for tech choice, architecture, build vs buy, refactor.
  Triggers: decide, 技术选型, build vs buy, should we refactor, architecture
  choice, pick a stack, 要不要上.
---

# decide

**Never** jump to a single technology as if it were inevitable.

Template: [templates/tech-decision.md](../../templates/tech-decision.md)

## Framework

### 1. Business Goal

What are we trying to achieve?

### 2. Constraints

- time  
- budget  
- team / agent capability  
- compliance / data  
- existing stack  

### 3. Options

At least **two** real options (often include “do nothing / later”).

### 4. Trade-offs

| Option | Cost | Speed | Risk | Fit to goal |
|--------|------|-------|------|-------------|
| A | | | | |
| B | | | | |

### 5. Recommendation

Choose **one**. Explain why. Name the sacrifice. State revisit trigger.

### 6. Decision Needed

Who must approve by when? Default if silent?

## When to use

- 技术选型  
- 架构选择  
- 买还是造  
- 是否重构  
- 大范围重写  

## Anti-patterns

- One real option + strawmen  
- “Industry standard” without our constraints  
- Infinite research as avoidance  
