# Guía Modelo 190 — Resumen Anual de Retenciones IRPF

## Plazo: 1-31 de enero del año siguiente

## Qué es
Resumen anual de TODAS las retenciones declaradas en los 4 Modelos 111 trimestrales. Detalla perceptor por perceptor (NIF, nombre, tipo de renta, importe, retención).

## Datos necesarios
1. **Listado de TODOS los perceptores del año**:
   - NIF / DNI / NIE
   - Nombre y apellidos (o razón social)
   - Tipo de percepción (clave A = trabajo, clave G = profesionales)
   - Base total percibida en el año
   - Retención total practicada en el año
2. Verificar que la suma coincida con los 4 Modelos 111

## Claves de percepción relevantes

| Clave | Tipo | Uso |
|-------|------|-----|
| A | Rendimientos del trabajo: empleados | Nóminas |
| B.01 | Rendimientos del trabajo: administradores | Nómina de co-CEOs |
| G.01 | Actividades profesionales | Facturas de tutores autónomos, abogados, etc. |
| G.02 | Actividades profesionales: nuevo autónomo (7%) | Tutores nuevos autónomos |
| F | Premios | Improbable |

## Ejemplo práctico

### Datos anuales:
- Tutor 1 (NIF 12345678A): ha facturado 8.000€ con retención 15% = 1.200€
- Tutor 2 (NIF 87654321B): ha facturado 3.000€ con retención 7% (nuevo) = 210€
- Tutor 3 (NIF 11111111C): ha facturado 2.000€ con retención 15% = 300€

### Modelo 190:
```
Perceptor 1: Clave G.01 | NIF 12345678A | Base 8.000€ | Retención 1.200€
Perceptor 2: Clave G.02 | NIF 87654321B | Base 3.000€ | Retención 210€
Perceptor 3: Clave G.01 | NIF 11111111C | Base 2.000€ | Retención 300€

TOTAL: Base 13.000€ | Retención 1.710€
```

Verificación: 1.710€ debe coincidir con la suma de casilla 28 de los 4 Modelos 111.

## Presentación
- Telemática obligatoria con certificado digital
- Formato: si >10 perceptores, presentación de fichero (Holded lo genera)
- Si ≤10: se puede rellenar manualmente en la Sede Electrónica

---

# Guía Modelo 347 — Operaciones con Terceros >3.005,06€

## Plazo: Febrero del año siguiente

## Qué es
Declaración informativa de TODAS las operaciones realizadas con un mismo tercero cuando el importe total anual supera **3.005,06€** (IVA incluido).

## ¿Quién está obligado?
Toda persona física o jurídica que realice actividades empresariales/profesionales.

## Datos necesarios
1. **Listado de clientes** a los que se ha facturado >3.005,06€ en el año
2. **Listado de proveedores** a los que se ha pagado >3.005,06€ en el año
3. Importes **IVA incluido**
4. Desglose por trimestres

## Relevancia para el marketplace

### Tutores
Si un tutor factura a la S.L. más de 3.005,06€ en el año → incluir en el 347.
El tutor también debe incluir a la S.L. en su 347.
**Si no coinciden → AEAT puede enviar requerimiento a ambos.**

### Proveedores
Si pagáis >3.005,06€/año a Stripe, hosting, Holded, etc. → incluir.

### Clientes/Estudiantes
Si un estudiante/familia paga >3.005,06€/año → incluir (improbable pero posible con clases intensivas).

## Ejemplo:
```
Proveedor: Stripe (Irlanda) | NIF intracom: IE1234567 | Importe anual: 4.500€
Tutor: Juan García | NIF: 12345678A | Importe anual: 8.000€ IVA incl.
Proveedor: AWS | NIF intracom: IE7654321 | Importe anual: 3.600€
```

---

# Guía Modelo 390 — Resumen Anual IVA

## Plazo: 1-30 de enero (junto con el 303 del 4T)

## Qué es
Resumen anual de los 4 Modelos 303 trimestrales. Debe cuadrar exactamente.

## Datos necesarios
- Suma de los 4 Modelos 303 del año
- Desglose por tipo impositivo
- Volumen de operaciones del año
- Prorrata (si aplica — probablemente no)

## Contenido principal
```
OPERACIONES REALIZADAS EN EL EJERCICIO:
- Total base imponible IVA devengado al 21%: [suma 4 trimestres]
- Total base imponible IVA devengado al 10%: [si aplica]
- Total IVA devengado: [suma]

OPERACIONES CON DERECHO A DEDUCCIÓN:
- Total base cuotas soportadas: [suma de gastos con IVA]
- Total IVA deducible: [suma]

RESULTADO:
- Total IVA ingresado en los 4 trimestres: [suma casilla 69 de los 4 Modelos 303]
- Diferencia: debe ser 0 (si cuadra)
```

## Verificación
La IA debe cuadrar el 390 contra los 4 Modelos 303 del año. Si hay discrepancia, corregir antes de presentar.

---

# Requisitos Legales de Factura en España (RD 1619/2012)

## Factura completa (Art. 6)

Toda factura emitida por la S.L. debe contener:

| Campo | Detalle |
|-------|---------|
| Número y serie | Correlativo dentro de cada serie (ej: F-2026-0001) |
| Fecha de expedición | Fecha de emisión de la factura |
| Fecha de operación | Si difiere de la de expedición |
| NIF del emisor | NIF de la S.L. |
| Nombre/razón social del emisor | Nombre completo de la S.L. |
| Domicilio del emisor | Domicilio fiscal |
| NIF del destinatario | Obligatorio si >100€ o si el cliente lo pide |
| Nombre/razón social del destinatario | |
| Descripción | Detalle de la operación |
| Base imponible | Importe sin IVA |
| Tipo impositivo | 21%, 10%, 4% |
| Cuota de IVA | Base × tipo |
| Importe total | Base + IVA |
| Retención IRPF | Si aplica (factura de profesional) |
| Mención de exención | Si aplica: "Operación exenta de IVA según Art. 20.Uno.[X] LIVA" |

## Factura simplificada (Art. 7) — tipo "ticket"
- Permitida para importes <400€ (operaciones generales)
- No requiere NIF del destinatario
- Para el marketplace: facturas al estudiante <400€ podrían ser simplificadas
- **PERO**: si el cliente pide factura completa, obligación de emitirla

## Plazos de expedición
- Factura a empresario/profesional: antes del día 16 del mes siguiente a la operación
- Factura a consumidor final: en el momento de la operación
- **Recomendación**: facturar en el momento de cada reserva/clase (automatizado por Holded)

## Series de facturación recomendadas

| Serie | Uso |
|-------|-----|
| F-YYYY-NNNN | Facturas a clientes (estudiantes) |
| R-YYYY-NNNN | Facturas rectificativas |
| A-YYYY-NNNN | Abonos / devoluciones |

## Conservación
- **Obligación legal**: conservar facturas emitidas y recibidas durante **4 años** (plazo prescripción tributaria) + **6 años** (obligación mercantil del Art. 30 CCom)
- Formato digital aceptado si garantiza integridad y legibilidad
- **Holded las conserva** automáticamente en la nube
