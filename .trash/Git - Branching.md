---
{}
---

# Git — Branching

## Resumen
> Las ramas permiten trabajar en funcionalidades de forma aislada sin afectar al código principal.

## Comandos de ramas
```bash
git branch                    # listar ramas
git branch nueva-rama         # crear rama
git checkout nueva-rama       # cambiar a rama
git checkout -b nueva-rama    # crear y cambiar a la vez
git branch -d rama            # eliminar rama
```

## Merge — unir ramas
```bash
# Estando en main:
git merge nueva-rama
```

## Flujo típico
```
main ──●──────────────────●── (merge)
        \                /
feature  ●──●──●──●──●──
```

## Ver también
- [[Notes/Git - Basic Commands|Comandos básicos]]
- [[Notes/Git - Rebase vs Merge|Rebase vs Merge]]
