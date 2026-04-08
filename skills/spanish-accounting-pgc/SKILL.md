---
name: spanish-accounting-pgc
description: "Contabilidad PGC PYMES, asientos contables, balance, PyG, cuentas anuales para S.L. española. Usar cuando se pregunte sobre contabilidad, asientos tipo, plan de cuentas, cierre contable, o preparación de cuentas anuales."
---

# Spanish Accounting PGC

## When to Use
Use this skill when the user:
- Asks about accounting entries (asientos contables)
- Needs help with the chart of accounts (PGC PYMES)
- Wants to prepare annual accounts (cuentas anuales)
- Asks about depreciation/amortization
- Needs help with account reconciliation
- Wants to understand balance sheet or P&L structure

## Knowledge Base Files
- `knowledge/legislacion/obligaciones-mercantiles.md` — Cuentas anuales, libros, plazos
- `knowledge/marketplace-educativo/flujo-facturacion.md` — Asientos tipo del marketplace
- `operativa/contabilidad/plan-cuentas-pgc.md` — Plan de cuentas adaptado
- `operativa/contabilidad/asientos-tipo.md` — Asientos recurrentes

## Chart of Accounts — PGC PYMES (Cuentas principales para marketplace educativo)

### Grupo 1: Financiación básica
- 100 Capital social (3.000€)
- 112 Reserva legal
- 113 Reservas voluntarias
- 120 Remanente
- 129 Resultado del ejercicio
- 170 Deudas a largo plazo con entidades de crédito

### Grupo 2: Inmovilizado
- 206 Aplicaciones informáticas (software — aportación no dineraria CTO)
- 217 Equipos para procesos de información (servidores, ordenadores)
- 280 Amortización acumulada inmovilizado intangible
- 281 Amortización acumulada inmovilizado material

### Grupo 3: Existencias — NO APLICA (servicio puro)

### Grupo 4: Acreedores y deudores
- 410 Acreedores por prestación de servicios (tutores pendientes de pago)
- 430 Clientes (estudiantes pendientes de cobro)
- 4700 HP deudora por IVA (IVA a compensar)
- 4750 HP acreedora por IVA (IVA a ingresar)
- 4751 HP acreedora retenciones IRPF
- 473 HP retenciones y pagos a cuenta
- 476 Organismos SS acreedores

### Grupo 5: Cuentas financieras
- 572 Bancos (cuenta corriente S.L.)
- 573 Bancos — pasarela de pago (Stripe escrow)

### Grupo 6: Compras y gastos
- 621 Arrendamientos (oficina/coworking)
- 622 Reparaciones y conservación
- 623 Servicios profesionales (abogado, contable puntual)
- 625 Primas de seguros
- 626 Servicios bancarios y similares (comisiones Stripe, comisiones banco)
- 627 Publicidad y marketing
- 628 Suministros (internet, teléfono, electricidad)
- 629 Otros servicios (hosting, software, suscripciones, Claude)
- 640 Sueldos y salarios (cuando se paguen nóminas)
- 642 SS a cargo de la empresa
- 681 Amortización del inmovilizado intangible
- 682 Amortización del inmovilizado material

### Grupo 7: Ventas e ingresos
- 705 Prestación de servicios (comisiones del marketplace)
- 759 Ingresos por servicios diversos

## Asientos Tipo

### Cobro de reserva (estudiante paga 36,30€, comisión 20%)
```
(572) Bancos              36,30
    (705) Ingresos comisión       6,00
    (477) IVA repercutido         6,30
    (410) Acreedores tutor       24,00
```

### Pago al tutor autónomo (con retención 15%)
```
(410) Acreedores tutor    24,00
(472) IVA soportado        5,04  [solo si tutor no exento]
    (572) Bancos                 25,44  [24€ - 3,60€ ret + 5,04€ IVA]
    (4751) HP ret IRPF            3,60
```

### Gasto de hosting mensual (100€ + IVA)
```
(629) Otros servicios    100,00
(472) IVA soportado       21,00
    (572) Bancos                121,00
```

### Pago cuota autónomo societario (380€/mes)
```
(642) SS empresa         380,00
    (476) Organismos SS          380,00

(476) Organismos SS      380,00
    (572) Bancos                 380,00
```

### Liquidación IVA trimestral (a ingresar 924€)
```
(477) IVA repercutido   [total trimestre]
    (472) IVA soportado         [total trimestre]
    (4750) HP acreedora IVA      924,00

(4750) HP acreedora IVA   924,00
    (572) Bancos                  924,00
```

## Tablas de Amortización (PGC)

| Elemento | Coef. máximo | Período máx. | ERD (×2) |
|----------|-------------|-------------|----------|
| Aplicaciones informáticas | 33% | 6 años | 66% (1.5 años) |
| Equipos informáticos | 25% | 8 años | 50% (2 años) |
| Mobiliario | 10% | 20 años | 20% (5 años) |
| Elementos de transporte | 16% | 14 años | 32% |

**Con ERD**: amortización acelerada = el doble del coeficiente máximo (Art. 103 LIS).

## Critical Rules
- Seguir PGC PYMES (RD 1515/2007, no el PGC completo)
- Los asientos deben SIEMPRE cuadrar (debe = haber)
- La aportación no dineraria del CTO se registra como inmovilizado intangible (206) contra capital (100)
- Las comisiones de Stripe van a cuenta 626, no a 629
