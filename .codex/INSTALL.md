# Install humanize-doc for Codex

## Preferred

```bash
npx skills add gigio1023/humanize-doc@humanize-doc --agent codex
```

## Manual install

1. Clone the repo:

```bash
mkdir -p ~/.local/share
git clone https://github.com/gigio1023/humanize-doc.git ~/.local/share/humanize-doc
```

2. Copy the skill into Codex skills:

```bash
mkdir -p ~/.agents/skills
cp -R ~/.local/share/humanize-doc/humanize-doc ~/.agents/skills/
```

3. Restart Codex.
