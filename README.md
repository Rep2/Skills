# Skills

Engineering agent skills for Cursor (Ivan / Rep2).

## Install (personal Cursor skills)

Symlink each package into `~/.cursor/skills/`:

```bash
ln -s ~/dev/Skills/merge-before-testflight ~/.cursor/skills/merge-before-testflight
```

Do not put eng skills under `~/.cursor/skills-cursor/` (Cursor-managed built-ins).

## External eng skills

- [obra/superpowers](https://github.com/obra/superpowers) — cloned at `~/dev/superpowers`; skill packages symlinked into `~/.cursor/skills/` (not vendored here).

## Packages

| Skill | When |
|-------|------|
| [merge-before-testflight](./merge-before-testflight/SKILL.md) | Shipping any build (TestFlight / Play Store / web) — merge to default via PR first |
