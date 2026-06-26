# Project log

## 2026-06-26

Objectif: adapter pour Codex l'article Substack de Hannah Stulberg sur la status line Claude Code.

Contexte local:

- Dossier: `C:\Users\ciram\OneDrive\Documents\statusline`
- Depot Git existant, sans commit initial au moment de l'inspection.
- `gh` disponible: version 2.93.0.
- `codex` disponible: `codex-cli 0.137.0`.

Sources consultees:

- Article source: `https://hannahstulberg.substack.com/p/claude-code-for-everything-your-status-line-is-empty`
- Manuel Codex officiel recupere le 2026-06-26: `https://developers.openai.com/codex/codex-manual.md`

Constat:

- Claude Code permet une status line extensible via `~/.claude/settings.json`, avec une recommandation Windows d'utiliser un script Node.js `~/.claude/statusline.js`.
- Codex documente une configuration native via `/statusline` et `status_line` dans `~/.codex/config.toml`.
- Le manuel Codex ne documente pas, dans les sections consultees, un segment `status_line` custom execute par script arbitraire.

Livrables crees:

- `README.md`
- `AGENTS.md`
- `.gitignore`
- `.codex/config.statusline.example.toml`
- `docs/codex-statusline-adaptation.md`
- `docs/decisions.md`

Verification prevue:

```powershell
rg -n "status_line|/statusline|config.toml" .
git status --short
```
