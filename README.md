# Vibe Coder's Checklist

You vibe coded your app. Did you add CI/CD? Back up your database? Set a spend cap on your LLM API?

This is a Claude skill that audits your app for the production basics people skip before launch. Claude looks at your actual code and config, marks each item Done, Missing, or Can't verify, and puts the high-risk stuff (money, data loss, leaked secrets) first.

## How to use it

**Claude Code:** copy the `vibe-code-launch-check` folder into `~/.claude/skills/` (or `.claude/skills/` in your project). Then ask Claude "is my app ready to launch?"

**Claude.ai:** zip the `vibe-code-launch-check` folder and upload it as a skill.

**Anything else:** paste the contents of `SKILL.md` into your prompt.

## What it checks

High risk, testing and deploys, monitoring, infrastructure, AI-specific checks (only if your app calls a model), users and legal, and polish. The full list is in [`vibe-code-launch-check/SKILL.md`](vibe-code-launch-check/SKILL.md).

## License

Apache 2.0
