# Claude Code Skills

A collection of reusable [skills](https://docs.anthropic.com/en/docs/claude-code/skills) for [Claude Code](https://docs.anthropic.com/en/docs/claude-code/overview) — Anthropic's official CLI for Claude.

## What are skills?

Skills are markdown files that teach Claude Code how to handle specific types of tasks. They act as specialized knowledge modules that activate based on trigger words or context.

## Available Skills

| Skill | Description |
|-------|-------------|
| [strategy-mindset](./skills/strategy-mindset/) | Strategic thinking discipline — warm but acid, evidence-based. Grounded in Rumelt, Martin, and Helmer. Includes onboarding, weekly review system, scoreboard, decision journal, and strategy versioning. |
| [edu-prompt-best-practices](./skills/edu-prompt-best-practices/) | Best practices for designing AI tutor prompts. Based on research from Khanmigo, ChatGPT Study Mode, Google LearnLM, Claude, and academic papers. |

## Installation

### Option 1: Copy individual skills

1. Copy the skill folder (e.g., `skills/strategy-mindset/`) into your `~/.claude/skills/` directory
2. That's it — Claude Code will pick it up automatically

### Option 2: Clone the full repo

```bash
git clone https://github.com/profesorj13/skills.git ~/.claude/skills-community
```

Then symlink the skills you want:

```bash
ln -s ~/.claude/skills-community/skills/strategy-mindset ~/.claude/skills/strategy-mindset
ln -s ~/.claude/skills-community/skills/edu-prompt-best-practices ~/.claude/skills/edu-prompt-best-practices
```

## Portable Prompts (no Claude Code required)

Don't use Claude Code? You can still use these frameworks as copy-paste prompts in any AI assistant:

- **[Strategy Advisor Prompt](https://profesorj13.github.io/prompts/strategy-advisor.html)** — A self-contained prompt that turns any AI into a Rumelt/Martin/Helmer strategy advisor. Just copy, paste, and go.

Visit **[profesorj13.github.io](https://profesorj13.github.io)** for all available prompts.

## Contributing

PRs welcome. Each skill should:

- Have a `SKILL.md` with proper frontmatter (name, description)
- Include a clear description of when/how it triggers
- Be self-contained (reference files go in a `references/` subfolder)
- Be generic enough to be useful beyond a single project

## License

MIT
