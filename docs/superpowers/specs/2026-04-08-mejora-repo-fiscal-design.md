# Mejora integral del repositorio de asesoría fiscal IA

**Fecha:** 2026-04-08
**Estado:** Pre-constitución de la S.L.
**Objetivo:** Convertir el repo de base de conocimiento en un sistema operativo y navegable, tanto para consulta humana directa como para uso por LLM como contexto de asesoría fiscal automatizada.

---

## Fase 1: Navegabilidad

### README.md (raíz)

Contenido:
- Descripción en una línea: sistema de asesoría fiscal IA para S.L. EdTech/marketplace educativo
- Estructura de carpetas con descripción de cada una:
  - `knowledge/` — base de conocimiento legislativo y específico del negocio
  - `operativa/` — calendarios, checklists trimestrales, contabilidad
  - `skills/` — workflows especializados para el LLM
  - `agents/` — definiciones de agentes con roles diferenciados
- Flujo de uso: tabla "si necesitas X → consulta Y"
- Estado del proyecto: pre-constitución, datos pendientes marcados con [PENDIENTE] en CLAUDE.md

### knowledge/INDEX.md

Índice temático organizado por necesidad/pregunta, no por carpeta:
- Sección IVA: qué archivos consultar para dudas de IVA (educación, autorepercutión, modelo 303)
- Sección IS: archivos de impuesto de sociedades (LIS, modelo 200, ERD, Ley Startups)
- Sección IRPF/Retenciones: modelo 111, nóminas administradores
- Sección Marketplace: falsos autónomos, flujo facturación, IVA educación
- Sección Internacional: sede dirección efectiva, CDI, jurisdicciones, ZEC
- Sección Operativa: calendario fiscal, checklist trimestral, plan de cuentas, asientos tipo

Cada entrada: título descriptivo + ruta al archivo + una línea de contexto.

---

## Fase 2: Robustez IA

### Reglas de escalación en agentes

Añadir sección `LÍMITES Y ESCALACIÓN` en los 3 archivos de `agents/`:

Criterios comunes (adaptar por agente):
- Operaciones que superen 50.000 EUR o impliquen operaciones vinculadas (Art. 18 LIS) → derivar a asesor
- Duda interpretativa entre artículos o normativa contradictoria → exponer ambas posturas, recomendar consulta vinculante a la DGT
- Datos insuficientes para calcular → listar exactamente qué datos faltan, no estimar
- Temas fuera de ámbito fiscal (laboral complejo, mercantil litigioso) → derivar a abogado especialista
- Situaciones con posible inspección en curso → derivar inmediatamente

Criterios específicos por agente:
- `fiscal-trimestral.md`: si las cifras no cuadran entre modelos (303 vs 390, 111 vs 190) → no presentar, revisar
- `contable.md`: si el balance de sumas y saldos no cuadra → parar y diagnosticar antes de cerrar
- `consultor-internacional.md`: si hay sustancia económica dudosa en la jurisdicción destino → advertir riesgo de fraude de ley (Art. 15 LGT)

### Protocolo de datos incompletos

Nuevo archivo: `operativa/protocolo-datos-incompletos.md`

Contenido:
- Directiva principal: "NUNCA estimar importes. Si no tienes el dato exacto, pídelo."
- Checklist de datos mínimos por tipo de consulta:
  - IVA trimestral: facturas emitidas (base + IVA), facturas recibidas (base + IVA deducible), facturas intracomunitarias
  - IS anual: resultado contable, ajustes extracontables, bases imponibles negativas pendientes, deducciones aplicables
  - Retenciones: nóminas emitidas, facturas de profesionales, tipo de retención aplicado
  - Internacional: residencia fiscal de todos los socios, jurisdicción destino, sustancia económica prevista
- Formato estándar para solicitar datos: "Para responder necesito: [lista numerada de datos exactos]. Por favor proporciona cada uno."

### Disclaimer en CLAUDE.md

Añadir nueva directiva (nº 9) en CORE DIRECTIVES:
- "Toda respuesta fiscal debe incluir: (a) base legal citada con artículo específico, (b) si la respuesta implica cálculo o planificación con importes >10.000 EUR o complejidad media-alta, recomendar confirmación con asesor fiscal colegiado."

---

## Fase 3: Contenido incompleto

### Completar guías de modelos fiscales

**modelo-111-guia.md** — elevar al nivel de modelo-303-guia.md:
- Quién está obligado a presentarlo (retenedores)
- Tipos de retención: trabajo personal (nómina), profesionales (tutores), administradores
- Desglose de casillas con ejemplo numérico usando datos del marketplace:
  - 2 administradores con nómina
  - N tutores con facturas de servicios profesionales (15% retención, 7% si nuevos)
- Plazo y forma de presentación
- Relación con modelo 190 (resumen anual)

**modelo-202-guia.md** — elevar al nivel de modelo-200-guia.md:
- Obligados: sociedades con IS positivo en el ejercicio anterior
- Primer ejercicio: no hay obligación si no hay cuota anterior
- Cálculo: 18% de la casilla 599 del modelo 200 del ejercicio anterior
- Ejemplo numérico partiendo del ejemplo del modelo-200 existente
- Plazos: abril (1-20), octubre (1-20), diciembre (1-20)
- Exención primer ejercicio como punto clave para la S.L. nueva

**modelo-111-190-347-390-factura.md** — reorganizar como guía de trazabilidad documental:
- Matriz: qué documento (factura emitida, recibida, nómina, certificado retención) alimenta qué modelo
- Flujo: factura → libro registro → modelo trimestral → modelo anual
- Obligaciones de conservación (Art. 29 LGT): 4 años

### Nueva guía: nóminas y retenciones de administradores

Nuevo archivo: `knowledge/legislacion/nominas-retenciones-administradores.md`

Contenido:
- Obligación de nómina para administradores con funciones de dirección
- Retención administradores: 35% con carácter general (Art. 101.2 RIRPF), 19% si entidad con cifra de negocios <100.000 EUR en ejercicio anterior
- Para la S.L. nueva: aplicar 19% el primer ejercicio si cumple ERD
- Cotización RETA: obligatoria para socios administradores con >25% (o >33% si trabajan). Los 2 co-CEOs con 45% cada uno → RETA obligatorio
- Base mínima RETA 2026: verificar contra tabla vigente
- Asientos contables: añadir en `operativa/contabilidad/asientos-tipo.md` los asientos de nómina de administrador (cuenta 640, 4751, 476, 465, 572)

### Actualizar Verifactu / Facturación electrónica

Nuevo archivo: `knowledge/legislacion/verifactu-facturacion-electronica.md`

Contenido:
- Marco normativo: RD 1007/2023 (Reglamento Verifactu) + Orden HAC/1177/2024
- Calendario de implantación:
  - Desarrolladores de software: obligados desde julio 2025 a tener sistemas adaptados
  - Empresarios y profesionales: obligación de usar sistemas Verifactu (fecha según facturación — verificar calendario definitivo publicado)
- Qué implica para la S.L.: el software de facturación (Holded u otro) debe cumplir requisitos Verifactu
- Requisitos técnicos esenciales: registro de facturación, hash encadenado, envío a AEAT
- Acción requerida: al constituir la S.L., verificar que el software de facturación elegido es compatible con Verifactu

---

## Fuera de alcance (YAGNI)

- Plantillas de contratos de intermediación con tutores (trabajo jurídico)
- Jurisprudencia adicional más allá de la ya documentada
- Guía de prorrata IVA (irrelevante para el modelo de negocio)
- Guía de facturación electrónica B2G (la S.L. no factura a administraciones públicas)
- Integración con software específico (Holded, A3, etc.) — documentar requisitos, no implementar
