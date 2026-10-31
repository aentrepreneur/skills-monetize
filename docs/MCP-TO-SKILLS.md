<!-- ================================================================= -->
<!-- Development By Angel Esquivel (Entrepreneur) [SKILLS-MONETIZE 2026] -->
<!-- ================================================================= -->
<!-- SKILLS-MONETIZE - Pipeline deterministico para empaquetar y vender agent skills propias -->

# MCP-TO-SKILLS — Evaluacion de MCPs como skills vendibles

Documento de referencia. Evita repetir el inventario y el analisis de autoría.

## 1. Metodo

1. Fecha: **2026-10-17**.
2. Fuente: `~/.config/opencode/mcp-servers/` y `opencode.json` (server MCP
   declarados), mas revision de cabeceras, LICENSE y docstrings de cada uno.
3. Criterio de autoría: docstrings en espanol + sin LICENSE + sin git =
   probable autoría del dueno. LICENSE con otro autor o README en otro idioma
   = tercero.

## 2. Inventario (12 MCP declarados)

| MCP | Tipo | Actor | Autoría | Vendible como propio |
|---|---|---|---|---|
| ytdlp-transcript | local (py) | propio | Dueno (docstrings es) | **Si** |
| ddg-search | local (py) | propio | Dueno (docstrings es) | **Si** |
| github-insight | local (py) | tercero | `wjddusrb03` (MIT, README ko) | No (MIT de tercero) |
| mcp-security-audit | local (npm) | tercero | paquete npm | No |
| context7 | remote | tercero | Context7 | No |
| github | local (npm) | tercero | GitHub | No |
| filesystem | local (npm) | tercero | oficial MCP | No |
| sequential-thinking | local (npm) | tercero | oficial MCP | No |
| chrome-devtools | local (npm) | tercero | oficial MCP | No |
| mempalace | remote | tercero | MemPalace | No |
| agent-browser | local (npm) | tercero | agent-browser | No |

Nota: `github-insight` es MIT; permitiria reventa con atribucion, pero NO es
autoría del dueno y confundirla como propia es un riesgo de veracidad. Se
excluye como SKU propio.

## 3. Candidatos propios (autoría del dueno)

### 3.1. `ddg-search` -> skill `web-research`

1. Que es: busqueda web/news/imagenes + fetch de contenido via DuckDuckGo,
   sin API key.
2. Formato actual: servidor MCP (`ddg-search/server.py`, 143 lineas).
3. Conversion: extraer la logica a un script CLI `websearch.py` (subcomandos
   `web`, `news`, `image`, `fetch`) y crear `SKILL.md` que ensene a usarlo.
4. Requisitos: `ddgs>=9` (pip). Sin claves.
5. Valor: alto (busqueda sin coste ni clave), generico, portable.
6. Precio sugerido: ~$12-16.
7. Esfuerzo: bajo (una funcionalidad, sin estado).

### 3.2. `ytdlp-transcript` -> skill `youtube-transcript`

1. Que es: obtencion de transcripciones de YouTube con yt-dlp (subtitulos
   manuales/ASR), sin transcribir audio.
2. Formato actual: servidor MCP (`ytdlp-transcript/server.py`, 235 lineas).
3. Conversion: script CLI `yt_transcript.py` + `SKILL.md`.
4. Requisitos: `yt-dlp` (binario + lib).
5. Valor: medio-alto. Se solapa con `content-matcher` (que lo usa), pero
   como skill base es reutilizable por otros flujos.
6. Precio sugerido: ~$10-14.
7. Esfuerzo: bajo-medio (backoff, idiomas, formatos).

## 4. Receta de conversion MCP -> skill

1. Aislar la logica en una funcion pura por operacion (sin estado de servidor).
2. Exponerla como CLI: `python3 script.py <subcomando> ...` con salida texto.
3. Escribir `SKILL.md`: cuando usarla, prerequisitos, ejemplos, limites.
4. Sanear con `skillpack stage` + `leakcheck` (quitar rutas del entorno).
5. Validar, precir y empaquetar: `validate`, `price`, `pack`.
6. Probar en un proyecto limpio (instalacion real de dependencias).

## 5. Alternativa: vender el MCP como MCP (linea aparte)

1. `MCP Market` es el canal natural; el producto es el servidor, no la skill.
2. Ventaja: es el artefacto original (no hay que reescribir).
3. Desventaja: requiere runtime MCP; menos portable que una skill.
4. Decision pendiente (V+): vender como skill (portable), como MCP (original)
   o ambos.

## 6. Recomendacion

1. Empezar por `ddg-search` -> `web-research` (mayor valor, menor esfuerzo).
2. Seguir con `ytdlp-transcript` -> `youtube-transcript` solo si no canibaliza
   `content-matcher`.
3. **No** usar `github-insight` como SKU propio (no es autoría del dueno).
4. Mantener la linea MCP separada del catalogo de skills.

## 7. Estado

- Analisis: completo (este documento).
- Conversion: **ejecutada (0.4.0)**. `web-research` y `youtube-transcript` estan
  en `staging/`, pasan `validate` + `leakcheck` (0 hallazgos) + `prescan`, y se
  empaquetan en `dist/` como SKUs propios (catalogo 13 -> 15).
- `github-insight`: no convertido (autoría de tercero).

<!-- End Development By Angel Esquivel (Entrepreneur) [SKILLS-MONETIZE 2026] -->
