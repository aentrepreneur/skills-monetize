<!-- ================================================================= -->
<!-- Development By Angel Esquivel (Entrepreneur) [SKILLS-MONETIZE 2026] -->
<!-- ================================================================= -->
<!-- SKILLS-MONETIZE - Pipeline deterministico para empaquetar y vender agent skills propias -->

# skills-monetize

<!-- HEADER_LANG: en -->
<!-- HEADER_ROLE: (Entrepreneur) -->
<!-- HEADER_NAME: SKILLS-MONETIZE -->
<!-- HEADER_DESC: Pipeline deterministico para empaquetar y vender agent skills propias -->

Pipeline deterministico para **validar, pre-escanear, precificar y empaquetar**
agent skills propias, y para **preparar su publicacion** en marketplaces y en un
canal propio. Todo local, sin dependencias externas, sin tokens de LLM en el
empaquetado.

## Que resuelve

Empaquetar una skill para venderla hoy es manual, propenso a filtrar secretos y
sin criterio de precio. `skills-monetize` convierte ese proceso en un comando
reproducible:

1. **Valida** el `SKILL.md` (frontmatter, nombre, descripcion).
2. **Pre-escanea** seguridad (secretos, ejecucion peligrosa, rutas personales,
   egreso de red, tamano) — adelanta el escaneo del marketplace.
3. **Precifica** con una heuristica transparente (categoria + contenido).
4. **Empaqueta** ZIP + `listing.md` + `manifest.json` (con `sha256`).
5. **Prepara** el payload especifico de cada canal (Agensi, PromptBase, MCP
   Market, sitio propio).

## Estructura

```text
skills-monetize/
├── core/            # validator, prescan, pricing, packager
├── tools/           # CLI skillpack
├── channels/        # adaptadores de canal de publicacion
├── integrations/    # matriz de rutas de cobro (payout)
├── security/        # guardrail de frontera de datos (G5)
├── utils/           # utilidades transversales
├── tests/           # suite pytest (G4) + fixtures
└── docs/            # PRODUCTS, CATALOG, MARKET-RESEARCH, MCP-TO-SKILLS, MARKETS, PATHS, VERACIDAD, CHANNELS, LICENSING, VALUE, FACT-SHEET
```

## Quick start

```bash
# Entorno de desarrollo
uv venv venv && uv pip install --python venv/bin/python pytest ruff mypy

# Validar y pre-escanear una skill
python3 tools/skillpack.py validate <skill_dir>
python3 tools/skillpack.py prescan  <skill_dir>

# Empaquetar (zip + listing + manifest)
python3 tools/skillpack.py pack <skill_dir> --out dist

# Empaquetar sin escribir nada (gate)
python3 tools/skillpack.py selfcheck <skills_dir>

# Preparar payloads de todos los canales
python3 tools/skillpack.py prepare <skill_dir> --out dist

# Catalogo y material de publicacion (kits por producto + global)
python3 tools/skillpack.py catalog dist
python3 tools/skillpack.py kit dist --out dist/kits

# Rutas de cobro recomendadas para Guatemala
python3 tools/skillpack.py payout --country GT
```

## CLI

| Comando | Descripcion |
|---|---|
| `validate` | Valida frontmatter y contenido de `SKILL.md`. |
| `prescan` | Pre-scan de seguridad determinista. |
| `price` | Sugerencia de precio (min / recomendado / max). |
| `list` | Lista skills de un directorio. |
| `pack` | Empaqueta una skill. |
| `pack-all` | Empaqueta todas las skills de un directorio. |
| `prepare` | Empaqueta y genera payloads de canal. |
| `selfcheck` | Gate: exit 1 si alguna skill no pasa. |
| `payout` | Recomienda rutas de cobro por pais. |

## Que ofrecemos y a quien

La **fabrica** es este proyecto (`skills-monetize`), que no se vende. El
**producto** son las agent skills originales empaquetadas en `dist/`.

- **Que**: agent skills (carpetas con `SKILL.md`) que ensenan a un agente de IA
  a ejecutar un trabajo concreto. El catalogo (v0.4) es un set de **15 skills
  genericas**: `repo-intelligence`, `whitebox-pentest`, `ocr-texto`,
  `book-to-skill`, `sepia`, `readme-builder`, `niche-validator`, `video-prompts`,
  `skill-optimizer`, `content-matcher`, `website`, `licensed-one`,
  `opencode-agent-creator`, `web-research`, `youtube-transcript`. Total sugerido:
  **$230.40**. `repo-intelligence` se entrega **gratis** (MIT, lead magnet);
  `sepia` conserva su **MIT** original.
- **A quien**: desarrolladores y equipos pequenos que ya usan agentes de IA para
  programar (opencode, Claude Code, Cursor); nichos fuertes en seguridad
  (AppSec), contenido/video y negocios locales.
- **Con que fin**: productizar el harness de trabajo diario en productos
  portables, a costo marginal casi nulo, y venderlos en marketplaces y en canal
  propio.

Detalle completo en `docs/PRODUCTS.md`; evaluacion de todo lo empaquetable en
`docs/CATALOG.md`; caminos de salida en `docs/PATHS.md`.

## Valor del proyecto

Los escenarios de ingresos, costos y ROI estan en `docs/VALUE.md`. El analisis
de veracidad de Agensi y el estado de la investigacion estan en
`docs/VERACIDAD.md`.

## Pruebas

```bash
venv/bin/ruff check .                 # lint
venv/bin/mypy                         # tipos
venv/bin/python -m pytest             # tests (G4)
python3 scripts/update_headers.py --check   # gate Regla 14
```

## Estado

Proyecto en construccion (F0-F7). Cobro diferido por decision (ver
`docs/CHANNELS.md`). No publicar nada en servicios externos sin aprobacion
explicita (guardrail G3).

<!-- End Development By Angel Esquivel (Entrepreneur) [SKILLS-MONETIZE 2026] -->
