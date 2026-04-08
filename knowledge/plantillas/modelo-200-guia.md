# Guía Modelo 200 — Declaración Anual Impuesto de Sociedades

## Cuándo presentar
- **Plazo**: 25 días naturales siguientes a los 6 meses posteriores al cierre del ejercicio
- Si el ejercicio cierra el 31 de diciembre → plazo hasta **25 de julio** del año siguiente
- Presentación telemática obligatoria (certificado digital)

## Es el modelo más complejo — Estructura

### Páginas principales del Modelo 200

1. **Datos identificativos**: NIF, razón social, domicilio, ejercicio
2. **Balance**: activo + pasivo + patrimonio neto (datos contables de Holded)
3. **Cuenta de Pérdidas y Ganancias**: ingresos - gastos = resultado del ejercicio
4. **Resultado contable → Base imponible**: ajustes extracontables
5. **Base imponible**: resultado contable ± ajustes
6. **Liquidación**: tipo × base - deducciones - pagos fraccionados = cuota

## Cálculo paso a paso

### Paso 1: Resultado contable (de la contabilidad)
```
Ingresos de explotación (ventas, comisiones)
- Gastos de explotación (personal, servicios, amortizaciones, suministros)
= Resultado de explotación

+ Ingresos financieros
- Gastos financieros
= Resultado financiero

Resultado antes de impuestos = Resultado explotación + Resultado financiero
```

### Paso 2: Ajustes extracontables
```
Resultado contable
+ Aumentos (gastos no deducibles fiscalmente):
  + Multas y sanciones
  + Liberalidades
  + Amortización excesiva
  + Provisiones no deducibles
  + Gastos no justificados
  
- Disminuciones (ingresos no computables o gastos extra deducibles):
  - Amortización acelerada (ERD Art. 103 LIS)
  - Reserva de nivelación (ERD Art. 105 LIS)
  - Exención dividendos (Art. 21 LIS)

= BASE IMPONIBLE PREVIA

- Compensación bases imponibles negativas de años anteriores (Art. 26 LIS)

= BASE IMPONIBLE
```

### Paso 3: Liquidación
```
Base imponible × Tipo IS (15% Ley Startups / 23% ERD / 25% general)
= CUOTA ÍNTEGRA

- Deducciones por doble imposición
- Deducción I+D+i (Art. 35 LIS)
- Deducción creación empleo (Art. 37 LIS)
- Otras deducciones
= CUOTA LÍQUIDA

- Retenciones e ingresos a cuenta (soportadas durante el año)
- Pagos fraccionados (Modelos 202 presentados)
= CUOTA DIFERENCIAL

Si positiva → A INGRESAR
Si negativa → A DEVOLVER
```

## Datos necesarios para preparar el 200

Necesito que me proporciones (o exportes de Holded):

### Contabilidad del ejercicio
1. **Balance de situación** a 31 de diciembre con desglose de cuentas PGC
2. **Cuenta de Pérdidas y Ganancias** del ejercicio completo
3. **Libro Diario** del ejercicio (para verificar)

### Información fiscal adicional
4. **Pagos fraccionados** (Modelos 202) presentados durante el año
5. **Retenciones soportadas** (retenciones sobre dividendos cobrados, intereses bancarios, etc.)
6. **Gastos de I+D+i** del ejercicio (si aplica la deducción)
7. **Bases imponibles negativas** de ejercicios anteriores pendientes de compensar
8. **Operaciones con vinculadas** (operaciones entre socios y la S.L.)
9. **Reserva de nivelación** aplicada en años anteriores pendiente de revertir

### Datos adicionales de la declaración
10. ¿Se ha distribuido dividendos durante el ejercicio?
11. ¿Se han realizado operaciones con el extranjero?
12. ¿Se ha contratado empleados? (para deducción creación empleo)
13. ¿Se cumplen los requisitos de ERD? (cifra negocio <10M€)
14. ¿Estáis inscritos como empresa emergente (Ley Startups)?

## Ejemplo práctico — Año 1 de la S.L.

### Datos del ejercicio:
- Ingresos por comisiones: 30.000€
- Gastos operativos: 22.000€ (hosting, software, marketing, SS administradores)
- Amortización: 500€ (equipos informáticos)
- Resultado contable: 30.000 - 22.000 - 500 = 7.500€

### Cálculo:
```
Resultado contable: 7.500€
Ajustes extracontables: 0€ (no hay gastos no deducibles)
Base imponible previa: 7.500€
Reserva nivelación ERD (-10% máx): -750€
BASE IMPONIBLE: 6.750€

Tipo IS (Ley Startups): 15%
Cuota íntegra: 6.750 × 15% = 1.012,50€

Deducción I+D+i (12% sobre gastos desarrollo CTO):
- Gastos desarrollo cualificados: 8.000€
- Deducción: 8.000 × 12% = 960€
- Límite: 25% cuota íntegra = 253,13€

Cuota líquida: 1.012,50 - 253,13 = 759,37€

Pagos fraccionados (202): 0€ (primer ejercicio)
Retenciones soportadas: 50€ (intereses bancarios)

CUOTA DIFERENCIAL: 759,37 - 50 = 709,37€ A INGRESAR
```

### Ahorro fiscal acumulado:
- Sin optimización (25% tipo general): 7.500 × 25% = 1.875€
- Con optimización (15% + I+D+i + nivelación): 709,37€
- **Ahorro: 1.165,63€** (62% menos impuestos)

## ⚠️ REVISIÓN HUMANA RECOMENDADA

El Modelo 200 es el más complejo del año. Errores pueden generar requerimientos de Hacienda con recargos.

**Recomendación**: La IA prepara el borrador completo → un fiscal/contable lo revisa en 1-2 horas (~€200-300). Es la única revisión humana del año.

## Presentación
1. Sede Electrónica AEAT → Impuesto sobre Sociedades → Modelo 200
2. Rellenar todas las páginas (balance, PyG, ajustes, liquidación)
3. Firmar con certificado digital
4. Pagar cuota diferencial (si positiva) por domiciliación
5. Guardar justificante
