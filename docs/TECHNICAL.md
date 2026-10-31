<!-- ================================================================= -->
<!-- Development By Angel Esquivel (Entrepreneur) [SKILLS-MONETIZE 2026] -->
<!-- ================================================================= -->
<!-- SKILLS-MONETIZE - Pipeline deterministico para empaquetar y vender agent skills propias -->

# Technical Documentation

## Overview

`skills-monetize` es un pipeline determinista (sin LLM en el empaquetado) que
transforma skills propias en artefactos listos para publicar: valida, pre-escanea,
precifica y empaqueta, y prepara el material especifico de cada canal de venta.

## Arquitectura

```text
skill_dir (SKILL.md + recursos)
   │
   ├─ core/validator.validate_skill ──► ValidationResult
   ├─ core/prescan.prescan ───────────► PrescanResult
   ├─ core/pricing.suggest_price ─────► PriceSuggestion
   │
   └─ core/packager.build_package
         ├─ dist/<name>-<version>.zip
         ├─ dist/<name>-<version>.listing.md
         └─ dist/<name>-<version>.manifest.json
                │
                └─ channels/*.build_payload ──► dist/<name>-<version>/channels/<channel>.json
```

Capas:
1. **core**: logica pura, sin red ni estado global.
2. **tools**: CLI (`skillpack`) que orquesta core + channels.
3. **channels**: adaptadores que preparan payloads por canal (no publican).
4. **integrations**: matriz de rutas de cobro (informacion, no ejecucion).
5. **security**: guardrail G5 de frontera de datos.
6. **utils**: utilidades transversales.

## Flujo de empaquetado

1. **Seleccion**: `utils.fs.iter_package_files` define el conjunto incluido,
   excluyendo artefactos de desarrollo (backups, entornos virtuales —incluidas
   variantes por nombre y por `pyvenv.cfg`—, caches, `.git`) y archivos de
   respaldo. Es la fuente unica de verdad para el escaneo y el ZIP.
2. **Validacion**: `SKILL.md` existe, frontmatter valido, nombre kebab-case,
   descripcion 20-1024 caracteres, cuerpo no vacio.
3. **Pre-scan**: por cada archivo de texto incluido se detectan secretos
   (severidad critical), ejecucion peligrosa y rutas personales —`high` en
   codigo, `low` en documentacion—, `.env` (high), tamanos (high), licencia
   (medium) y hosts no verificados (low). Un hallazgo critical/high bloquea el
   paquete salvo `--force`.
4. **Precio**: categoria inferida por palabras clave; rango = base × factor.
5. **Empaquetado**: ZIP reproducible con la estructura bajo el nombre de la
   skill; `listing.md` con material de venta; `manifest.json` con precio, tags,
   `sha256`, tamano y estado del pre-scan.

## Modelo de datos

- `SkillMeta`: name, description, license, extra.
- `ValidationResult`: ok, errors[], warnings[], meta.
- `PrescanResult`: passed, findings[], files_scanned, total_bytes.
- `Finding`: check, severity, detail, file.
- `PriceSuggestion`: minimum, suggested, maximum, category, rationale[].
- `PackResult`: ok, name, version, zip_path, listing_path, manifest_path,
  sha256, size_bytes, errors[], warnings[].
- `ChannelPayload`: channel, name, version, fields{}, requires_review, notes[].
- `PayoutRoute`: id, label, compatible_gt, taxes_note, friction, recommended.

## Decisiones de diseno

1. **Stdlib-only en runtime**: cero dependencias de produccion.
2. **Determinista**: sin LLM ni red; misma entrada → misma salida.
3. **Publicacion separada**: los adaptadores preparan payloads pero no publican
   (guardrail G3: accion externa irreversible requiere aprobacion).
4. **Frontera de datos (G5)**: el guardrail evita filtrar codigo de cliente o
   rutas internas.

## Verificacion

```bash
venv/bin/ruff check .
venv/bin/mypy
venv/bin/python -m pytest
python3 scripts/update_headers.py --check
```

<!-- End Development By Angel Esquivel (Entrepreneur) [SKILLS-MONETIZE 2026] -->
