# my-skills

My Claude Code skills, in one place, packaged as a Claude Code plugin.

## How it works
- Skills live in `skills/<skill-name>/SKILL.md`.
- The repo is both a plugin (`.claude-plugin/plugin.json`) and a marketplace (`.claude-plugin/marketplace.json`).
- Skills run with a `my-skills:` prefix, for example `/my-skills:ui-ux-pro-max`, or just ask for the task and Claude picks the right skill.
- The repo is public, so any session can install the plugin, including cloud sessions on other repos. Keep secrets out of it.

## Use these skills in a project
Commit this as `.claude/settings.json` in the project (merge it if the file already exists):

```json
{
  "extraKnownMarketplaces": {
    "my-skills": {
      "source": { "source": "github", "repo": "davidagr88/my-skills" }
    }
  },
  "enabledPlugins": {
    "my-skills@my-skills": true
  }
}
```

Every session on that project, including cloud sessions, then loads the skills. Changes pushed here reach every project.

To install it by hand instead:

```
/plugin install my-skills --marketplace davidagr88/my-skills
```

Skills that only matter to one project go in that project's own `.claude/skills/`.

## Add a skill from skills.sh
Ask Claude in a session on this repo:

> Run `npx skills add <owner/repo> --agent claude-code` (no `-g`), move the new folder from `.claude/skills/` to `skills/`, then commit and push.

Read the skill's `SKILL.md` and any `scripts/` folder before committing. If the `SKILL.md` calls its scripts by a `.claude/skills/<name>/...` path, change it to `${CLAUDE_SKILL_DIR}/...` so it works once installed.

After changing skills, bump `version` in `.claude-plugin/plugin.json` so projects pick up the update.
