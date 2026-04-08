# Guía Modelo 111 — Retenciones IRPF (Trabajo y Actividades Profesionales)

## Cuándo presentar

| Trimestre | Período | Plazo |
|-----------|---------|-------|
| 1T | Enero-Marzo | 1-20 abril |
| 2T | Abril-Junio | 1-20 julio |
| 3T | Julio-Septiembre | 1-20 octubre |
| 4T | Octubre-Diciembre | 1-20 enero |

## Cuándo está obligada la S.L. a presentar el 111

La S.L. debe presentarlo siempre que practique retenciones de IRPF sobre:
- **Nóminas** de trabajadores o administradores
- **Facturas de profesionales** autónomos (tutores, abogados, consultores)
- **Retribuciones de administradores** (cuando se les pague nómina)

Si en un trimestre no se practica ninguna retención → no hay obligación de presentar (pero conviene presentarlo a 0€ para evitar requerimientos).

## Datos necesarios

1. **Rendimientos del trabajo**: nóminas brutas pagadas en el trimestre + retenciones practicadas
2. **Rendimientos de actividades profesionales**: facturas de autónomos pagadas + retenciones practicadas  
3. **Otros**: premios, rendimientos de cursos/conferencias (improbable para vosotros)

## Cálculo

```
PERCEPCIONES (casillas por tipo):

Casilla 01: Nº perceptores por rendimientos del trabajo
Casilla 02: Base retenciones trabajo (total bruto de nóminas)
Casilla 03: Retenciones practicadas sobre trabajo
Casilla 04: Ingresos a cuenta sobre trabajo

Casilla 07: Nº perceptores por actividades profesionales
Casilla 08: Base retenciones profesionales (total base facturas profesionales)
Casilla 09: Retenciones practicadas sobre profesionales

RESULTADO:
Casilla 28: Total retenciones e ingresos a cuenta
Casilla 29: A deducir (retenciones ingresadas en exceso anteriormente, si aplica)
Casilla 30: RESULTADO A INGRESAR = 28 - 29
```

## Ejemplo práctico — Trimestre con pagos a tutores autónomos

### Datos:
- 5 tutores autónomos han facturado a la S.L. este trimestre
- Total base imponible facturas: 4.000€
- Retención IRPF aplicada por los tutores: 15% = 600€
- No hay nóminas (fase pre-ingresos, nadie cobra)

### Cálculo:
```
Casilla 07: 5 (nº perceptores profesionales)
Casilla 08: 4.000€ (base)
Casilla 09: 600€ (retenciones)

Casilla 28: 600€
Casilla 30: 600€ A INGRESAR
```

La S.L. paga 600€ a Hacienda en concepto de retenciones IRPF de los tutores.

## Retenciones aplicables

| Tipo de pago | Retención IRPF |
|-------------|---------------|
| Nómina administrador/trabajador | Según tablas IRPF (variable) |
| Factura autónomo profesional | 15% |
| Factura nuevo autónomo (<3 años) | 7% |
| Factura autónomo agrario | 2% |
| Premios en metálico | 19% |

## Importante para tutores

- Si el tutor factura con retención del 15%: la S.L. le paga el 85% y el 15% va a Hacienda (111)
- Si el tutor factura con retención del 7% (nuevo autónomo): la S.L. retiene menos
- **La S.L. es responsable de ingresar las retenciones**: si no lo hacéis, la deuda es de la S.L.

## Retenciones a administradores (cuando haya nómina)

Cuando los co-CEOs cobren nómina como administradores, las retenciones se declaran en este mismo modelo 111:
- **Casillas 01-03**: rendimientos del trabajo (nº perceptores, base, retenciones)
- Tipo fijo: **35%** general o **19%** si cifra de negocios <100.000€ (Art. 101.2.b RIRPF, RD 439/2007)
- En el Modelo 190 anual: clave **B.01**

Para guía completa con ejemplo numérico, cálculo de coste y conexión con modelos fiscales, ver `nominas-retenciones-administradores.md`.
