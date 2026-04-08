# Mejora Integral del Repo Fiscal IA — Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Make the fiscal advisory repo navigable for humans, robust for LLM usage (with guardrails and escalation), and complete the thin content areas.

**Architecture:** Three sequential phases — (1) navegabilidad adds a README and INDEX, (2) robustez IA adds escalation rules to agents, a data protocol, and a disclaimer directive, (3) contenido completes guides and adds new ones. All work is markdown authoring with no code.

**Tech Stack:** Markdown, Git

---

## Phase 1: Navegabilidad

### Task 1: Create README.md

**Files:**
- Create: `README.md`

- [ ] **Step 1: Write README.md**

```markdown
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
```

- [ ] **Step 2: Commit**

```bash
git add README.md
git commit -m "docs: add README with repo structure and quick reference guide"
```

---

### Task 2: Create knowledge/INDEX.md

**Files:**
- Create: `knowledge/INDEX.md`

- [ ] **Step 1: Write knowledge/INDEX.md**

```markdown
# Índice Temático — Base de Conocimiento Fiscal

Índice organizado por tema. Cada entrada apunta al archivo relevante con una descripción breve.

---

## IVA (Impuesto sobre el Valor Añadido)

- [Modelo 303 — Autoliquidación trimestral](plantillas/modelo-303-guia.md) — Cálculo paso a paso con casillas, ejemplo práctico con comisiones y autorepercusión
- [Modelo 390 — Resumen anual IVA](plantillas/modelo-111-190-347-390-factura.md#guía-modelo-390--resumen-anual-iva) — Consolidación de los 4 trimestres, verificación de cuadre
- [IVA en educación y exenciones](marketplace-educativo/iva-educacion-exenciones.md) — Art. 20.Uno.9º y 10º LIVA: cuándo aplica la exención y cuándo no (la S.L. como intermediario NO está exenta)
- [Flujo de facturación](marketplace-educativo/flujo-facturacion.md) — Posición IVA neta por transacción según tutor exento/no exento

## IS (Impuesto sobre Sociedades)

- [LIS — Impuesto sobre Sociedades](legislacion/lis-impuesto-sociedades.md) — Resumen de la Ley 27/2014: tipos, deducciones, ERD, gastos no deducibles
- [Modelo 200 — Declaración anual IS](plantillas/modelo-200-guia.md) — Cálculo completo: resultado contable → ajustes → base imponible → liquidación, con ejemplo numérico
- [Modelo 202 — Pago fraccionado IS](plantillas/modelo-202-guia.md) — Dos modalidades (Art. 40.2 y 40.3 LIS), primer ejercicio = 0€
- [Ley de Startups 2022](legislacion/ley-startups-2022.md) — IS al 15% durante 4 años, requisitos Art. 3, inscripción ENISA

## IRPF y Retenciones

- [Modelo 111 — Retenciones trimestrales](plantillas/modelo-111-guia.md) — Retenciones sobre nóminas, profesionales y administradores, con ejemplo y tipos aplicables
- [Modelo 190 — Resumen anual retenciones](plantillas/modelo-111-190-347-390-factura.md#guía-modelo-190--resumen-anual-de-retenciones-irpf) — Claves de percepción, formato, verificación con 111
- [IRPF de los socios](legislacion/irpf-socios.md) — Tres vías de cobro (nómina, factura, dividendos) con comparativa fiscal detallada
- [Nóminas y retenciones de administradores](legislacion/nominas-retenciones-administradores.md) — Retención fija 35%/19%, cotización RETA, asientos contables

## Seguridad Social

- [Seguridad Social de los socios](legislacion/seguridad-social-socios.md) — RETA autónomo societario, cuotas, tarifa plana, timing del alta

## Marketplace Educativo (específico del negocio)

- [Falsos autónomos — tutores](marketplace-educativo/falsos-autonomos-tutores.md) — Indicios de laboralidad, STS 25/09/2020, mitigación del riesgo
- [IVA en educación](marketplace-educativo/iva-educacion-exenciones.md) — Exenciones y su (in)aplicabilidad al marketplace
- [Flujo de facturación](marketplace-educativo/flujo-facturacion.md) — Arquitectura de cobros/pagos, documentos fiscales por transacción, asientos

## Fiscalidad Internacional

- [Sede de dirección efectiva](internacional/sede-direccion-efectiva.md) — Art. 8.1 LIS, jurisprudencia, requisitos de sustancia
- [Jurisdicciones UE](internacional/jurisdicciones-eu.md) — Estonia, Irlanda, Portugal, Chipre: análisis por jurisdicción
- [Jurisdicciones no-UE](internacional/jurisdicciones-non-eu.md) — Dubai, otros: análisis por jurisdicción
- [Convenios de doble imposición](internacional/convenios-doble-imposicion.md) — CDI aplicables, retenciones, eliminación de doble imposición
- [ZEC Canarias](internacional/zec-canarias.md) — IS al 4%, requisitos de empleo e inversión

## Obligaciones Mercantiles y Facturación

- [Obligaciones mercantiles](legislacion/obligaciones-mercantiles.md) — Cuentas anuales, Registro Mercantil, libros obligatorios
- [Requisitos legales de factura](plantillas/modelo-111-190-347-390-factura.md#requisitos-legales-de-factura-en-españa-rd-16192012) — RD 1619/2012: contenido obligatorio, facturas simplificadas, plazos, series
- [Modelo 347 — Operaciones con terceros](plantillas/modelo-111-190-347-390-factura.md#guía-modelo-347--operaciones-con-terceros-300506) — Umbral >3.005,06€, relevancia para tutores y proveedores
- [Verifactu — Facturación electrónica](legislacion/verifactu-facturacion-electronica.md) — RD 1007/2023, calendario de implantación, requisitos técnicos

## Operativa y Contabilidad

- [Calendario fiscal](../operativa/calendario-fiscal.md) — Mes a mes con alertas y plazos
- [Checklist trimestral](../operativa/checklist-trimestral.md) — 8 pasos para cerrar el trimestre fiscal
- [Plan de cuentas PGC PYMES](../operativa/contabilidad/plan-cuentas-pgc.md) — Cuentas adaptadas al marketplace educativo
- [Asientos tipo](../operativa/contabilidad/asientos-tipo.md) — Constitución, operativa diaria, gastos, liquidaciones, cierre
```

- [ ] **Step 2: Commit**

```bash
git add knowledge/INDEX.md
git commit -m "docs: add thematic index for knowledge base navigation"
```

---

## Phase 2: Robustez IA

### Task 3: Add escalation rules to fiscal-trimestral agent

**Files:**
- Modify: `agents/fiscal-trimestral.md` (append after line 108)

- [ ] **Step 1: Add LÍMITES Y ESCALACIÓN section**

Append the following at the end of `agents/fiscal-trimestral.md`:

```markdown

## LÍMITES Y ESCALACIÓN

### Cuándo PARAR y pedir datos
- Si el usuario no ha proporcionado facturas emitidas y recibidas del trimestre → NO calcular. Pedir los datos exactos.
- Si hay facturas intracomunitarias/extracomunitarias y no se sabe el importe → NO estimar. Pedir desglose.
- NUNCA estimar importes. Si falta un dato, listar exactamente qué se necesita.

### Cuándo DERIVAR a asesor humano
- Si las cifras del 303 no cuadran con el 390 acumulado → no presentar. Pedir revisión contable.
- Si las retenciones del 111 no cuadran con las facturas de profesionales → parar y diagnosticar.
- Si el resultado del trimestre es inusualmente alto o bajo respecto al anterior (variación >50%) → advertir y recomendar revisión.
- Si hay operaciones vinculadas (Art. 18 LIS) con importes >50.000€ → derivar a asesor fiscal.
- Si hay una inspección o requerimiento en curso de AEAT → derivar inmediatamente a asesor fiscal y abogado tributarista.

### Cuándo ADVERTIR
- Si se detecta que no se ha autorepercutido IVA en servicios UE/extra-UE → advertir antes de calcular.
- Si el usuario quiere compensar IVA sin arrastrar correctamente la casilla 67 → bloquear y explicar.
- Si es el primer ejercicio y el usuario intenta presentar el 202 con importe >0€ → verificar que hay IS anterior.
```

- [ ] **Step 2: Commit**

```bash
git add agents/fiscal-trimestral.md
git commit -m "feat: add escalation and guardrail rules to fiscal-trimestral agent"
```

---

### Task 4: Add escalation rules to contable agent

**Files:**
- Modify: `agents/contable.md` (append after line 139)

- [ ] **Step 1: Add LÍMITES Y ESCALACIÓN section**

Append the following at the end of `agents/contable.md`:

```markdown

## LÍMITES Y ESCALACIÓN

### Cuándo PARAR y pedir datos
- Si el usuario describe una operación sin importes concretos → NO registrar asiento con importes estimados. Pedir cifras exactas.
- Si no se conoce el tipo de IVA aplicable (¿exento? ¿21%? ¿inversión sujeto pasivo?) → preguntar antes de contabilizar.
- Si el asiento no cuadra (debe ≠ haber) → NUNCA forzar el cuadre. Revisar la lógica de la operación.

### Cuándo DERIVAR a asesor humano
- Si el balance de sumas y saldos no cuadra al cierre → parar y diagnosticar antes de cerrar el ejercicio.
- Si hay discrepancias en la conciliación bancaria que no se pueden explicar → derivar a contable humano.
- Si se detectan operaciones vinculadas (socios ↔ S.L.) con importes significativos (>10.000€) → advertir sobre obligación de documentación de precios de transferencia (Art. 18 LIS).
- Si el usuario pide contabilizar una operación que parece irregular (pagos sin factura, facturas sin contraprestación real) → advertir del riesgo y recomendar consulta.
- Si hay dudas sobre la calificación contable (¿gasto o inversión? ¿provisión o contingencia?) con impacto >5.000€ → recomendar confirmación con contable colegiado.

### Cuándo ADVERTIR
- Si se registra un gasto sin factura soporte → advertir que no será deducible en IS (Art. 106 LGT).
- Si la amortización acelerada ERD supera los límites legales → corregir automáticamente.
- Si el resultado del ejercicio es negativo y se intenta dotar reserva legal → bloquear (solo se dota con beneficios).
```

- [ ] **Step 2: Commit**

```bash
git add agents/contable.md
git commit -m "feat: add escalation and guardrail rules to contable agent"
```

---

### Task 5: Add escalation rules to consultor-internacional agent

**Files:**
- Modify: `agents/consultor-internacional.md` (append after line 148)

- [ ] **Step 1: Add LÍMITES Y ESCALACIÓN section**

Append the following at the end of `agents/consultor-internacional.md`:

```markdown

## LÍMITES Y ESCALACIÓN

### Cuándo PARAR y pedir datos
- Si no se ha respondido la primera pregunta obligatoria (residencia fiscal de los 3 socios) → NO analizar ninguna jurisdicción. Insistir en obtener esta información.
- Si el usuario pregunta por una jurisdicción no cubierta en la base de conocimiento → advertir que el análisis puede ser incompleto y recomendar asesor especializado en esa jurisdicción.

### Cuándo DERIVAR a asesor humano
- Si hay sustancia económica dudosa en la jurisdicción destino → advertir del riesgo de fraude de ley (Art. 15 LGT) y simulación (Art. 16 LGT). Derivar a abogado tributarista.
- Si la operación implica exit tax (Art. 19.1 LIS) con plusvalías latentes >50.000€ → derivar a asesor fiscal internacional para cuantificación exacta.
- Si se plantea una estructura multi-jurisdiccional (holding, filiales, IP box) → derivar. La complejidad excede la capacidad de asesoría automatizada.
- Si hay una inspección de AEAT o requerimiento sobre residencia fiscal → derivar inmediatamente a abogado tributarista.
- Si se plantean precios de transferencia entre entidades vinculadas en distintas jurisdicciones → derivar a especialista en transfer pricing.

### Cuándo ADVERTIR
- Si el usuario quiere constituir en el extranjero sin que ningún socio resida allí → advertir que es una estructura sin sustancia y con riesgo de sede de dirección efectiva en España (Art. 8.1 LIS).
- Si la motivación es exclusivamente fiscal (sin motivo económico real) → advertir del riesgo de planificación fiscal agresiva (Directiva DAC6, Ley 10/2014).
- Si el ahorro fiscal estimado es <3.000€/año → recomendar no cambiar. El coste de estructura y compliance supera el ahorro.
```

- [ ] **Step 2: Commit**

```bash
git add agents/consultor-internacional.md
git commit -m "feat: add escalation and guardrail rules to consultor-internacional agent"
```

---

### Task 6: Create protocolo-datos-incompletos.md

**Files:**
- Create: `operativa/protocolo-datos-incompletos.md`

- [ ] **Step 1: Write protocolo-datos-incompletos.md**

```markdown
# Protocolo de Datos Incompletos

## Directiva principal

**NUNCA estimar importes. Si no tienes el dato exacto, pídelo antes de calcular.**

Este protocolo aplica a todos los agentes (fiscal trimestral, contable, consultor internacional). Cuando el usuario solicita un cálculo fiscal, contable o de planificación, verificar que se dispone de todos los datos mínimos antes de responder.

---

## Datos mínimos por tipo de consulta

### IVA trimestral (Modelo 303)
1. Total facturas emitidas del trimestre (base imponible por tipo de IVA: 21%, 10%, 4%)
2. Total IVA repercutido del trimestre
3. Total facturas recibidas del trimestre (base imponible + IVA soportado deducible)
4. Facturas intracomunitarias con inversión sujeto pasivo (base + identificación del proveedor)
5. Facturas extracomunitarias con inversión sujeto pasivo (base + identificación del proveedor)
6. IVA a compensar de trimestres anteriores (casilla 67 del 303 anterior, si aplica)
7. ¿Es el 4T? → ¿Se solicita devolución o compensación?

### Retenciones trimestrales (Modelo 111)
1. Nóminas brutas pagadas en el trimestre (si hay empleados o administradores con nómina)
2. Retenciones IRPF practicadas sobre nóminas (tipo aplicado a cada perceptor)
3. Facturas de profesionales autónomos pagadas en el trimestre (base + retención practicada)
4. Número de perceptores por categoría (trabajo, profesionales, administradores)

### Pago fraccionado IS (Modelo 202)
1. ¿Es el primer ejercicio de la S.L.? → Si sí, el pago es 0€ (Art. 40.2 LIS)
2. Si no es el primer ejercicio (modalidad Art. 40.2): cuota íntegra del último Modelo 200 presentado
3. Si se ha optado por modalidad Art. 40.3: resultado contable provisional del período actual

### Declaración anual IS (Modelo 200)
1. Balance de situación a 31 de diciembre (exportado de Holded)
2. Cuenta de Pérdidas y Ganancias del ejercicio completo
3. Pagos fraccionados (Modelos 202) presentados durante el año
4. Retenciones soportadas durante el año
5. Gastos de I+D+i del ejercicio (si se pretende aplicar deducción Art. 35 LIS)
6. Bases imponibles negativas de ejercicios anteriores pendientes de compensar
7. Operaciones con vinculadas (socios ↔ S.L.) y sus importes
8. ¿Se ha distribuido dividendos? ¿Se cumple ERD? ¿Hay inscripción Ley Startups?

### Consulta contable (registro de asiento)
1. Tipo de operación (venta, compra, gasto, nómina, liquidación)
2. Importe exacto de la operación
3. IVA aplicable (tipo, exento, inversión sujeto pasivo)
4. Retención IRPF aplicable (si la hay)
5. Fecha de la operación
6. Medio de pago (banco, Stripe, efectivo)

### Consulta internacional
1. Residencia fiscal actual de los 3 socios (país + situación: residente fiscal, nómada, dual)
2. Jurisdicción destino que se quiere evaluar
3. Previsión de ingresos anuales de la S.L.
4. ¿Los socios se mudarían realmente o solo quieren constituir allí?
5. ¿Hay sustancia económica real en el destino? (oficina, empleados, clientes)

---

## Formato estándar para solicitar datos

Cuando falten datos, responder con este formato:

```
Para responder a tu consulta necesito los siguientes datos:

1. [Dato concreto que falta]
2. [Dato concreto que falta]
3. [Dato concreto que falta]

Por favor proporciona cada uno. Si algún dato no está disponible, indícalo y te explico cómo obtenerlo.
```

## Reglas de conducta

1. **No inventar datos**: Si falta el importe de IVA soportado, no asumir un porcentaje medio. Pedir el dato.
2. **No redondear por conveniencia**: Los importes fiscales van con céntimos. No redondear a cifras "limpias".
3. **No asumir el tipo de IVA**: Si no se sabe si un gasto lleva 21%, 10%, o es exento, preguntar.
4. **No asumir la retención**: Si no se sabe si el profesional es nuevo autónomo (7%) o veterano (15%), preguntar.
5. **Alertar de datos sospechosos**: Si un importe parece anómalo (ej: comisiones de Stripe de 500€ en un mes con 200€ de ingresos), alertar antes de contabilizar.
```

- [ ] **Step 2: Commit**

```bash
git add operativa/protocolo-datos-incompletos.md
git commit -m "feat: add incomplete data protocol for AI guardrails"
```

---

### Task 7: Add directive 9 to CLAUDE.md

**Files:**
- Modify: `CLAUDE.md` (after line 62, the current directive 8)

- [ ] **Step 1: Add directive 9**

After the line `8. Advertir siempre de plazos próximos según el calendario fiscal.`, add:

```
9. Toda respuesta fiscal debe incluir: (a) base legal citada con artículo específico, (b) si la respuesta implica cálculo o planificación con importes >10.000€ o complejidad media-alta, recomendar confirmación con asesor fiscal colegiado.
```

- [ ] **Step 2: Commit**

```bash
git add CLAUDE.md
git commit -m "feat: add directive 9 — mandatory legal citation and advisor referral for complex queries"
```

---

## Phase 3: Contenido

### Task 8: Enhance modelo-111-guia.md with administradores section

**Files:**
- Modify: `knowledge/plantillas/modelo-111-guia.md` (append after line 82)

The current guide covers tutores well but lacks detail on administradores with nómina, which will be relevant when the S.L. starts paying the co-CEOs.

- [ ] **Step 1: Add administradores section**

Append the following at the end of `knowledge/plantillas/modelo-111-guia.md`:

```markdown

## Retenciones a administradores (cuando haya nómina)

Cuando los co-CEOs cobren nómina como administradores de la S.L., las retenciones se declaran en este mismo modelo 111.

### Tipo de retención para administradores
- **General: 35%** (Art. 101.2 RIRPF)
- **Reducido: 19%** si la cifra de negocios del ejercicio anterior <100.000€ (Art. 101.2.b RIRPF)
- Para la S.L. nueva con Ley Startups + ERD: aplicar **19%** en los primeros ejercicios

### Ejemplo práctico — Trimestre con tutores + nómina administradores

#### Datos:
- 2 administradores con nómina bruta mensual: 1.500€/mes × 3 meses = 4.500€ cada uno
- Retención IRPF administradores: 19% (cifra negocio <100.000€)
- 5 tutores autónomos con facturas totales: 4.000€ (retención 15%)

#### Cálculo:
```
RENDIMIENTOS DEL TRABAJO (administradores):
Casilla 01: 2 (nº perceptores)
Casilla 02: 9.000€ (2 × 4.500€)
Casilla 03: 1.710€ (19% de 9.000€)

ACTIVIDADES PROFESIONALES (tutores):
Casilla 07: 5 (nº perceptores)
Casilla 08: 4.000€ (base)
Casilla 09: 600€ (15% de 4.000€)

RESULTADO:
Casilla 28: 2.310€ (1.710 + 600)
Casilla 30: 2.310€ A INGRESAR
```

### Relación con el Modelo 190 (resumen anual)

Al cerrar el año, el Modelo 190 incluirá:
- Administradores con clave **B.01** (rendimientos del trabajo — administradores)
- Tutores con clave **G.01** (actividades profesionales) o **G.02** (nuevos autónomos al 7%)
- La suma anual de retenciones del 190 debe coincidir con la suma de los 4 Modelos 111
```

- [ ] **Step 2: Commit**

```bash
git add knowledge/plantillas/modelo-111-guia.md
git commit -m "feat: add administradores retention section to modelo 111 guide"
```

---

### Task 9: Add trazabilidad documental to modelo-111-190-347-390-factura.md

**Files:**
- Modify: `knowledge/plantillas/modelo-111-190-347-390-factura.md` (prepend before line 1)

- [ ] **Step 1: Add trazabilidad matrix at the beginning of the file**

Insert the following at the very beginning of `knowledge/plantillas/modelo-111-190-347-390-factura.md`, before the existing content:

```markdown
# Trazabilidad Documental — De la Factura al Modelo Fiscal

## Matriz: qué documento alimenta qué modelo

| Documento | Modelo trimestral | Modelo anual | Observación |
|-----------|------------------|--------------|-------------|
| Factura emitida a estudiante | 303 (IVA repercutido) | 390 | Base + cuota IVA |
| Factura recibida de tutor (con IRPF) | 303 (IVA soportado) + 111 (retención) | 390 + 190 | Si tutor exento IVA → solo 111 |
| Factura recibida proveedor nacional | 303 (IVA soportado) | 390 | Solo IVA deducible |
| Factura proveedor UE (Stripe, AWS) | 303 (autorepercusión casillas 10-11 + 30-31) | 390 | Inversión sujeto pasivo |
| Factura proveedor extra-UE (Anthropic) | 303 (autorepercusión casillas 10-11 + 30-31) | 390 | Art. 84.Uno.2º LIVA |
| Nómina administrador | 111 (retención IRPF trabajo) | 190 (clave B.01) | SS por separado |
| Certificado retención a profesional | — | 190 | Se emite al cierre del año |
| Total operaciones >3.005,06€ con un tercero | — | 347 | IVA incluido |

## Flujo documental

```
Factura/Nómina → Libro Registro (IVA emitidas/recibidas) → Modelo trimestral (303/111) → Modelo anual (390/190/347)
```

### Obligaciones de conservación
- **Tributaria (Art. 70 LGT)**: 4 años (plazo de prescripción)
- **Mercantil (Art. 30 CCom)**: 6 años desde el último asiento del ejercicio
- **Recomendación**: conservar 6 años. Holded los conserva automáticamente en la nube, pero mantener backup.

---

```

- [ ] **Step 2: Commit**

```bash
git add knowledge/plantillas/modelo-111-190-347-390-factura.md
git commit -m "feat: add document traceability matrix to fiscal models guide"
```

---

### Task 10: Create nominas-retenciones-administradores.md

**Files:**
- Create: `knowledge/legislacion/nominas-retenciones-administradores.md`

This file complements `irpf-socios.md` (which covers how socios receive money) and `seguridad-social-socios.md` (which covers SS obligations). This new file focuses specifically on the mechanics of administrador payroll: how to set up the nómina, what to retain, and how it connects to the fiscal models.

- [ ] **Step 1: Write nominas-retenciones-administradores.md**

```markdown
# Nóminas y Retenciones de Administradores — Guía Operativa

## Contexto

Los 2 co-CEOs son administradores mancomunados con 45% cada uno. Cuando la S.L. empiece a pagarles nómina, esta guía cubre la mecánica completa: retención IRPF, cotización RETA, y conexión con los modelos fiscales.

Para la estrategia de retribución (nómina vs. dividendos vs. factura), ver `irpf-socios.md`.
Para las obligaciones de Seguridad Social, ver `seguridad-social-socios.md`.

---

## Retención IRPF de administradores

### Base legal
- **Art. 101.2 del Reglamento del IRPF (RD 439/2007)**
- Las retribuciones a administradores y miembros de consejos de administración tributan a tipo fijo, no por las tablas progresivas del trabajo ordinario.

### Tipos de retención

| Cifra de negocios de la S.L. (ejercicio anterior) | Tipo de retención |
|---------------------------------------------------|-------------------|
| ≥100.000€ | **35%** |
| <100.000€ | **19%** |

### Aplicación práctica para la S.L.

- **Primer ejercicio**: no hay cifra de negocios anterior. Aplicar **19%** si se prevé facturar <100.000€. Posición conservadora: la Hacienda acepta esta interpretación para nuevas sociedades.
- **Ejercicios siguientes**: verificar cifra de negocios del ejercicio anterior.
- **Ley Startups**: no afecta al tipo de retención IRPF del administrador. La Ley Startups reduce el IS (15%), no la retención IRPF.

### Ejemplo: nómina mensual de un administrador

Nómina bruta mensual: 1.500€

```
Nómina bruta:                    1.500,00€
Retención IRPF (19%):            -285,00€
Neto a percibir:                 1.215,00€

La S.L. paga al administrador:   1.215,00€
La S.L. ingresa en AEAT (111):     285,00€
```

**Importante**: A diferencia de un empleado ordinario, el administrador NO cotiza por contingencias comunes en nómina — cotiza como autónomo societario por separado (RETA).

---

## Cotización RETA del administrador

### Obligación
Los 2 co-CEOs con 45% + cargo de administrador → alta obligatoria en RETA como autónomo societario (ver `seguridad-social-socios.md` para detalle completo).

### Cuota estimada 2026
- Base mínima autónomo societario: ~1.200€/mes
- Tipo cotización: ~30,6%
- **Cuota mensual: ~380€/mes por administrador**

### ¿Quién paga la cuota?
La S.L. puede asumir la cuota (opción recomendada):
- Es gasto deducible en IS para la S.L. (Art. 10 LIS, retribución del administrador)
- Pero es retribución en especie para el administrador → se incluye en su IRPF
- **Requisito**: los estatutos deben prever la retribución del cargo de administrador (Art. 217 LSC). Si no lo prevén, Hacienda puede considerar el gasto no deducible (Art. 15.e LIS).

---

## Conexión con modelos fiscales

### Modelo 111 (trimestral)
Las retenciones de nómina del administrador se declaran en el Modelo 111:
- Casilla 01: nº de perceptores (rendimientos del trabajo)
- Casilla 02: base de retenciones (total bruto de nóminas del trimestre)
- Casilla 03: retenciones practicadas

### Modelo 190 (resumen anual)
- Clave **B.01**: rendimientos del trabajo a administradores
- Incluir NIF, nombre, base total anual, retención total anual
- La suma debe cuadrar con los 4 Modelos 111 del año

### Modelo 200 (IS anual)
- La nómina del administrador es gasto deducible en la base imponible del IS
- Incluir en la partida de gastos de personal
- Si la S.L. asume la cuota RETA: incluir como gasto de Seguridad Social a cargo de la empresa

---

## Requisito de los estatutos

**Art. 217 LSC**: el cargo de administrador es gratuito salvo que los estatutos establezcan lo contrario.

Si los estatutos NO prevén retribución → la nómina del administrador NO es gasto deducible en IS (el gasto existe, pero Hacienda puede rechazar la deducción).

**Acción requerida antes de pagar nómina**: verificar que los estatutos incluyen:
1. Que el cargo de administrador es retribuido
2. El sistema de retribución (cantidad fija, % sobre beneficios, o combinación)
3. La cuantía máxima aprobada en Junta General

---

## Coste total mensual por administrador (estimación)

| Concepto | Importe |
|----------|---------|
| Nómina bruta | 1.500,00€ |
| Retención IRPF 19% (la ingresa la S.L. en AEAT) | 285,00€ |
| Cuota RETA autónomo societario | ~380,00€ |
| **Coste total para la S.L.** | **~1.880,00€** |
| **Neto que recibe el administrador** | **1.215,00€** |

El administrador paga la cuota RETA de su bolsillo o la S.L. la asume como retribución en especie.
```

- [ ] **Step 2: Commit**

```bash
git add knowledge/legislacion/nominas-retenciones-administradores.md
git commit -m "feat: add complete guide for administradores payroll and retention"
```

---

### Task 11: Add nómina administrador asiento to asientos-tipo.md

**Files:**
- Modify: `operativa/contabilidad/asientos-tipo.md` (insert after section 3.5, line 109)

- [ ] **Step 1: Add asiento for nómina de administrador**

After section `3.5 Cuota autónomo societario` and before section `3.6 Factura de abogado`, insert:

```markdown

### 3.6 Nómina de administrador (ej: bruto 1.500€, retención IRPF 19%)
```
(640) Sueldos y salarios        1.500,00
    (4751) HP ret. IRPF practicadas      285,00
    (465) Remuneraciones pdte. pago    1.215,00

(465) Remuneraciones pdte. pago  1.215,00
    (572) Bancos                        1.215,00
```
Nota: el administrador NO cotiza en nómina (no hay cuenta 476 aquí). Cotiza por RETA — ver asiento 3.5.
```

Then renumber the existing section `3.6 Factura de abogado` to `3.7`.

- [ ] **Step 2: Commit**

```bash
git add operativa/contabilidad/asientos-tipo.md
git commit -m "feat: add administrador payroll journal entry to asientos-tipo"
```

---

### Task 12: Create verifactu-facturacion-electronica.md

**Files:**
- Create: `knowledge/legislacion/verifactu-facturacion-electronica.md`

- [ ] **Step 1: Write verifactu-facturacion-electronica.md**

```markdown
# Verifactu — Facturación Electrónica Obligatoria

## Marco normativo

- **RD 1007/2023**, de 5 de diciembre — Reglamento que establece los requisitos de los sistemas informáticos de facturación (Reglamento Verifactu)
- **Orden HAC/1177/2024** — Especificaciones técnicas del sistema Verifactu
- **Ley 18/2022 (Ley Crea y Crece)**, Art. 12 — Establece la obligación de facturación electrónica B2B

## Qué es Verifactu

Verifactu es el sistema de la AEAT que exige que todos los programas de facturación:
1. **Registren** cada factura emitida de forma inalterable (hash encadenado)
2. **Envíen** los registros de facturación a la AEAT (en tiempo real o en plazo)
3. **Garanticen** la integridad de la información (no se pueden borrar ni modificar facturas sin traza)

Es distinto de la facturación electrónica B2B (que obliga a emitir y recibir facturas en formato estructurado entre empresas). Verifactu afecta al **software de facturación**; la facturación electrónica B2B afecta a las **facturas entre empresas**.

## Calendario de implantación

### Obligación del software (Verifactu — RD 1007/2023)
- **Desarrolladores de software**: deben adaptar sus programas antes del **29 de julio de 2025**
- **Empresarios y profesionales (usuarios)**: obligados a usar software adaptado. La fecha de obligación para los usuarios depende de la publicación de la orden ministerial de desarrollo — a fecha de abril 2026, pendiente de confirmación definitiva.
- **Estimación**: los contribuyentes estarán obligados a partir de **2026-2027**, dependiendo del volumen de facturación.

### Facturación electrónica B2B (Ley Crea y Crece)
- **Empresas con facturación >8M€**: obligadas a emitir factura electrónica a partir de la fecha que establezca el reglamento (previsto 2026-2027)
- **Resto de empresas y autónomos**: obligadas en un plazo posterior (previsto 2027-2028)
- **La S.L. como startup nueva**: probablemente en el segundo tramo (<8M€)

## Qué implica para la S.L.

### Impacto inmediato (pre-constitución)
1. **Al elegir software de facturación** (Holded, A3, Contasol, etc.): verificar que el software ya cumple o tiene previsto cumplir con Verifactu.
2. Holded ha anunciado compatibilidad con Verifactu — verificar estado actual al momento de la constitución.

### Impacto cuando esté en vigor
1. Cada factura emitida por la S.L. generará un registro firmado digitalmente
2. Los registros se enviarán a la AEAT automáticamente (el software lo hace)
3. No se podrán emitir facturas "en B" ni modificar facturas sin traza
4. Las facturas rectificativas deben seguir el procedimiento formal (Art. 15 RD 1619/2012)

### Factura electrónica B2B
1. Cuando entre en vigor, las facturas entre la S.L. y los tutores autónomos deberán ser electrónicas (formato Facturae o equivalente)
2. Las facturas al consumidor final (estudiantes) **no se ven afectadas inicialmente** por la obligación B2B
3. El software de facturación deberá soportar envío/recepción de facturas electrónicas estructuradas

## Requisitos técnicos esenciales (Verifactu)

| Requisito | Descripción |
|-----------|-------------|
| Registro de facturación | Cada factura genera un registro con huella digital (hash) |
| Hash encadenado | Cada registro incluye el hash del registro anterior — forma una cadena inmutable |
| Envío a AEAT | Los registros se envían telemáticamente (API de la AEAT) |
| Inalterabilidad | No se pueden borrar ni modificar registros sin dejar traza |
| Conservación | Los registros deben conservarse durante el plazo de prescripción (4 años) |

## Acción requerida

**Al constituir la S.L.:**
1. Verificar que el software de facturación elegido es compatible con Verifactu (o tiene fecha comprometida de adaptación)
2. No usar hojas de cálculo ni sistemas manuales para facturar — no cumplirán con Verifactu
3. Si se elige Holded: confirmar que la versión contratada incluye el módulo de Verifactu

**Cuando entre en vigor la facturación electrónica B2B:**
1. Configurar el software para emitir facturas en formato Facturae
2. Comunicar a los tutores autónomos que deberán poder recibir facturas electrónicas
3. Verificar que el flujo de facturación del marketplace (ver `marketplace-educativo/flujo-facturacion.md`) es compatible
```

- [ ] **Step 2: Commit**

```bash
git add knowledge/legislacion/verifactu-facturacion-electronica.md
git commit -m "feat: add Verifactu and electronic invoicing guide"
```

---

## Final Task: Update knowledge/INDEX.md with new files

### Task 13: Update INDEX.md references

**Files:**
- Modify: `knowledge/INDEX.md`

- [ ] **Step 1: Verify that INDEX.md already references the new files**

The INDEX.md written in Task 2 already includes references to:
- `legislacion/nominas-retenciones-administradores.md` (in IRPF section)
- `legislacion/verifactu-facturacion-electronica.md` (in Obligaciones Mercantiles section)

No changes needed if Task 2 was implemented as specified.

- [ ] **Step 2: Final verification — check all files exist and are referenced**

```bash
# Verify all new/modified files
ls README.md
ls knowledge/INDEX.md
ls operativa/protocolo-datos-incompletos.md
ls knowledge/legislacion/nominas-retenciones-administradores.md
ls knowledge/legislacion/verifactu-facturacion-electronica.md

# Verify modifications
git log --oneline -15
```

- [ ] **Step 3: Commit (only if INDEX.md needed changes)**

```bash
git add knowledge/INDEX.md
git commit -m "docs: update INDEX.md with references to new content"
```
