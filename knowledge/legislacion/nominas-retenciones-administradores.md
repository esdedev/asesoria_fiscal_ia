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

| Cifra de negocios de la S.L. (ejercicio anterior) | Tipo de retención | Base legal |
|---------------------------------------------------|-------------------|------------|
| ≥100.000€ | **35%** | Art. 101.2.a RIRPF |
| <100.000€ | **19%** | Art. 101.2.b RIRPF |

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
