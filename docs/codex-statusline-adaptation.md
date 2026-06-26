# Codex status line adaptation

## Resume

L'article source explique comment transformer la status line Claude Code en tableau de bord de terminal: dossier courant, modele, contexte, cout ou usage, branche Git, Gmail, calendrier, meteo et autres sources externes.

L'adaptation Codex doit etre plus stricte. Codex documente une status line configurable, mais par liste d'elements integres dans `config.toml`, pas par commande shell arbitraire equivalent a `~/.claude/statusline.js`.

## Mapping pratique

| Besoin dans l'article Claude Code | Adaptation Codex fiable |
|---|---|
| Dossier courant | Element integre `current-dir`, present dans la configuration par defaut. |
| Modele actif | Element integre `model` ou `model-with-reasoning`. |
| Contexte restant | Element integre `context-remaining`. |
| Branche Git | Element integre `git-branch`. |
| Tokens, limites, session | Utiliser `/statusline` pour voir les elements disponibles dans la version locale. Utiliser aussi `/status` et `/usage` pour inspection ponctuelle. |
| Gmail, calendrier, meteo, scores, PR GitHub | Pas d'equivalent `status_line` custom documente. A traiter via connecteurs, MCP, automatisations ou scripts externes. |

## Configuration recommandee

Point de depart:

```toml
status_line = ["model", "context-remaining", "git-branch"]
```

Version Codex par defaut documentee:

```toml
status_line = ["model-with-reasoning", "context-remaining", "current-dir"]
```

## Commandes utiles dans Codex CLI

```text
/statusline
/status
/usage
/debug-config
```

`/statusline` est le meilleur chemin parce qu'il affiche les champs disponibles dans la version installee et persiste la configuration proprement.

## Ce qu'il ne faut pas porter tel quel

Ne pas copier l'approche Claude `~/.claude/settings.json` ou `~/.claude/statusline.js` dans Codex. Codex lit `~/.codex/config.toml`, et le manuel indique que la configuration projet `.codex/config.toml` n'est chargee que si le projet est approuve comme trusted.

Ne pas ajouter de requetes Gmail, calendrier ou meteo dans une boucle de terminal sans cache. Si ces donnees doivent etre visibles, preferer une automation Codex, un connecteur autorise, ou un script externe avec cache explicite.
