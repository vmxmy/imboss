# Install imboss

**One setup → your AI agent becomes a CTO.**

Pick your host:

| Host | Guide | Fastest path |
|------|--------|--------------|
| **Claude Code** | [claude-code.md](./claude-code.md) | `git clone … ~/.claude/skills/imboss` |
| **Cursor** | [cursor.md](./cursor.md) | Rule + clone / copy skill pack |
| **Codex** | [codex.md](./codex.md) | `AGENTS.md` + vendor clone |
| **GitHub Copilot** | [github-copilot.md](./github-copilot.md) | `.github/copilot-instructions.md` + vendor |

## After install — try this

```text
/ceo-mode 我们要不要现在上 Redis？
```

```text
给老板写本周进展（不要列 commit）
```

```text
帮我决策：微信登录 vs 手机号登录
```

## What “installed” means

The agent loads [SKILL.md](../SKILL.md) and can pull:

- [core/cto-operating-model.md](../core/cto-operating-model.md)  
- [skills/ceo-mode](../skills/ceo-mode/SKILL.md)  
- communication / workflows / templates / examples  

You do **not** need to be a programmer to use it — talk in business outcomes.

## Update

Wherever you cloned imboss:

```bash
git pull
```
