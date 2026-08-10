# Install imboss on Claude Code

**Goal:** one setup → your agent thinks like a CTO.

---

## One-command install (user-wide)

Runs for all projects on this machine:

```bash
git clone https://github.com/vmxmy/imboss.git ~/.claude/skills/imboss
```

Restart Claude Code (or open a new session). Done.

---

## Project-only install

Only this repo:

```bash
cd /path/to/your-product
mkdir -p .claude/skills
git clone https://github.com/vmxmy/imboss.git .claude/skills/imboss
```

Or symlink if you already cloned elsewhere:

```bash
ln -s ~/src/imboss .claude/skills/imboss
```

---

## Verify

In Claude Code, try:

```text
/ceo-mode 我们要不要现在上 Redis？
```

or:

```text
用 imboss 帮我决定：微信登录还是手机号登录
```

You should get: Situation → Business Impact → Options → Recommendation → Decision Needed  
— not a raw OAuth implementation dump.

---

## Update

```bash
cd ~/.claude/skills/imboss   # or your project path
git pull
```

---

## Uninstall

```bash
rm -rf ~/.claude/skills/imboss
# or: rm -rf .claude/skills/imboss
```

---

## Notes for non-technical founders

1. You do **not** need to read every file in the repo.  
2. After install, talk in **business language** (“提高注册转化”, “给老板汇报”).  
3. Use **`/ceo-mode`** whenever the agent gets too technical.  
4. Large builds: ask imboss to **plan + confirm** before coding agents implement.

More: [../README.md](../README.md) · [../SKILL.md](../SKILL.md)
