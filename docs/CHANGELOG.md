<!-- ================================================================= -->
<!-- Development By Angel Esquivel (Entrepreneur) [SKILLS-MONETIZE 2026] -->
<!-- ================================================================= -->
<!-- SKILLS-MONETIZE - Pipeline deterministico para empaquetar y vender agent skills propias -->

# Changelog

## 0.4.0 — 2026-10-17

### Added

- Precio fijo declarado en frontmatter: `core/pricing.py` lee `price:` y, si es
  valido, fija `min = sugerido = max` (usado por el lead magnet gratuito).
- Seccion "## Licencia" en el `listing.md` de cada producto y columna
  `Licencia` + marca `GRATIS` en `dist/INDEX.md` (`core/packager.py`,
  `tools/skillpack.py cmd_catalog`).
- Skills `web-research` (desde el MCP propio `ddg-search`) y `youtube-transcript`
  (desde el MCP propio `ytdlp-transcript`): el catalogo pasa de 13 a **15**.
- 3 pruebas nuevas en `tests/test_pricing.py` (override $0, override `$49.00`,
  override invalido -> heuristica).

### Changed

- Licencia del catalogo: esquema **mixto**. 13 SKUs propietarios + `sepia` (MIT
  de tercero, se revende con atribucion) + `repo-intelligence` (MIT, se entrega
  **gratis** como lead magnet con `price: 0`). Total sugerido: **$230.40**.
- `pyproject.toml`: 0.3.0 -> 0.4.0.
- Documentos reconciliados al set de 15 y al esquema de licencia (PRODUCTS,
  CATALOG, LICENSING, PATHS, VALUE, FACT-SHEET, README, MCP-TO-SKILLS).

### Decided

- Politica de licencia mixta: propietaria para los SKUs de pago; MIT solo para
  el lead magnet y para `sepia` (que ya era MIT de tercero).
- La conversion MCP -> skill se ejecuta para los dos MCP propios; se descarta
  `github-insight` como SKU (autoría de tercero).


## 0.3.0 — 2026-10-17

### Added

- `channels/marketing.py`: generador determinista de material de publicacion y
  seguimiento, sin LLM. Por producto: `LISTING.md`, `README-SHORT.md`,
  `FAQS.md`, `posts/{x,linkedin,reddit,hackernews,producthunt,email}.md` y
  `TRACKING.csv`. Global: `PLAYBOOK.md`, `LAUNCH-CALENDAR.md` y `TRACKING.csv`.
- Comando CLI `skillpack kit [dist_dir] [--out dist/kits]`: escribe los kits
  en `dist/kits/`.
- `docs/MARKET-RESEARCH.md`: referencias de GitHub (skills y MCP populares),
  marketplaces y patrones de demanda, con fecha y caveat de veracidad.
- `docs/MCP-TO-SKILLS.md`: inventario de los 12 MCP del entorno, distincion
  propio/tercero, candidatos (`ddg-search`, `ytdlp-transcript`) y receta de
  conversion MCP -> skill.
- 10 pruebas nuevas (`tests/test_marketing.py`).

### Changed

- Los borradores de post dejan marcadores `{{LINK}}` y notas de edicion; el
  material describe capacidades reales y no inventa resultados (Regla de
  veracidad).

### Decided

- `github-insight` NO es autoría del dueno (MIT de `wjddusrb03`); se excluye
  como SKU propio. `ddg-search` y `ytdlp-transcript` si son propios.


## Versiones anteriores

Las releases previas (0.2.0, 0.1.3 y anteriores) estan archivadas en
`docs/history/CHANGELOG-202610.md`. El historico completo es `git log`.

<!-- End Development By Angel Esquivel (Entrepreneur) [SKILLS-MONETIZE 2026] -->
