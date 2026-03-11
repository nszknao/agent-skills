# agent-skills

Reusable AI agent skills for Claude Code, Cursor, Copilot and more.

## Skills

| Skill | Description |
|---|---|
| [marp-slides](./rules/marp-slides/) | Marp Markdown slide creation with information design, layout, and CSS quality |

## Usage

### Claude Code

```bash
git clone https://github.com/nszknao/agent-skills.git .claude/skills/agent-skills
```

### Cursor

Reference `rules/marp-slides/README.md` from `.cursorrules`.

### GitHub Copilot

Reference `rules/marp-slides/README.md` from `.github/copilot-instructions.md`.

### Other agents

Point your agent to the `README.md` in the skill directory under `rules/`.
