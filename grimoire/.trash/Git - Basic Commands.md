---
{}
---

# Git — Basic Commands

## Resumen
> Los comandos fundamentales de Git para el día a día.

## Flujo básico
```bash
# 1. Inicializar repositorio
git init

# 2. Ver estado
git status

# 3. Añadir cambios al staging
git add archivo.txt       # un fichero
git add .                 # todo

# 4. Hacer commit
git commit -m "mensaje descriptivo"

# 5. Ver historial
git log --oneline
```

## Trabajar con remotos (GitHub)
```bash
git remote add origin https://github.com/usuario/repo.git
git push origin main
git pull origin main
git clone https://github.com/usuario/repo.git
```

## Comandos útiles
```bash
git diff          # ver cambios sin añadir
git restore .     # deshacer cambios sin commitear
git stash         # guardar cambios temporalmente
```

## Ver también
- [[Notes/Git - Branching|Ramas en Git]]
- [[Notes/Git - Rebase vs Merge|Rebase vs Merge]]
- [[Tools/Git/Index|Git — Índice completo]]

## Referencias
- https://git-scm.com/docs
