# Punto de restauración — Pre-Taller

Fecha: 2026-06-30

## Estado guardado
- Commit: `e23671b` — "Clarify required Python version (3.11) in taller instructions"
- Tag de git: `checkpoint-pre-taller` (pusheado a GitHub)
- Base de datos: `backups/salud_natura_checkpoint_pre_taller.db`
  - 36 plantas en el grimorio (`base_conocimiento_salud`)
  - 29 dolencias en el botiquín (25 vinculadas por FK `id_remedio` al grimorio)

## Cómo volver si algo se rompe en el taller

### Restaurar el código
```bash
git fetch --tags
git reset --hard checkpoint-pre-taller
git push origin main --force   # solo si ya se pusheó algo roto a producción
```

### Restaurar la base de datos local
```bash
cp backups/salud_natura_checkpoint_pre_taller.db data/salud_natura.db
```

## Requisitos para correr local
- Python 3.11 (no 3.12/3.13/3.14 — `pydantic-core` no es compatible)
- Entorno virtual: `.venv/`
- Levantar servidor: `.venv/Scripts/python.exe -m uvicorn app.main:app --port 8000`
