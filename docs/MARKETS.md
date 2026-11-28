<!-- ================================================================= -->
<!-- Development By Angel Esquivel (Entrepreneur) [SKILLS-MONETIZE 2026] -->
<!-- ================================================================= -->
<!-- SKILLS-MONETIZE - Pipeline deterministico para empaquetar y vender agent skills propias -->

# MARKETS — ubicacion de mercados y canales (Fase 4)

> **Este documento ubica; no publica.** La publicacion es **manual** y requiere
> aprobacion explicita del dueno (V+, guardrail G3). Aqui se identifica donde
> colocar cada producto, con las restricciones conocidas, para que el paso
> manual sea rapido y sin sorpresas.
>
> Fuente: `MARKET-RESEARCH.md`, `CHANNELS.md` y `PATHS.md`. Los dominios y las
> condiciones de cada plataforma **deben re-verificarse al momento de publicar**
> (cambian); aqui no se inventan cifras.

Fecha: 2026-10-17 (v0.4.0).

## 1. Canales objetivo

| Canal | Tipo | Producto que encaja | Notas |
|---|---|---|---|
| Agensi (`agensi.io`) | Marketplace de skills/agentes | SKUs propietarios | Split ~70/30; ToS prohibe venta fuera de plataforma y rechaza reempaquetado de terceros. |
| PromptBase | Marketplace de prompts | Prompts y skills afines | Venta unica; 80% marketplace / 100% enlace propio. |
| MCP Market | Directorio/marketplace de MCP | Linea MCP (aparte, ver §6) | Listados destacados de pago. |
| Sitio propio (Cloudflare Pages) | Venta directa | Todos + lead magnet | Mayor margen (solo fee MoR); captura audiencia propia. |

Regla del ToS de Agensi (ver `CHANNELS.md` §1): **no** enlazar ventas fuera de
la plataforma; la plataforma puede ajustar el split; no se puede excluir la
skill de la distribucion por agente/creditos.

## 2. Mapeo por vertical

1. **Ingenieria/Dev** (espacio con menos competencia, segun `MARKET-RESEARCH.md`
   §4): `whitebox-pentest`, `skill-optimizer`, `book-to-skill`, `readme-builder`,
   `licensed-one`, `opencode-agent-creator`, `web-research`, `website`,
   `ocr-texto`.
2. **Creador/Contenido**: `content-matcher`, `niche-validator`, `video-prompts`,
   `youtube-transcript`, `sepia`.
3. **Lead magnet**: `repo-intelligence` (gratis, MIT) como entrada al funnel
   (Camino C, ver `PATHS.md`).

## 3. Canales de descubrimiento (no de venta)

Listas curadas donde una skill puede ganar visibilidad (contribuir via PR,
respetando las reglas del repo): `ComposioHQ/awesome-claude-skills`,
`VoltAgent/awesome-agent-skills`, `hesreallyhim/awesome-claude-code`,
`github/awesome-copilot`, `sickn33/agentic-awesome-skills`. Son **canal**, no
producto (`MARKET-RESEARCH.md` §3.5).

## 4. Restricciones que condicionan la publicacion

1. **Originalidad**: Agensi rechaza skills reempaquetadas de terceros (§6.4);
   por eso el catalogo es de obra propia + `sepia` (MIT, atribuida).
2. **Licencia declarada**: cada ZIP viaja con `license` en el manifest y en el
   `listing.md` (§ "Licencia"); ver `LICENSING.md`.
3. **Sin fugas**: solo se publica lo que pasa `leakcheck` (0 hallazgos).
4. **Cobro**: Stripe no opera en Guatemala; usar MoR (LemonSqueezy/Gumroad) o
   PayPal (ver `CHANNELS.md` §2).

## 5. Checklist de publicacion manual

Se ejecuta **una sola vez por canal**, con V+ del dueno:

1. Elegir el canal y el producto (`dist/<skill>-1.0.0.zip`).
2. Confirmar el dominio y las condiciones vigentes del canal.
3. Subir el ZIP + el `listing.md` como descripcion; pegar desde
   `dist/kits/<producto>/LISTING.md` y los `posts/`.
4. Respetar el ToS (sin enlaces de venta fuera de plataforma en Agensi).
5. Registrar la publicacion en `dist/kits/TRACKING.csv`.
6. Verificar que la licencia visible coincide con el manifest.

## 6. Linea MCP (producto distinto)

Los MCP propios (`ddg-search`, `ytdlp-transcript`) pueden venderse como MCP en
MCP Market, **como linea aparte** de las skills (`MCP-TO-SKILLS.md` §5). La
version-skill ya esta en el catalogo (`web-research`, `youtube-transcript`); la
version-MCP es un artefacto distinto con su propio canal.

## 7. Pendientes (V+)

1. Re-verificar dominios y condiciones de Agensi/PromptBase/MCP Market antes de
   publicar.
2. Confirmar soporte de payout para Guatemala (LemonSqueezy/Gumroad via PayPal)
   al suscribir.
3. Decidir el canal de arranque (recomendacion: sitio propio, Camino A + C).
4. Ningun SKU esta publicado.

<!-- End Development By Angel Esquivel (Entrepreneur) [SKILLS-MONETIZE 2026] -->
