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
