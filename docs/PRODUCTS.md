<!-- ================================================================= -->
<!-- Development By Angel Esquivel (Entrepreneur) [SKILLS-MONETIZE 2026] -->
<!-- ================================================================= -->
<!-- SKILLS-MONETIZE - Pipeline deterministico para empaquetar y vender agent skills propias -->

# PRODUCTS — Que ofrecemos (v0.4.0)

## 1. Que es una skill

Una skill es una carpeta con un archivo `SKILL.md`. Le dice a un agente de IA
(opencode, Claude Code, Cursor u otro compatible) como hacer una tarea concreta.
El agente la carga cuando la tarea lo pide.

## 2. Fabrica y producto

1. La fabrica es `skills-monetize`. Valida, detecta fugas, precia y empaqueta.
   No se vende.
2. El producto son las skills empaquetadas en `dist/`.

## 3. Catalogo — 15 skills genericas

Criterio: la skill debe funcionar en cualquier equipo, sin rutas, herramientas
ni proyectos del dueno. Toda skill vendible pasa `leakcheck` sobre el contenido
real del ZIP (0 hallazgos).

Licencia (esquema mixto): 13 SKUs **propietarios**; `sepia` es **MIT** de
tercero (se revende con atribucion); `repo-intelligence` es **MIT** y se
entrega **gratis** como lead magnet (`price: 0`).

| # | Skill | Categoria | Licencia | Que hace |
|---|---|---|---|---|
| 1 | repo-intelligence | general | MIT (gratis) | Divide una idea en modulos, busca repos en GitHub con `gh` y recomienda usar o construir. |
| 2 | whitebox-pentest | security | Propietaria | Lista entradas de usuario y funciones peligrosas en Python, y busca secretos. Local. |
| 3 | ocr-texto | general | Propietaria | Extrae texto de imagenes de forma local (RapidOCR/ONNX, offline). |
| 4 | book-to-skill | agent | Propietaria | Convierte un libro tecnico en PDF/EPUB a un paquete de conocimiento consultable. |
| 5 | sepia | engineering | MIT | Hace que un texto generado por IA se lea humano (ficcion y prosa profesional). |
| 6 | readme-builder | general | Propietaria | Genera un README con estandar visual alto (badges, alertas, hero centrado). |
| 7 | niche-validator | general | Propietaria | Valida nichos en tiempo real y los clasifica GREEN/YELLOW/RED. |
| 8 | video-prompts | content | Propietaria | Genera proyectos de video AI con niveles progresivos y consultas integradas. |
| 9 | skill-optimizer | agent | Propietaria | Reduce el uso de tokens de una skill entre 80% y 95% sin perder funcion. |
| 10 | content-matcher | content | Propietaria | Transcribe videos de YouTube y los matchea contra los proyectos de un directorio. |
| 11 | website | devops | Propietaria | Genera un sitio para un negocio y lo despliega gratis en Cloudflare Pages. |
| 12 | licensed-one | agent | Propietaria | Matriz D1-D5 para licenciar un proyecto de IA/LLM/agentes. |
| 13 | opencode-agent-creator | agent | Propietaria | Crea agentes de opencode (modos, prompts, modelos, permisos). |
| 14 | web-research | general | Propietaria | Busqueda web/news/imagenes + fetch con DuckDuckGo, sin API key. |
| 15 | youtube-transcript | content | Propietaria | Obtiene la transcripcion de un video de YouTube (subtitulos, sin transcribir audio). |

Total sugerido (sin el lead magnet gratuito): **$230.40** (heuristica; se ajusta
con ventas reales).

## 4. Fuera del catalogo y por que

| Skill | Motivo |
|---|---|
| project-builder | Depende de plantillas, licencias y memoria propias. |
| project-auditor | Verifica contra reglas propias del ecosistema. |
| finish-loop | Cierre atado a memoria y documentos propios. |
| project-operator | Ciclo post-deploy atado al triangulo Builder/Auditor/Operator propio. |
| wsl2-backup | Respalda rutas concretas del equipo del dueno; no es generico. |
| grill-me, ecosystem-audit, music-operator | Ligadas al harness o a un proyecto propio. |

## 5. A quien

1. Desarrolladores y equipos que ya usan agentes de IA para programar.
2. Nicho seguridad: revision previa de codigo propio (whitebox-pentest).
3. Nicho creador: contenido y video (niche-validator, video-prompts, content-matcher).
4. Nicho negocio local: sitios para pymes (website).

## 6. Limites de veracidad

1. No se venden skills de terceros con licencia restrictiva ni la fabrica.
2. `sepia` se distribuye bajo su licencia MIT original (atribucion conservada).
3. `repo-intelligence` es MIT y gratuito (lead magnet); no cuenta en el total.
3. Las cifras de `VALUE.md` son escenarios, no datos de venta.
4. Los precios son una heuristica; se ajustan con ventas reales.
5. Nada se publica sin aprobacion explicita (V+, guardrail G3).

## 7. Estado

1. Empaquetado local: 15 skills en `dist/` (ZIP, listing, manifest, payloads).
2. Material de publicacion y seguimiento: `dist/kits/` (por producto y global)
   generado con `skillpack kit` (`PLAYBOOK.md`, `LAUNCH-CALENDAR.md`,
   `TRACKING.csv`).
3. Publicado en ningun lado.
4. Pendientes V+: publicacion en canales externos. La licencia comercial ya
   quedo definida (esquema mixto; ver `LICENSING.md`).

## 8. Convertidos desde MCP (0.4.0)

1. `web-research` (desde el MCP propio `ddg-search`): busqueda sin API key.
2. `youtube-transcript` (desde el MCP propio `ytdlp-transcript`).
3. `github-insight` NO se convierte: es de tercero (`wjddusrb03`, MIT).
4. Ver `docs/MCP-TO-SKILLS.md` para el analisis y la receta de conversion.

<!-- End Development By Angel Esquivel (Entrepreneur) [SKILLS-MONETIZE 2026] -->
