<!-- ================================================================= -->
<!-- Development By Angel Esquivel (Entrepreneur) [SKILLS-MONETIZE 2026] -->
<!-- ================================================================= -->
<!-- SKILLS-MONETIZE - Pipeline deterministico para empaquetar y vender agent skills propias -->

# MARKET-RESEARCH — Referencias de GitHub y del mercado de skills

Documento de referencia. Evita repetir la busqueda. Toda cifra que aparece
aqui viene de la busqueda indicada y lleva su fecha.

## 1. Metodo

1. Fecha de la busqueda: **2026-10-17**.
2. Herramienta: busqueda de repositorios en GitHub (orden por estrellas).
3. Consultas usadas: `claude skills`, `agent skills awesome`,
   `mcp server security audit`.
4. Reutilizar este documento antes de volver a buscar. Si se refina, anotar
   aqui la consulta nueva y el resultado.

## 2. Caveat de veracidad

Las cifras de estrellas del entorno salen anormalmente altas para varios
repos (p.ej. cientos de miles). Usarlas como **referencia relativa** (que
tipo de proyecto lidera), **no como dato absoluto**. No citar estos numeros
en material de venta.

## 3. Repos de referencia (2026-10-17)

### 3.1. Harness y rendimiento de agentes

| Repo | Descripcion | Lectura para nosotros |
|---|---|---|
| affaan-m/ECC | Sistema de optimizacion de rendimiento del harness: skills, instintos, memoria, seguridad, research-first. | Confirma que "harness + skills + memoria" es una categoria que atrae; ya lo tenemos propio. |
| JuliusBrussee/caveman | Skill + proxy que recorta ~65% de tokens. | La reduccion de tokens vende; nuestro `skill-optimizer` juega en esa liga. |
| ruvnet/ruflo | Harness de agentes original: swarms, memoria adaptativa, federacion, RAG. | Multi-agente/memoria es tendencia; no es nuestro foco de SKU. |

### 3.2. Contexto y conocimiento

| Repo | Descripcion | Lectura para nosotros |
|---|---|---|
| Graphify-Labs/graphify | Convierte cualquier codebase en un grafo de conocimiento consultable; parsing AST determinista local, sin vector store. | Valida el enfoque local/determinista. Tenemos `graphify` en el harness (no vendible tal cual). |
| multica-ai/andrej-karpathy-skills | Un solo `CLAUDE.md` que mejora el comportamiento del agente. | Un archivo simple puede tener mucho alcance. |

### 3.3. Diseno y frontend

| Repo | Descripcion | Lectura para nosotros |
|---|---|---|
| nextlevelbuilder/ui-ux-pro-max-skill | Skill de inteligencia de diseno UI/UX multi-plataforma. | Categoria de diseno con demanda; tenemos `web-design-guidelines` (tercero) y `frontend-ui-engineering` (Anthropic). |
| bergside/awesome-design-skills | Lista de 67 archivos SKILL.md / DESIGN.md de diseno agentico. | Hay ecosistema de "design skills"; posible vertical. |

### 3.4. Diagramas y visual

| Repo | Descripcion | Lectura para nosotros |
|---|---|---|
| tt-a1i/archify | Convierte idea/plan/codebase en diagrama interactivo. | "Explicar visualmente" vende; no lo cubrimos aun. |

### 3.5. Directorios y listas curadas (para descubrimiento, no competencia)

| Repo | Descripcion |
|---|---|
| ComposioHQ/awesome-claude-skills | Lista curada de Claude Skills. |
| VoltAgent/awesome-agent-skills | 1000+ skills comunitarias, multi-agente. |
| hesreallyhim/awesome-claude-code | Recursos, plugins y skills de Claude Code. |
| github/awesome-copilot | Instrucciones/agentes/skills para GitHub Copilot. |
| sickn33/agentic-awesome-skills | Control plane local con 2600+ skills. |
| Shubhamsaboo/awesome-llm-apps | 100+ apps de agentes y RAG. |

**Uso:** estos directorios son canales de **descubrimiento** (donde puede
aparecer una skill), no productos a vender.

### 3.6. Seguridad de agentes/MCP (nicho fuerte)

| Repo | Descripcion | Lectura para nosotros |
|---|---|---|
| getagentseal/agentseal | Escanea la maquina por skills peligrosas y configs MCP; prueba resistencia a prompt injection. | Nicho de seguridad de agentes en auge. |
| graygnatconsole/mcp-audit-tool | CLI de auditoria de servidores MCP (tool poisoning, secretos, command injection); SARIF + CI. | `whitebox-pentest` esta cerca; se podria sumar auditoria MCP. |
| HarmonicSecurity/claudit-sec | Auditoria de MCP/plugins/permisos en Claude Desktop/Code. | Idem. |
| vulnersCom/api | SDK con MCP para vulnerabilidades (CVEs/EPSS/KEV). | Fuente de datos, no producto propio. |

## 4. Patrones que se repiten (que vende / que atrae)

1. **Ahorro medible**: tokens, tiempo, pasos. (`caveman`, `skill-optimizer`).
2. **Contexto/knowledge graph local y determinista**. (`graphify`).
3. **Diseno y UI/UX de calidad** como skill. (design skills).
4. **Explicar visualmente** (diagramas). (`archify`).
5. **Seguridad de agentes/MCP** como nicho en crecimiento. (agentseal, mcp-audit).
6. **Un solo archivo, mucho efecto** (`CLAUDE.md`).
7. **Listas curadas** = canal de descubrimiento.

## 5. Marketplaces observados

| Canal | Modelo | Nota |
|---|---|---|
| Agensi | Marketplace de skills/agentes; split 70/30; ToS prohibe off-platform. | Real, pero cifras de trafico de marketing infladas. |
| PromptBase | Marketplace de prompts. | Adyacente; sirve para prompts, no solo skills. |
| MCP Market | Directorio/marketplace de servidores MCP. | Natural para la linea MCP (ver `MCP-TO-SKILLS.md`). |
| Sitio propio (Cloudflare Pages) | Checkout Merchant-of-Record. | Mayor margen; activo de audiencia directa. |

Detalle de cobro en `docs/CHANNELS.md`, `docs/PATHS.md` y `docs/LICENSING.md`.

## 6. Lectura para nuestro catalogo

1. Nuestro catalogo ya cubre: ahorro de tokens (`skill-optimizer`),
   seguridad (`whitebox-pentest`), contexto (`repo-intelligence`), contenido
   (`niche-validator`, `video-prompts`, `content-matcher`).
2. Huecos con demanda detectada: **diseno/UI**, **diagramas**,
   **auditoria de MCP**.
3. No competir con directorios: usarlos como canal.
4. La linea MCP propia (`ddg-search`, `ytdlp-transcript`) es un producto
   distinto con su propio canal (`MCP Market`). Ver `MCP-TO-SKILLS.md`.

<!-- End Development By Angel Esquivel (Entrepreneur) [SKILLS-MONETIZE 2026] -->
