# Flujo de Facturación del Marketplace Educativo

## Arquitectura de cobros y pagos

## Modelo recomendado: Intermediario con pasarela de pago

### Flujo completo

```
1. ESTUDIANTE busca tutor en la plataforma
2. ESTUDIANTE reserva clase con TUTOR (precio fijado por el tutor)
3. ESTUDIANTE paga a la S.L. vía pasarela (Stripe/Redsys)
4. La S.L. retiene la comisión (ej: 20%)
5. La S.L. transfiere el resto al TUTOR (ej: 80%)
6. La S.L. emite factura al ESTUDIANTE por la comisión
7. El TUTOR emite factura a la S.L. (o recibo si no es autónomo)
```

### Diagrama de flujo fiscal

```
ESTUDIANTE (consumidor final)
    │
    │ Paga 30€ + IVA 21% = 36,30€
    ▼
S.L. (MARKETPLACE)
    │
    │ Retiene comisión: 6€ + IVA = 7,26€ → INGRESO de la S.L.
    │
    │ Transfiere al tutor: 24€
    ▼
TUTOR (autónomo o persona física)
    │
    │ Factura a la S.L.: 24€ + IVA 21% = 29,04€ (si no exento)
    │                  o 24€ sin IVA (si exento Art. 20.Uno.10º)
    ▼
```

### Posición IVA neta de la S.L. (por cada transacción de 30€)

| Concepto | Si tutor NO exento | Si tutor exento |
|----------|-------------------|-----------------|
| IVA repercutido (al estudiante) | 6,30€ (21% de 30€) | 6,30€ |
| IVA soportado (factura tutor) | 5,04€ (21% de 24€) | 0€ |
| **IVA neto a ingresar** | **1,26€** | **6,30€** |

**⚠️ Importante**: Si el tutor está exento de IVA (clases particulares de materias del sistema educativo), la S.L. soporta más IVA neto. Esto afecta a la tesorería.

### Alternativa: Solo facturar la comisión

```
ESTUDIANTE paga al TUTOR directamente: 24€
ESTUDIANTE paga a la S.L. la comisión: 6€ + IVA = 7,26€

S.L. solo factura: 6€ + IVA 21% = 7,26€
IVA repercutido: 1,26€
IVA soportado: gastos generales (hosting, software, etc.)
```

- **Ventaja**: menor volumen de IVA, menor complejidad
- **Desventaja**: requiere que el pago al tutor sea directo (la plataforma no controla el flujo)
- **Riesgo menor de falsos autónomos**: la S.L. tiene menos control sobre la transacción

## Documentos fiscales por transacción

### 1. Factura al estudiante/padre
- Emisor: S.L. (NIF, razón social, domicilio)
- Receptor: estudiante o padre/tutor legal (NIF si empresa; sin NIF si consumidor final <100€)
- Concepto: "Servicio de intermediación educativa — reserva de clase [materia] [fecha]"
- Base imponible: 30€ (o solo 6€ si modelo comisión pura)
- IVA: 21%
- Total: 36,30€ (o 7,26€)
- Serie: F-YYYY-NNNN (correlativa)

### 2. Factura del tutor a la S.L.
- Emisor: tutor (NIF, nombre/autónomo)
- Receptor: S.L.
- Concepto: "Prestación de servicios de tutoría [materia] [fecha]"
- Base: 24€
- IVA: 21% o exento (Art. 20.Uno.10º LIVA)
- Retención IRPF: 15% (o 7% si nuevo autónomo) → solo si el tutor es autónomo
- Si el tutor no es autónomo: recibo/justificante de pago (la S.L. retiene IRPF)

### 3. Retenciones IRPF a tutores

**Si el tutor es autónomo y factura:**
- El tutor incluye retención del 15% en su factura
- La S.L. ingresa esa retención en AEAT (Modelo 111 trimestral)
- Ejemplo: factura 24€ - retención 15% = 3,60€ → la S.L. paga 20,40€ al tutor + 3,60€ a AEAT

**Si el tutor NO es autónomo (persona física esporádica):**
- La S.L. practica retención sobre el pago
- **⚠️ RIESGO**: si el tutor no es autónomo pero cobra regularmente → debería serlo o la S.L. debería contratarlo

## Contabilidad de cada transacción (PGC PYMES)

### Asiento por reserva completada (30€, tutor no exento)

```
--- Al cobrar del estudiante ---
(572) Bancos          36,30€
    (705) Ingresos por comisión    6,00€
    (477) IVA repercutido          6,30€
    (410) Acreedores - tutor      24,00€

--- Al pagar al tutor ---
(410) Acreedores - tutor   24,00€
(472) IVA soportado         5,04€
    (572) Bancos                   25,44€
    (4751) HP acreedora IRPF        3,60€

--- Al ingresar retención IRPF (trimestral) ---
(4751) HP acreedora IRPF    3,60€
    (572) Bancos                    3,60€
```

### Asiento simplificado (tutor exento IVA)
```
(572) Bancos          36,30€
    (705) Ingresos por comisión    6,00€
    (477) IVA repercutido          6,30€
    (410) Acreedores - tutor      24,00€

(410) Acreedores - tutor   24,00€
    (572) Bancos                   20,40€
    (4751) HP acreedora IRPF        3,60€
```

## Stripe / Redsys — Consideraciones fiscales

### Comisiones de la pasarela de pago
- Stripe: ~1.5% + 0,25€ por transacción (Europa)
- Redsys: variable según banco, generalmente más bajo
- **Estas comisiones son gasto deducible de la S.L. en IS**
- **El IVA de las comisiones de Stripe**: Stripe factura desde Irlanda → inversión del sujeto pasivo (la S.L. autorepercute y deduce IVA)

### Stripe Atlas (constitución en Delaware)
- ❌ **NO usar Stripe Atlas para constituir** en EEUU. Crea una C-Corp en Delaware → residente fiscal en España de todos modos + doble contabilidad + obligaciones US
- ✅ Usar Stripe solo como **pasarela de pago** para la S.L. española

## Modelo 347 — Operaciones con terceros >3.005,06€

Si algún tutor factura más de 3.005,06€/año a la S.L.:
- Incluir en el Modelo 347 (declaración anual, febrero)
- El tutor debe hacer lo mismo en su declaración
- **Si hay muchos tutores**: automatizar la extracción de datos de Holded

## Facturación electrónica B2B (desde 2027-2028 aprox.)

- Obligación progresiva de que todas las facturas B2B sean electrónicas
- Entre la S.L. y los tutores autónomos → factura electrónica
- Holded soportará este formato
- Facturas al consumidor final (estudiantes): no aplica inicialmente
