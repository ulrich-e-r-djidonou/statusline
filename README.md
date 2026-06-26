# Codex status line

Adaptation Codex de l'article de Hannah Stulberg sur la status line de Claude Code.

Source de depart: [Claude Code for Everything: Your Status Line Is Empty](https://hannahstulberg.substack.com/p/claude-code-for-everything-your-status-line-is-empty).

Ce depot contient aussi une copie corrigee du skill Codex [`youtube-transcript-pdf`](skills/youtube-transcript-pdf/SKILL.md), issue du depot public [aniketpanjwani/skills](https://github.com/aniketpanjwani/skills), sous licence MIT. Les corrections locales ciblent Windows, UTF-8, Chrome/Edge, et l'adaptation des libelles de PDF selon la langue.

## Ce que Codex supporte nativement

Codex n'utilise pas le meme modele que Claude Code pour cette fonction. Cote Codex, la status line du terminal se configure avec la commande interactive `/statusline` ou avec la cle `status_line` dans `~/.codex/config.toml`.

Selon le manuel Codex consulte le 2026-06-26, la valeur par defaut est:

```toml
status_line = ["model-with-reasoning", "context-remaining", "current-dir"]
```

Un point de depart plus proche de l'article est:

```toml
status_line = ["model", "context-remaining", "git-branch"]
```

## Installation manuelle

1. Ouvrir Codex CLI.
2. Taper `/statusline`.
3. Choisir et ordonner les champs utiles: modele, contexte restant, branche Git, tokens, limites, session.
4. Laisser Codex persister la configuration dans `~/.codex/config.toml`.

Alternative par fichier:

1. Ouvrir `~/.codex/config.toml`.
2. Copier une ligne `status_line` depuis [.codex/config.statusline.example.toml](.codex/config.statusline.example.toml).
3. Relancer Codex CLI si la session en cours ne reflete pas le changement.

## Limite importante

L'article montre une status line Claude Code extensible par script, avec Gmail, calendrier, meteo, PR GitHub et autres donnees externes. Je n'ai pas trouve dans le manuel Codex un equivalent documente permettant d'ajouter directement des segments custom arbitraires dans `status_line`.

Pour Codex, l'adaptation fiable est donc:

- utiliser `/statusline` pour les segments integres;
- utiliser `/status` et `/usage` pour les details ponctuels;
- traiter Gmail, calendrier, meteo et GitHub comme des workflows separes via connecteurs, MCP, automatisations ou scripts de shell, pas comme une status line native tant que Codex ne documente pas de segment custom.

## Fichiers

- [.codex/config.statusline.example.toml](.codex/config.statusline.example.toml): snippets a copier dans `~/.codex/config.toml`.
- [docs/codex-statusline-adaptation.md](docs/codex-statusline-adaptation.md): mapping Claude Code vers Codex.
- [docs/project-log.md](docs/project-log.md): trace de travail et sources consultees.
- [docs/decisions.md](docs/decisions.md): decisions de configuration.
- [skills/youtube-transcript-pdf/SKILL.md](skills/youtube-transcript-pdf/SKILL.md): skill YouTube transcript PDF corrige pour Windows et francais.
- [THIRD_PARTY_LICENSES/aniketpanjwani-skills-MIT.txt](THIRD_PARTY_LICENSES/aniketpanjwani-skills-MIT.txt): licence MIT du depot source.
