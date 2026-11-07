<!-- ================================================================= -->
<!-- Development By Angel Esquivel (Entrepreneur) [SKILLS-MONETIZE 2026] -->
<!-- ================================================================= -->
<!-- SKILLS-MONETIZE - Pipeline deterministico para empaquetar y vender agent skills propias -->

# LICENSING — politica de licencias del catalogo

> Metodo: lectura del campo `license` en cada `SKILL.md` y, cuando existe, del
> archivo `LICENSE`/`LICENSE.txt`. Aplica la matriz D1-D5 del skill
> `licensed-one`. **No es una opinion legal.**

Fecha: 2026-10-17 (v0.4.0).

## 1. Esquema elegido: licencia mixta

1. **Propietaria** para los SKUs de pago: `license: Proprietary` en el
   frontmatter, reflejado en el `manifest.json` y en la seccion "## Licencia"
   del `listing.md` que ve el comprador.
2. **MIT** para dos casos:
   - `repo-intelligence`: obra propia, se distribuye como **lead magnet**
     gratuito (`price: 0`). MIT maximiza la difusion de entrada al funnel.
   - `sepia`: obra de tercero (github.com/Nanako0129/sepia) que ya era MIT;
     se revende respetando la licencia y la atribucion original.
3. Decision cerrada: **no** se crean archivos `LICENSE` por paquete con el
   nombre del autor. La licencia se declara en frontmatter + manifest +
   `listing.md` + este documento.

## 2. Catalogo y licencia (15 SKUs)

| Skill | Licencia | Base |
|---|---|---|
| repo-intelligence | MIT (gratis) | Obra propia; lead magnet |
| whitebox-pentest | Propietaria | Obra propia |
| ocr-texto | Propietaria | Obra propia |
| book-to-skill | Propietaria | Obra propia (ver §5: derechos del corpus) |
| sepia | MIT | Tercero, Nanako0129 (atribucion conservada) |
| readme-builder | Propietaria | Obra propia |
| niche-validator | Propietaria | Obra propia |
| video-prompts | Propietaria | Obra propia |
| skill-optimizer | Propietaria | Obra propia |
| content-matcher | Propietaria | Obra propia |
| website | Propietaria | Obra propia |
| licensed-one | Propietaria | Obra propia |
| opencode-agent-creator | Propietaria | Obra propia |
| web-research | Propietaria | Obra propia (desde MCP propio `ddg-search`) |
| youtube-transcript | Propietaria | Obra propia (desde MCP propio `ytdlp-transcript`) |

Resumen: **13 propietarias + 2 MIT** (de las cuales una es la gratis).

## 3. Excluidos por licencia/procedencia

1. **Terceros Apache-2.0** (agent-skills de Anthropic): `security-best-practices`,
   `mcp-builder`, `transcribe`, `yeet`. Permiten redistribucion con atribucion,
   pero son contenido gratuito de terceros; Agensi rechaza skills reempaquetadas
   (§6.4). EXCLUIR.
2. **Otras skills de tercero**: `python-pro` (zenobi-us), `web-design-guidelines`
   (Vercel), `agent-browser` (envuelve una herramienta de tercero). EXCLUIR.
3. **`github-insight`** (MCP): autoría de tercero (`wjddusrb03`, MIT). No se
   presenta como propia. EXCLUIR como SKU.
4. **Las 22 agent-skills** de `~/.agents/skills`: uso interno, no reventa.
5. **Originales atados al harness propio** (`project-builder`, `project-auditor`,
   `finish-loop`, `project-operator`, `wsl2-backup`): no son genericos.

## 4. Reglas de cumplimiento

1. Toda skill a vender declara un campo `license:` en su `SKILL.md`.
2. Skills MIT/Apache-2.0 de terceros: **no** se revenden salvo `sepia` (MIT, con
   atribucion). Nunca presentar obra de tercero como propia.
3. La licencia viaja al `manifest.json` y al `listing.md` (visibilidad del
   comprador).
4. Excluir cualquier skill con codigo de cliente o rutas internas (G5); hoy el
   catalogo pasa `leakcheck` con 0 hallazgos.

## 5. Pendientes

1. Confirmar derechos del **corpus** que el usuario procese con `book-to-skill`:
   la skill es propia; el corpus es responsabilidad de quien la usa (documentado
   en el propio `SKILL.md`).
2. Confirmar autoria de `doc-coauthoring`, `graphify` y `opencode-agent-creator`
   (no entran al catalogo de 15 hasta resolverlo).
3. Revision legal formal (contador/abogado) antes de facturacion: fuera de
   alcance de este documento.

<!-- End Development By Angel Esquivel (Entrepreneur) [SKILLS-MONETIZE 2026] -->
