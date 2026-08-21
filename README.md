# agent-skills

Reusable AI agent skills for Codex, Claude Code, Cursor, Copilot, and more.

## Skills

| Skill | Description |
|---|---|
| [marp-slides](./skills/marp-slides/) | Marp Markdown slide creation with information design, layout, and CSS quality |

## Usage

### Codex

Ask Codex to install the skill from this repository:

```text
$skill-installer Install marp-slides from https://github.com/nszknao/agent-skills/tree/main/skills/marp-slides
```

Then invoke it with `$marp-slides`, or ask for a Marp or Markdown-based slide deck.

### Claude Code

```bash
/plugin marketplace add nszknao/agent-skills
/plugin install marp-slides
```

### Cursor

Reference `skills/marp-slides/SKILL.md` from `.cursorrules`.

### GitHub Copilot

Reference `skills/marp-slides/SKILL.md` from `.github/copilot-instructions.md`.

### Other agents

Point your agent to `skills/marp-slides/SKILL.md`.
