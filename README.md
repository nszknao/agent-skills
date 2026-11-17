# agent-skills

Reusable AI agent skills for Codex, Claude Code, Cursor, Copilot, and more.

## Skills

| Skill | Description |
|---|---|
| [marp-slides](./skills/marp-slides/) | Marp Markdown slide creation with information design, layout, and CSS quality |
| [story-review](./skills/story-review/) | Review nonfiction content, structure, and clarity for its audience and purpose |

## Usage

Replace `<skill>` with a name from the table above.

### Codex

```text
$skill-installer Install <skill> from https://github.com/nszknao/agent-skills/tree/main/skills/<skill>
```

Invoke with `$<skill>`.

### Claude Code

```bash
/plugin marketplace add nszknao/agent-skills
/plugin install <skill>@nszknao-agent-skills
```

Invoke with `/<skill>:<skill>`.

### Other agents

Reference `skills/<skill>/SKILL.md` in your agent's instructions.
