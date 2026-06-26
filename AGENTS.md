# AGENTS.md

## Projet

Ce depot documente une adaptation Codex de la status line de Claude Code.

## Regles de travail

- Repondre en francais sauf demande contraire.
- Ne pas modifier directement `~/.codex/config.toml` sans demande explicite.
- Garder les exemples de configuration sans secrets, tokens, chemins personnels sensibles, ni identifiants OAuth.
- Verifier les affirmations Codex dans le manuel officiel Codex ou via la CLI locale avant de les presenter comme actuelles.
- Ne pas utiliser de tiret em ni d'emojis dans les fichiers du projet.

## Verification

Avant de finaliser une modification, verifier au minimum:

```powershell
git status --short
rg -n "status_line|/statusline|config.toml" .
```
