<!-- Development By Angel Esquivel (Entrepreneur) [SKILLS-MONETIZE 2026] -->

# Guia de lanzamiento manual — Skills Monetize (Fase 2)

Estado: 12 SKUs listos en `dist/`, payloads por canal en `dist/kits/<sku>/channels/`. Nada publicado. Esta guia es el manual de uso completo: cada paso es una accion manual tuya, en orden.

## 1. Contenido del pipeline (ya generado)

| Artefacto | Ubicacion | Uso |
|---|---|---|
| Producto (ZIP) | `dist/<sku>-1.0.0.zip` | Lo que subes a cada canal |
| Listing de venta | `dist/<sku>-1.0.0.listing.md` y `dist/kits/<sku>/LISTING.md` | Texto para el formulario |
| FAQ de soporte | `dist/kits/<sku>/FAQS.md` | Nodo de soporte del canal |
| README comprador | `dist/kits/<sku>/README-BUYER.md` | Seccion "Documentation" del canal |
| Posts sociales | `dist/kits/<sku>/posts/*.md` | Anuncio en X/LinkedIn/Reddit/HN/PH |
| Payload SkillHQ | `dist/kits/<sku>/channels/skillhq.json` | Copiar/pegar en el form de SkillHQ |
| Payload AgentAlley | `dist/kits/<sku>/channels/agentalley.json` | Copiar/pegar en AgentAlley |
| Payload Capafy | `dist/kits/<sku>/channels/capafy.json` | Copiar/pegar en Capafy |
| Caso de prueba Capafy | `dist/kits/<sku>/TEST-CASE.md` | Requisito del alta Capafy |
| Catalogo consolidado | `dist/catalog.json`, `dist/INDEX.md` | Sitio propio / referencia |
| Playbook y calendario | `dist/kits/PLAYBOOK.md`, `LAUNCH-CALENDAR.md` | Cadencia de publicacion |
| Seguimiento | `dist/kits/TRACKING.csv` | Estado por SKU |

## 2. Comandos del pipeline (yo ejecuto, tu decides)

```bash
# Regenerar todo desde staging/ (tras editar una skill)
python3 tools/skillpack.py pack-all staging --out dist
python3 tools/skillpack.py catalog dist                      # -> catalog.json + INDEX.md ($212.40, 12 SKUs)
python3 tools/skillpack.py kit dist --out dist/kits          # kit humano (listing+posts+FAQ)
python3 tools/skillpack.py channel-kits dist --out dist/kits # payloads de los 3 canales
python3 tools/skillpack.py selfcheck staging                 # gate 12/12
```

## 3. Pre-requisitos (una vez)

1. **PayPal**: cuenta que pueda recibir dinero de terceros (Business o Premium). Se usa en SkillHQ y AgentAlley.
2. **Email de soporte**: define `support_email` antes de Capafy (campo en `channels/capafy.json`).
3. **GitHub**: los 3 canales loguean con GitHub.
4. **Pricing**: usa el `price_usd` de cada `channels/*.json` (viene del manifest).

## 4. Orden de publicacion

### 4.1 SkillHQ (empieza aqui — es el mas rapido)
1. Login con GitHub en skillhq.
2. Submit skill → coloca el contenido de `channels/skillhq.json` en los campos (title/description/tags/price).
3. Sube el ZIP `dist/<sku>-1.0.0.zip`.
4. Live tras aprobacion. Payout 80% por PayPal on-demand desde EUR 20.
5. DAC7: reporte si superas EUR 2.000 o 30 transacciones por ano.

### 4.2 AgentAlley (descubrimiento)
1. Vendor account con GitHub.
2. Submit con `channels/agentalley.json` + `LISTING.md`.
3. Revision humana 24-48h.
4. Payout 70% por PayPal el dia 10; minimo USD 50; hold 30 dias.
5. El catálogo gratuito del canal da descubrimiento: deja 1-2 SKUs o versiones light gratis si pide introduccion.

### 4.3 Capafy (banco GT)
1. Registrar Publisher; alta de Skill (cuota de certificacion USD 0.99).
2. Modelo **Download** en todos los SKUs (no Subscription: pierdes porque pagas tokens de LLM).
3. Completa `TEST-CASE.md` (input y output real copiado del agente).
4. Completa `support_email` y `agent_card` en `channels/capafy.json`.
5. Statement: no enviar datos fuera del host; EULA ya cumplimiento con Schedule C.
6. Configura payout (banco GT/BAM) en el Publisher Console y verifica metodo exacto para Guatemala antes de fijar precios.
7. Payout mensual desde el dia 15; minimo USD 100; ventana de disputa 7 dias.
8. Impuestos: MoR para indirectos; ISR local sigue siendo tuyo (fondo a contador GT).

## 5. Reglas fijas (no negociables)

- No publicar SKUs de pago en repos publicos de GitHub (skillsmk indexa gratis).
- Sepia NO es vendible: es MIT de Nanako0129 (copia 0.4.0 literal). Esta en `.excluded/sepia-0.4.0/`.
- skill-optimizer y opencode-agent-creator excluidos (autor terceros/verificar).
- Cobro: ISR de Guatemala sobre ingresos — valida con contador los tratados de doble tributacion y registro RADIAN.
- Fuera de los 3 canales, evitar cualquier MoR que pague solo por Stripe Connect (no opera en GT).

## 6. Ventas esperadas (marcos)

- Lanzamiento: los listings y precios del manifest ($212.40 total catalogo).
- Metricas a 30 dias: ventas por canal, refunds, primer payout recibido (PayPal y banco).
- Decisión: si Capafy banca funciona con buen fee, sube prioridad vs AgentAlley.

## 7. Checklist de submit por SKU (por cada canal)

- [ ] ZIP existe y la version matchea el manifest
- [ ] LICENSE + EULA en el paquete
- [ ] titulo/description/tags = `channels/<canal>.json`
- [ ] precio = `price_usd` del payload
- [ ] screenshot/preview subido (si el canal lo pide)
- [ ] TEST-CASE.md completado (solo Capafy)
- [ ] support_email definido (solo Capafy)

<!-- Development By Angel Esquivel (Entrepreneur) [SKILLS-MONETIZE 2026] -->
