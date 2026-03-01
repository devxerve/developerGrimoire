---
{}
---

# Git — Rebase vs Merge

## Resumen
> Dos formas de integrar cambios de una rama en otra. Diferente historial resultante.

## Merge
Crea un commit de fusión que une las dos historias.
```bash
git checkout main
git merge feature
```
```
main ──●──●──────────M
        \           /
feature  ●──●──●──●
```
✅ Preserva el historial completo
⚠️ Puede ensuciar el historial con muchos merges

## Rebase
Reaplica los commits de feature encima de main.
```bash
git checkout feature
git rebase main
```
```
main    ──●──●──●──●──●──●  (commits de feature reescritos)
```
✅ Historial lineal y limpio
⚠️ Reescribe el historial — no usar en ramas compartidas

## ¿Cuándo usar cada uno?
| Situación | Recomendación |
|---|---|
| Rama de feature personal | `rebase` |
| Rama compartida con equipo | `merge` |
| Pull de main a tu rama | `rebase` |
| Publicar feature a main | `merge` (PR) |

## Ver también
- [[Notes/Git - Branching|Ramas en Git]]
