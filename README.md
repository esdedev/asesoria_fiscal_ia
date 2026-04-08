# Asesoría Fiscal IA — S.L. EdTech / Marketplace Educativo

Sistema de asesoría fiscal, contable y societaria basado en IA para una Sociedad Limitada española del sector EdTech. Diseñado para ser utilizado tanto como referencia directa por humanos como contexto de un LLM (Claude, etc.) para asesoría fiscal automatizada.

## Estado del proyecto

**Pre-constitución.** Los datos de la empresa (NIF, razón social, domicilio fiscal) están pendientes y marcados como `[PENDIENTE]` en `CLAUDE.md`.

## Estructura del repositorio

| Carpeta | Contenido | Cuándo consultar |
|---------|-----------|-----------------|
| `knowledge/legislacion/` | Resúmenes de LIS, LIVA, LIRPF, Ley Startups, SS socios, obligaciones mercantiles | Cuando necesites entender la normativa aplicable |
| `knowledge/internacional/` | Sede de dirección efectiva, CDI, jurisdicciones UE/no-UE, ZEC Canarias | Cuando se plantee fiscalidad fuera de España |
| `knowledge/marketplace-educativo/` | IVA educación, falsos autónomos, flujo de facturación | Cuando haya dudas sobre el modelo de negocio específico |
| `knowledge/plantillas/` | Guías paso a paso de Modelos 303, 200, 202, 111, 190, 347, 390 y requisitos de factura | Cuando toque preparar o presentar un modelo fiscal |
| `operativa/` | Calendario fiscal, checklist trimestral, plan de cuentas PGC PYMES, asientos tipo | Para el día a día de la gestión fiscal y contable |
| `skills/` | Workflows especializados para el LLM (obligaciones fiscales, contabilidad PGC, compliance marketplace, planificación internacional) | Configuración interna del sistema IA |
| `agents/` | Definiciones de agentes (fiscal trimestral, contable, consultor internacional) | Configuración interna del sistema IA |

## Guía rápida

| Necesito... | Consultar |
|-------------|-----------|
| Presentar el IVA trimestral | `knowledge/plantillas/modelo-303-guia.md` + `operativa/checklist-trimestral.md` |
| Saber qué retenciones practicar | `knowledge/plantillas/modelo-111-guia.md` |
| Contabilizar una operación | `operativa/contabilidad/asientos-tipo.md` + `operativa/contabilidad/plan-cuentas-pgc.md` |
| Evaluar riesgo de falsos autónomos | `knowledge/marketplace-educativo/falsos-autonomos-tutores.md` |
| Preparar la declaración de Sociedades | `knowledge/plantillas/modelo-200-guia.md` |
| Saber cuánto pago de Seguridad Social | `knowledge/legislacion/seguridad-social-socios.md` |
| Evaluar mover la empresa fuera de España | `knowledge/internacional/sede-direccion-efectiva.md` |
| Entender el flujo de facturación del marketplace | `knowledge/marketplace-educativo/flujo-facturacion.md` |
| Conocer plazos fiscales | `operativa/calendario-fiscal.md` |

## Configuración IA

El archivo `CLAUDE.md` en la raíz contiene la configuración del sistema: rol, datos de empresa, obligaciones fiscales, fuentes legislativas, vectores de riesgo críticos y directivas de comportamiento. Es el punto de entrada para cualquier LLM que use este repositorio como contexto.

## Índice temático

Ver `knowledge/INDEX.md` para un índice completo organizado por tema y necesidad.
