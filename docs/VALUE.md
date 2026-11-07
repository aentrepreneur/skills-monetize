<!-- ================================================================= -->
<!-- Development By Angel Esquivel (Entrepreneur) [SKILLS-MONETIZE 2026] -->
<!-- ================================================================= -->
<!-- SKILLS-MONETIZE - Pipeline deterministico para empaquetar y vender agent skills propias -->

# VALUE — valor del proyecto skills-monetize

> **Advertencia**: las cifras de ingresos de este documento son **modelos con
> supuestos explicitos**, no pronosticos ni datos de mercado. No se usa ninguna
> cifra de Agensi ni de terceros como hecho (ver `VERACIDAD.md`). Ajustar los
> parametros con datos reales de ventas.

## 1. Que es el "valor" aqui

El proyecto aporta valor en dos ejes:

1. **Valor como herramienta** (interno, inmediato): convierte un proceso manual
   y riesgoso en un comando reproducible.
2. **Valor como negocio** (externo, condicionado): un canal para convertir
   activos de harness en ingreso.

## 2. Valor como herramienta

| Actividad | Manual (estimado) | Con skillpack |
|---|---|---|
| Validar frontmatter + contenido | 5-10 min | < 1 s |
| Pre-scan de seguridad (secretos, patrones) | 10-20 min (o se omite) | < 1 s |
| Empaquetar (zip + listing + manifest) | 10-15 min | < 1 s |
| Fijar precio | 5 min | instantaneo |

Pasos por skill: ~30-45 min → ~1 min. Para **52 skills** el ahorro es
~26 horas equivalenetes (una sola vez). Parametrizable por tarifa horaria.

**Valor de riesgo**: el pre-scan bloquea secretos, `shell=True`, rutas
personales y `.env` antes de publicar. Evita la fuga de una credencial durante
empaquetado, cuyo costo potencial supera cualquier ingreso de este proyecto.

## 3. Costos

| Concepto | Costo |
|---|---|
| Software (stdlib + pytest/ruff/mypy) | $0 |
| Cloudflare Pages/Workers (canal propio) | $0 (free tier) |
| Dominio (opcional) | ~$12/anio |
| Fee Merchant-of-Record (por venta) | ~5% (ya descontado en el neto) |
| Entidad US LLC (opcional) | ~$50-500/anio + Form 5472 |
| Tiempo de desarrollo | ya invertido (no recurrente) |

## 4. Modelo de ingresos por escenarios

Parametros: `N` skills listadas, `S` ventas/skill/mes, `P` precio promedio.
Bruto = `N * S * P`. Neto segun canal (sitio propio MoR ×0.95; Agensi ×0.70).

| Escenario | N | S | P | Bruto/mes | Neto sitio propio | Neto Agensi |
|---|---|---|---|---|---|---|
| Conservador | 8 | 1 | $9 | $72 | ~$68 | ~$50 |
| Base | 12 | 3 | $12 | $432 | ~$410 | ~$302 |
| Optimista | 20 | 8 | $15 | $2,400 | ~$2,280 | ~$1,680 |

Base anualizado (sitio propio): ~**$4,900/anio** neto.

> Estos valores dependen por completo de `S` (ventas/skill/mes), el parametro
> menos conocido. El primer objetivo verificable es medir `S` real durante 30
> dias con un set pequeno.

## 5. ROI y punto de equilibrio

1. **Costo fijo recurrente**: ~$0-12/anio → el punto de equilibrio se alcanza
   con la **primera venta**.
2. **Costo hundido**: tiempo de desarrollo (se amortiza con el primer uso).
3. **Riesgo principal**: `S` puede ser 0 sin traccion. El canal propio y el
   listado gratuito reducen el costo de equivocarse a tiempo, no dinero.

## 6. Valor como activo

1. **Activo reutilizable**: el pipeline empaqueta cualquier skill futura; el
   costo marginal por skill nueva tiende a cero.
2. **Activo de audiencia**: el sitio propio (Cloudflare) captura trafico y
   reduce la dependencia de marketplaces (principio "Audiencia Directa").
3. **Posicionamiento**: enfoque en skills de **harness/DevOps/security**
   (nicho con menos competencia que contenido/marketing en Agensi).
4. **Sin cifra de reventa**: valorar el bundle pipeline+catalogo requeriria
   datos de ingresos reales; no se inventa un multiplo.

## 7. Metodologia

1. Cada numero de ingresos = aritmetica sobre supuestos declarados en la tabla.
2. Ninguna cifra de terceros se trata como hecho.
3. Los precios por defecto provienen de `core/pricing.py` (heuristica
   transparente, ajustable).
4. El tratamiento fiscal (ISR Guatemala) no esta incluido en el neto: es un
   supuesto abierto pendiente de contador.

## 8. Siguiente medicion

1. Publicar el set de 15 (`dist/`) en canal gratuito (`repo-intelligence`) +
   propio.
2. Medir `S` real a 30 dias.
3. Recalcular este documento con `S` observado.

<!-- End Development By Angel Esquivel (Entrepreneur) [SKILLS-MONETIZE 2026] -->
