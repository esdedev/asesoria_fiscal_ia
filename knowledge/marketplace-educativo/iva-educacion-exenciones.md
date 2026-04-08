# IVA y Educación — Exenciones Art. 20 LIVA

## Análisis específico para el marketplace educativo

## Exención general de enseñanza — Art. 20.Uno.9º LIVA

### Texto legal (extracto)
Están exentas:
> "9.º La educación de la infancia y de la juventud, la guarda y custodia de niños, incluida la atención a niños en los centros docentes en tiempo interlectivo durante el comedor escolar o en aulas en servicio de guardería fuera del horario escolar, la enseñanza escolar, universitaria y de postgraduados, la enseñanza de idiomas y la formación y reciclaje profesional, realizadas por **Entidades de derecho público o entidades privadas autorizadas** para el ejercicio de dichas actividades."

### ¿Quién está exento?
1. **Entidades de derecho público**: universidades públicas, institutos, colegios públicos
2. **Entidades privadas autorizadas**: centros privados con autorización administrativa de la Consejería de Educación correspondiente

### ¿La S.L. marketplace está exenta?
**NO, con altísima probabilidad.**

Razones:
1. **No es un centro educativo autorizado**: la S.L. es un intermediario, no imparte enseñanza
2. **Servicio de intermediación ≠ servicio de enseñanza**: la S.L. cobra una comisión por conectar tutores con estudiantes
3. **Doctrina DGT clara**:
   - **V0180-20**: servicios de intermediación no se benefician de la exención educativa
   - **V2314-18**: plataforma online que conecta profesores con alumnos → la comisión de intermediación NO está exenta
   - **V0566-17**: servicios de plataforma tecnológica a centros educativos → sujetos y no exentos

### Conclusión IVA de la S.L.
La S.L. debe repercutir **IVA al 21%** sobre su comisión de intermediación.

## Exención de clases particulares — Art. 20.Uno.10º LIVA

### Texto legal
Están exentas:
> "10.º Las clases a título particular prestadas por personas físicas sobre materias incluidas en los planes de estudios de cualquiera de los niveles y grados del sistema educativo."

### Requisitos acumulativos
1. **Persona física** (no empresa ni S.L.)
2. **A título particular** (no como empleado de una academia)
3. **Materias del sistema educativo** (matemáticas, lengua, física... SÍ; guitarra, yoga... NO)

### ¿Aplica a los tutores del marketplace?
| Tutor | Situación | ¿Exento de IVA? |
|-------|-----------|-----------------|
| Universitario que da clases de matemáticas | Persona física, materia del SE | ✅ SÍ |
| Universitario que da clases de guitarra | Persona física, materia NO del SE | ❌ NO — IVA 21% |
| Empresa/academia que da clases | No es persona física | ❌ NO — IVA 21% |
| Tutor autónomo que da clases de inglés | Persona física, materia del SE | ✅ SÍ |

### Consecuencia para la S.L.
- Si el tutor está exento → su factura a la S.L. NO lleva IVA → la S.L. NO puede deducir IVA soportado por ese servicio
- Si el tutor NO está exento → su factura lleva IVA 21% → la S.L. SÍ deduce ese IVA soportado
- **Impacto en caja**: los tutores exentos "cuestan" más en IVA neto a la S.L. porque no hay soportado deducible

## Flujo de IVA del marketplace — Esquema

### Escenario tipo: Estudiante paga 30€/hora, comisión S.L. = 20% (6€)

```
ESTUDIANTE paga a la S.L. → 30€ + IVA 21% = 36.30€
(La S.L. factura al estudiante por el servicio de intermediación + el servicio del tutor)

o bien (modelo agencia):

ESTUDIANTE paga a la S.L. → 6€ comisión + IVA 21% = 7.26€ (comisión)
                          + 24€ al tutor (pass-through)

TUTOR factura a la S.L. → 24€ + IVA 21% = 29.04€ (si no exento)
                       o → 24€ sin IVA (si exento por Art. 20.Uno.10º)
```

### ⚠️ DECISIÓN CRÍTICA: ¿Modelo agente o modelo principal?

**Modelo Principal** (la S.L. compra el servicio del tutor y lo revende al estudiante):
- La S.L. factura al estudiante el precio total (30€ + IVA)
- El tutor factura a la S.L. su precio (24€ ± IVA)
- **IVA repercutido**: sobre 30€
- **IVA soportado**: sobre 24€ (si tutor no exento) o 0€ (si exento)
- **RIESGO**: mayor control sobre el servicio → mayor riesgo de falso autónomo

**Modelo Agente/Intermediario** (la S.L. solo cobra comisión):
- La S.L. factura al estudiante SOLO la comisión (6€ + IVA)
- El tutor cobra directamente del estudiante o a través de la plataforma (pero la S.L. actúa como intermediario)
- **IVA repercutido**: sobre 6€
- **RIESGO**: menor control → menor riesgo laboral

**Recomendación**: Modelo Agente/Intermediario → menor riesgo laboral + menor complejidad IVA

## Prorrata de IVA — ¿Aplica a la S.L.?

Si la S.L. realizase ALGUNA operación exenta de IVA (improbable pero posible si además ofrece formación propia), debería calcular prorrata:
- Prorrata = IVA repercutido operaciones gravadas / IVA total operaciones × 100
- El IVA soportado solo sería deducible en el % de la prorrata

**En principio, no aplica**: la S.L. solo hace intermediación (operación gravada al 21%).

## Registro ROI (Registro de Operadores Intracomunitarios)

Si la S.L. contrata servicios de empresas UE (hosting en Irlanda, AWS en Luxemburgo, Stripe en Irlanda):
- Darse de alta en ROI (Modelo 036, casilla 582)
- Aplicar inversión del sujeto pasivo (Art. 84.Uno.2º LIVA)
- Declarar en el Modelo 303 (casillas 10-11) y Modelo 349

## Facturación electrónica y TicketBAI

### Verifactu (RD 1007/2023)
- Desde 2026-2027 (calendario por fases según facturación)
- Software de facturación debe emitir registros de facturación verificables
- **Holded ya está adaptándose** — verificar estado actual

### TicketBAI (solo País Vasco y Navarra)
- Solo aplica si domicilio fiscal en Euskadi o Navarra
- **No aplica** si estáis en territorio común
