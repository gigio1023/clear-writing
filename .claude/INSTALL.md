# Install humanize-doc for Claude Code

## Preferred

```bash
npx skills add gigio1023/humanize-doc@humanize-doc --agent claude-code
```

## Manual install

```bash
git clone https://github.com/gigio1023/humanize-doc.git ~/.claude/humanize-doc
mkdir -p ~/.claude/skills
cp -R ~/.claude/humanize-doc/humanize-doc ~/.claude/skills/
```

Claude Code normally detects `SKILL.md` changes live. Restart only if the new
top-level skills directory was created after the session started or the skill
does not appear.
