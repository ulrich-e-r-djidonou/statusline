# Decisions

## 2026-06-26, ne pas modifier la config globale automatiquement

Decision: ne pas ecrire directement dans `~/.codex/config.toml`.

Raison: la demande porte sur une adaptation et le dossier courant est un depot de documentation. Modifier la configuration globale Codex changerait le comportement de toutes les sessions Codex sur la machine.

Alternative: fournir `.codex/config.statusline.example.toml` avec une ligne prete a copier.

Statut: retenu.

## 2026-06-26, preferer `/statusline` a un port script Claude

Decision: recommander `/statusline` et `status_line` plutot qu'un script Node.js.

Raison: le manuel Codex documente `/statusline` et `status_line`; il ne documente pas d'equivalent direct de `~/.claude/statusline.js` pour injecter des segments arbitraires dans la status line.

Alternative: construire un script externe PowerShell ou Node.js pour afficher Gmail, calendrier, meteo ou PR GitHub dans le prompt shell. Cette alternative sort de la status line native Codex.

Statut: retenu.
