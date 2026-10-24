<!-- ================================================================= -->
<!-- Development By Angel Esquivel (Entrepreneur) [SKILLS-MONETIZE 2026] -->
<!-- ================================================================= -->
<!-- SKILLS-MONETIZE - Pipeline deterministico para empaquetar y vender agent skills propias -->

# CHANNELS — canales de publicacion y rutas de cobro

> Estado: **cobro diferido por decision** (2026-10-16). Este documento registra
> la matriz evaluada para decidir cuando exista traccion o cuando el contador
> confirme el tratamiento fiscal.

## 1. Canales de publicacion

| Canal | Modelo | Split creador | Fuente al comprador | Subida |
|---|---|---|---|---|
| Agensi | Venta unica + subs | ~70% | No (corre en agente) | Manual |
| PromptBase | Venta unica | 80% marketplace / 100% enlace propio | Si (texto completo) | Manual |
| MCP Market | Directorio | Listados destacados de pago | Si (install local) | Manual |
| Sitio propio | Venta directa | ~95% (solo fee MoR) | Configurable | Automatizable |

Notas del ToS de Agensi relevantes:
1. Prohibido enlazar ventas fuera de la plataforma (§6.3a).
2. La plataforma puede cambiar el split con 30 dias de aviso (§7.1).
3. No se puede excluir la skill de la distribucion por agente/créditos (§6.5).
4. Rechazan skills reempaquetadas de terceros sin originalidad (§6.4).

## 2. Rutas de cobro para Guatemala

Stripe no opera en Guatemala. Rutas evaluadas (implementadas en
`integrations/payout.py`):

| id | Compatible GT | Fiscal | Friccion |
|---|---|---|---|
| `stripe_connect` | No | No aplica | Requiere entidad en pais soportado |
| `usdc_zoneless` | Si | ISR local (cripto: validar) | Procesador tercero no probado |
| `paypal` | Si | ISR local | Comision FX; retiro a banco/BAM |
| `lemonsqueezy` | Si | MoR gestiona VAT/sales tax; ISR local aparte | Comision por venta |
| `gumroad` | Si | MoR gestiona VAT/sales tax; ISR local aparte | Comision flat; fee de payout |
| `us_llc_stripe` | Si (via entidad US) | No reduce ISR; exige Form 5472 | Costo de LLC + cumplimiento |

## 3. Recomendacion provisional

1. **Recepcion**: PayPal (Guatemala soportado a nivel "enviar/recibir/retirar";
   BAM habilito retiro directo).
2. **Canal propio con Merchant-of-Record**: LemonSqueezy — la plataforma
   recauda y remite VAT/sales tax global; payout a PayPal. Maximiza margen.
3. **Agensi**: listado gratuito para trafico; canal pagado diferido.
4. **US LLC**: solo si el volumen justifica desbloquear Stripe Connect; no es
   un ahorro fiscal.

## 4. Pendientes (V+)

1. Confirmar ISR/crypto con contador.
2. Verificar soporte de payout de LemonSqueezy/Gumroad para Guatemala
   (via PayPal) al momento de suscribir.
3. Definir si se forma entidad en EE.UU.

<!-- End Development By Angel Esquivel (Entrepreneur) [SKILLS-MONETIZE 2026] -->
