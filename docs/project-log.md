# Project log

## 2026-06-26

Objectif: adapter pour Codex l'article Substack de Hannah Stulberg sur la status line Claude Code.

Contexte local:

- Dossier: `~/OneDrive/Documents/statusline`
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

## 2026-06-26, publication du skill corrige

Objectif: publier publiquement les corrections locales du skill `youtube-transcript-pdf`.

Source du skill:

- Depot: `https://github.com/aniketpanjwani/skills`
- Chemin: `skills/general/youtube-transcript-pdf`
- Licence: MIT, copyright Aniket Panjwani

Corrections integrees dans `skills/youtube-transcript-pdf`:

- detection Chrome/Edge sous Windows;
- lecture et ecriture UTF-8 pour JSON, TXT, Markdown, HTML et audits;
- prompts `codex exec` envoyes en bytes UTF-8;
- normalisation du tiret long dans les titres YouTube;
- adaptation des libelles de PDF pour les captions francaises;
- desactivation des intertitres anglais automatiques pour les captions francaises.

Exclusions volontaires:

- `youtube-transcripts/`
- `youtube-transcripts-fr/`
- caches Python `__pycache__` et `*.pyc`
