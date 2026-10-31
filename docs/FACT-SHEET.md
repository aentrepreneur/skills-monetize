<!-- ================================================================= -->
<!-- Development By Angel Esquivel (Entrepreneur) [SKILLS-MONETIZE 2026] -->
<!-- ================================================================= -->
<!-- SKILLS-MONETIZE - Pipeline deterministico para empaquetar y vender agent skills propias -->

# FACT-SHEET — skills-monetize

## Identidad

- **Nombre**: skills-monetize
- **Proposito**: validar, pre-escanear, precificar y empaquetar agent skills
  propias; preparar su publicacion en marketplaces y canal propio.
- **Persona**: Entrepreneur
- **Estado**: en construccion (F0-F7).

## Stack

- Python 3.12+ (solo stdlib en runtime).
- pytest (G4), ruff (lint), mypy (tipos).
- Sin dependencias runtime. Sin tokens de LLM en empaquetado.

## Modulos

| Ruta | Responsabilidad |
|---|---|
| `core/validator.py` | Valida `SKILL.md` y frontmatter. |
| `core/prescan.py` | Pre-scan de seguridad determinista. |
| `core/pricing.py` | Sugerencia de precio heuristica. |
| `core/packager.py` | ZIP + listing + manifest. |
| `tools/skillpack.py` | CLI. |
| `channels/` | Adaptadores Agensi/PromptBase/MCP Market/sitio propio. |
| `integrations/payout.py` | Matriz de rutas de cobro (GT). |
| `security/guard.py` | Frontera de datos (G5). |
| `utils/fs.py` | Utilidades. |

## Comandos clave

```bash
python3 tools/skillpack.py validate <skill_dir>
python3 tools/skillpack.py leakcheck <skill_dir>     # busca fugas del entorno
python3 tools/skillpack.py stage <skill_dir> --out staging
python3 tools/skillpack.py selfcheck <skills_dir>
python3 tools/skillpack.py pack-all <skills_dir> --out dist --version 1.0.0
python3 tools/skillpack.py prepare <skill_dir> --out dist
python3 tools/skillpack.py catalog dist
python3 tools/skillpack.py kit dist
python3 tools/skillpack.py payout --country GT
```

## Verificacion (G4)

```bash
venv/bin/ruff check .
venv/bin/mypy
venv/bin/python -m pytest
python3 scripts/update_headers.py --check
```

## Decisiones (registro cronologico; la iteracion mas reciente manda)

- 2026-10-16: project nuevo (no extender ai-monetize).
- 2026-10-16: cobro diferido; PayPal como rail provisional.
- 2026-10-16: set flagship solo de skills originales (excluye Apache-2.0 de
  terceros). Ver `LICENSING.md`.
- 2026-10-16: paquete vendible excluye `tests/`, `bench/`, `backups/`, venvs y
  respaldos; `.skillignore` y `.prescan-allow` permiten ajuste por skill.
- 2026-10-16: v0.1 = 5 SKUs de ingenieria/harness/seguridad
  (`project-builder`, `project-auditor`, `finish-loop`, `whitebox-pentest`,
  `repo-intelligence`). El resto de originales queda para v0.2 o vertical de
  creador. Ver `PRODUCTS.md` y `CATALOG.md`.
- 2026-10-16: las 22 agent-skills de `~/.agents/skills` (Anthropic) y las skills
  de terceros con licencia propia quedan EXCLUIDAS del catalogo vendible. Ver
  `CATALOG.md`.
- 2026-10-16: `nexus-one` y `nexus-core` no son skills; son linea de producto
  aparte (licencia D3). No entran al catalogo de skills de v0.1. Ver `PATHS.md`.

- 2026-10-16 (iteracion 2): la licencia del manifest se fija con `--license`
  en el momento de empaquetar. Eleccion de licencia comercial = V+ pendiente.
- 2026-10-16 (iteracion 2): etiquetas desde `keywords`; categoria explicita
  con `category:`. Precios heuristicos: ver `dist/catalog.json`.

- 2026-10-16 (iteracion 3): v0.1 = 2 skills genericas (`repo-intelligence`,
  `whitebox-pentest`). Las de uso interno salen de v0.1. Ver `PRODUCTS.md`.
- 2026-10-16 (iteracion 3): regla de venta = pasa `leakcheck` sobre el ZIP
  extraido. Atribucion `author:` permitida solo en frontmatter (decision
  pendiente: quitarla o mantenerla).
- 2026-10-16 (iteracion 4): v0.2 = **13 skills**. Se suman 11 reutilizando lo
  que ya existia (Tier 1: ocr-texto, book-to-skill, sepia, readme-builder; Tier
  2: niche-validator, video-prompts, skill-optimizer, content-matcher; bonus:
  website, licensed-one, opencode-agent-creator). Catalogo total $219.60.
- 2026-10-16 (iteracion 4): se mantiene `author:` (atribucion de marca, decision
  cerrada). `sepia` conserva su licencia MIT original.
- 2026-10-16 (iteracion 4): excluidos por no genericos: project-operator,
  wsl2-backup (ademas de los internos de iteracion 3).
- 2026-10-16 (iteracion 4): `.leakcheck-allow` para excepciones por skill (rutas
  universales de opencode). No se empaqueta.
- 2026-10-17 (iteracion 5): marketing kit determinista en `channels/marketing.py`
  + CLI `skillpack kit`; salida en `dist/kits/` (por producto y global). Sin LLM.
- 2026-10-17 (iteracion 5): investigacion de mercado documentada en
  `docs/MARKET-RESEARCH.md` (GitHub 2026-10-17; cifras de estrellas como
  referencia relativa, no absoluta).
- 2026-10-17 (iteracion 5): analisis de MCP documentado en `docs/MCP-TO-SKILLS.md`.
  Propios: `ddg-search`, `ytdlp-transcript` (candidatos). `github-insight` es de
  tercero (`wjddusrb03`, MIT) -> excluido como SKU propio. Conversion no ejecutada.
- 2026-10-17 (iteracion 6): **licencia mixta**. 13 SKUs `Proprietary` + `sepia`
  (MIT tercero) + `repo-intelligence` (MIT, **gratis**, `price: 0`, lead magnet).
  Total sugerido **$230.40** (excluye la gratis).
- 2026-10-17 (iteracion 6): precio fijo por frontmatter (`price:`) en
  `core/pricing.py`; seccion "Licencia" en el `listing.md` y columna de licencia
  + marca `GRATIS` en `dist/INDEX.md`.
- 2026-10-17 (iteracion 6): **conversion MCP -> skill ejecutada**: `web-research`
  (desde `ddg-search`) y `youtube-transcript` (desde `ytdlp-transcript`). Catalogo
  **13 -> 15**. `pyproject.toml` 0.3.0 -> 0.4.0.
- 2026-10-17 (iteracion 6): version del pipeline (pyproject) independiente de la
  version del producto (SKUs en `1.0.0`).

## Documentacion

| Archivo | Rol |
|---|---|
| `PRODUCTS.md` | Que ofrecemos, a quien y el catalogo de 15. |
| `CATALOG.md` | Evaluacion de todo lo empaquetable y vendible. |
| `PATHS.md` | Caminos de salida al mercado. |
| `LICENSING.md` | Estado de licencias de las skills. |
| `CHANNELS.md` | Canales de publicacion y cobro. |
| `VALUE.md` | Escenarios de ingresos y ROI. |
| `VERACIDAD.md` | Veracidad de datos del mercado (Agensi, etc.). |
| `MARKET-RESEARCH.md` | Referencias de GitHub/marketplaces y patrones de demanda. |
| `MCP-TO-SKILLS.md` | Evaluacion de MCP propios como skills vendibles. |
| `MARKETS.md` | Ubicacion de mercados/canales (Fase 4; la publicacion es manual). |
| `TECHNICAL.md` | Arquitectura y operacion.

## Artefactos generados (F6)

`dist/<skill>-1.0.0.{zip,listing.md,manifest.json}` + `channels/{agensi,promptbase,mcpmarket,own_site}.json`
para los **15** SKUs del catalogo, mas `dist/catalog.json`, `dist/INDEX.md` y
`dist/kits/` (material de publicacion por producto y global).

## Pendientes (V+)

- Confirmar ISR/crypto con contador.
- Licencia comercial: **resuelta** (esquema mixto; ver `LICENSING.md`). El
  manifest sale con `license` por SKU.
- Publicacion en canales externos (V+, guardrail G3). Ningun SKU esta publicado;
  depende de `docs/MARKETS.md` (Fase 4).
- Confirmar autoria de `doc-coauthoring`, `graphify`, `opencode-agent-creator` y
  derechos del corpus de `book-to-skill` (documentado, no bloquea).
- Medir ventas reales a 30 dias.

<!-- End Development By Angel Esquivel (Entrepreneur) [SKILLS-MONETIZE 2026] -->
