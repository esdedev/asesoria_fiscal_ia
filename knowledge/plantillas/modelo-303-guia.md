# Guía Modelo 303 — Autoliquidación IVA Trimestral

## Cuándo presentar

| Trimestre | Período | Plazo límite |
|-----------|---------|-------------|
| 1T | Enero-Marzo | 20 de abril |
| 2T | Abril-Junio | 20 de julio |
| 3T | Julio-Septiembre | 20 de octubre |
| 4T | Octubre-Diciembre | 30 de enero (+ Modelo 390) |

## Datos necesarios del período

Para preparar el 303, necesito que me proporciones:

### A) Ventas/Ingresos del trimestre
1. Total facturado al 21% (base imponible, sin IVA)
2. Total facturado al 10% (si aplica)
3. Total facturado al 4% (si aplica)
4. Operaciones exentas (si aplica)
5. Operaciones no sujetas (si aplica)

### B) Compras/Gastos del trimestre (con IVA deducible)
1. Facturas recibidas nacionales al 21% (base imponible)
2. Facturas recibidas nacionales al 10% (base)
3. Facturas recibidas intracomunitarias (inversión sujeto pasivo)
4. Facturas de importación (si aplica)

### C) Otros datos
1. IVA a compensar de trimestres anteriores (si lo hay)
2. ¿Es el 4T? → si quieres solicitar devolución en lugar de compensar

## Cálculo paso a paso

```
SECCIÓN: IVA DEVENGADO (lo que has cobrado de IVA)

Casilla 01: Base imponible al 21% = [total ventas 21%]
Casilla 02: Tipo = 21
Casilla 03: Cuota = Casilla 01 × 21% = [cuota IVA repercutido 21%]

Casilla 04: Base imponible al 10% = [total ventas 10%]
Casilla 05: Tipo = 10
Casilla 06: Cuota = Casilla 04 × 10%

Casilla 07: Base imponible al 4% = [total ventas 4%]
Casilla 08: Tipo = 4
Casilla 09: Cuota = Casilla 07 × 4%

Casilla 10: Adquisiciones intracomunitarias (base)
Casilla 11: Cuota = Casilla 10 × 21%

Casilla 27: TOTAL CUOTAS DEVENGADAS = 03 + 06 + 09 + 11

SECCIÓN: IVA DEDUCIBLE (lo que has pagado de IVA)

Casilla 28: Base cuotas soportadas operaciones interiores = [total gastos con IVA]
Casilla 29: Cuota = [total IVA pagado en facturas recibidas]

Casilla 30: Base cuotas soportadas adquisiciones intracomunitarias
Casilla 31: Cuota = Casilla 30 × 21% (se anula con casilla 11)

Casilla 45: TOTAL IVA DEDUCIBLE = 29 + 31 + otros

RESULTADO:
Casilla 46: RESULTADO RÉGIMEN GENERAL = Casilla 27 - Casilla 45

Casilla 64: A compensar de períodos anteriores = [importe pendiente]
Casilla 65: RESULTADO = Casilla 46 - Casilla 64

Si Casilla 65 > 0 → A INGRESAR (hay que pagar)
Si Casilla 65 < 0 → A COMPENSAR (o solicitar devolución en 4T)

Casilla 66: Solo 4T → Solicitar devolución (marcar si quieres que te devuelvan)
Casilla 69: RESULTADO DE LA LIQUIDACIÓN (a ingresar o a devolver)
```

## Ejemplo práctico (T1 de la S.L. marketplace)

### Datos del trimestre:
- Comisiones facturadas a estudiantes: 5.000€ (base, sin IVA)
- Gastos con IVA: hosting 100€, software 200€, publicidad 300€ = 600€ (base)
- Facturas de Stripe (Irlanda): 150€ (inversión sujeto pasivo)
- Sin IVA a compensar de períodos anteriores

### Cálculo:
```
IVA DEVENGADO:
Casilla 01: 5.000€ (ventas al 21%)
Casilla 03: 1.050€ (21% de 5.000€)
Casilla 10: 150€ (adq. intracomunitaria - Stripe)
Casilla 11: 31,50€ (21% de 150€)
Casilla 27: 1.081,50€ (total devengado)

IVA DEDUCIBLE:
Casilla 28: 600€ (gastos nacionales)
Casilla 29: 126€ (21% de 600€)
Casilla 30: 150€ (adq. intracomunitaria)
Casilla 31: 31,50€ (se anula con casilla 11)
Casilla 45: 157,50€ (total deducible)

RESULTADO:
Casilla 46: 1.081,50 - 157,50 = 924€
Casilla 65: 924€ A INGRESAR

→ Hay que pagar 924€ a Hacienda antes del 20 de abril
```

## Presentación

1. Acceder a Sede Electrónica AEAT: https://sede.agenciatributaria.gob.es
2. Identificarse con certificado digital de la S.L.
3. Ir a: Impuestos y tasas → IVA → Modelo 303
4. Rellenar casillas
5. Resultado: a ingresar → domiciliación bancaria o pago directo
6. Confirmar y obtener justificante de presentación
