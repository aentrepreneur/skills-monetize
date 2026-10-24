<!-- ================================================================= -->
<!-- Development By Angel Esquivel (Entrepreneur) [SKILLS-MONETIZE 2026] -->
<!-- ================================================================= -->
<!-- SKILLS-MONETIZE - Pipeline deterministico para empaquetar y vender agent skills propias -->

# PATHS — Caminos de salida para el catálogo

Cinco caminos para llevar las skills al mercado. No son excluyentes: se puede
arrancar por uno y encadenar con otros. Cada camino declara alcance, canal,
esfuerzo y riesgo.

## 1. Cómo leer esto

- **Alcance**: qué SKUs incluye.
- **Canal**: dónde se publica.
- **Esfuerzo**: trabajo adicional sobre lo ya empaquetado.
- **Riesgo**: principal incertidumbre.

Recomendación al final (§7). Los precios son **escenarios** (ver `VALUE.md`),
no hechos.

## 2. Camino A — Pack único (v0.4.0)

- **Alcance**: los 15 SKUs (`dist/`) como **un solo bundle** "Agent Skills Pack".
- **Canal**: marketplace + sitio propio.
- **Esfuerzo**: mínimo — ya está empaquetado en `dist/`.
- **Riesgo**: precio de entrada alto; comprador debe querer todo el set.
- **Ventaja**: salida inmediata; narrativa coherente ("el set completo").

## 3. Camino B — Dos verticales (Ingeniería + Creador)

- **Alcance**:
  1. **Vertical Ingeniería/Dev**: `whitebox-pentest`, `skill-optimizer`,
     `book-to-skill`, `readme-builder`, `licensed-one`, `opencode-agent-creator`,
     `web-research`, `website`, `ocr-texto`.
  2. **Vertical Creador**: `content-matcher`, `niche-validator`, `video-prompts`,
     `youtube-transcript`, `sepia`.
- **Canal**: marketplaces + sitio propio, con dos landings.
- **Esfuerzo**: bajo — el set ya está empaquetado; solo separar y presentar.
- **Riesgo**: dispersión de foco y de audiencia.
- **Ventaja**: amplía el mercado (el creador no es dev) sin diluir el pack
  técnico.

## 4. Camino C — Escalera con lead magnet (funnel)

- **Alcance**: `repo-intelligence` **gratis** (MIT, `price: 0`) como entrada +
  el resto como pago.
- **Canal**: prioritariamente **sitio propio** (control de funnel y datos).
- **Esfuerzo**: bajo — ya está empaquetado como gratis en `dist/`.
- **Riesgo**: la skill gratis debe ser buena y no canibalizar el resto.
- **Ventaja**: convierte tráfico en lista propia; medir conversión real
  (resuelve la variable desconocida).

## 5. Camino D — Línea adyacente Nexus

- **Alcance**:
  1. `nexus-one` como **skill de patrón** (enseñar "proyecto → harness
     desplegable") y/o **licencia del generador** (D3.generator).
  2. `nexus-core` como **licencia/despliegue** aparte (D3), con skill companion
     de despliegue.
- **Canal**: venta directa / consulta (no marketplace de skills).
- **Esfuerzo**: alto — resolver licencia comercial (D3), empaquetado legal,
  kill-switch/fingerprinting.
- **Riesgo**: complejidad legal y técnica; el comprador es más enterprise.
- **Ventaja**: ticket más alto; producto ya existente y maduro.

## 6. Camino E — Servicio pro (no self-serve)

- **Alcance**: vender el **harness como servicio** (setup, auditoría de
  proyecto, pentest white-box) usando las skills como motor interno.
- **Canal**: contacto directo / consultoría.
- **Esfuerzo**: bajo en empaquetado; alto en tiempo humano.
- **Riesgo**: no escala; depende de horas.
- **Ventaja**: ingreso inmediato y alto; valida demanda antes de publicar SKUs.

## 7. Comparación y recomendación

| Camino | Esfuerzo | Riesgo | Ingreso | Escalable |
|---|---|---|---|---|
| A. Pack único | Bajo | Medio | Medio | Sí |
| B. Dos verticales | Medio | Medio | Medio-Alto | Sí |
| C. Escalera / lead magnet | Bajo-Medio | Bajo | Medio | Sí |
| D. Nexus (línea aparte) | Alto | Alto | Alto | Parcial |
| E. Servicio pro | Bajo | Bajo | Alto (por hora) | No |

**Recomendación (arranque):**

1. Publicar **Camino A** (v0.4.0, ya listo) y **Camino C** (`repo-intelligence`
   gratis de entrada) **en el sitio propio** para medir conversión con datos
   propios.
2. En paralelo, **Camino E** si aparece interés directo (valida precio/demanda
   sin costo de empaquetado).
3. Diferir **Camino B** hasta tener señal de demanda; **Camino D** hasta
   resolver licencia D3 y decidir si es línea separada.

**Criterio de decisión (a 30 días):** si el sitio propio con lead magnet
convierte, escalar a B; si no hay tráfico, probar marketplace (A) y servicio (E).

## 8. Preguntas abiertas (requieren V+)

1. ¿Camino A solo, o A + C desde el inicio?
2. ¿Publicar en marketplace, en sitio propio, o ambos?
3. ¿`nexus-one`/`nexus-core` como línea aparte (D) o se quedan fuera de este
   proyecto?

<!-- End Development By Angel Esquivel (Entrepreneur) [SKILLS-MONETIZE 2026] -->
