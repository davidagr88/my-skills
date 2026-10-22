# my-skills

My Claude Code skills, in one place.

## How it works
- Skills live in `.claude/skills/<skill-name>/SKILL.md`.
- Open this repo in Claude Code (desktop, web, or phone) and every skill here loads automatically.
- Run a skill by typing `/<skill-name>`, or just ask for the task and Claude picks the right skill.

## Add a skill from skills.sh
Ask Claude in a session on this repo:

> Run `npx skills add <owner/repo> --agent claude-code` (no `-g`), then commit and push.

Read the skill's `SKILL.md` and any `scripts/` folder before committing.

## Use these skills in another project
From that project: `npx skills add <your-github-user>/my-skills --agent claude-code`
