# Asientos Tipo — Marketplace Educativo

## 1. Constitución de la S.L.

### 1.1 Aportación dineraria de los co-CEOs
```
(572) Bancos                2.700,00
    (100) Capital social           2.700,00

Detalle:
- Co-CEO 1: 1.350€
- Co-CEO 2: 1.350€
```

### 1.2 Aportación no dineraria del CTO (prototipo/beta)
```
(206) Aplicaciones informáticas   300,00
    (100) Capital social                300,00
```

## 2. Operativa diaria del marketplace

### 2.1 Cobro de reserva (estudiante paga 36,30€ vía Stripe)
Precio tutor: 24€, Comisión S.L.: 6€ (20%), IVA 21% sobre total
```
(5721) Banco Stripe          36,30
    (705) Prestación servicios       6,00
    (477) HP IVA repercutido         6,30
    (410) Acreedores tutor          24,00
```

### 2.2 Comisión de Stripe sobre la transacción (1.5% + 0.25€ = 0.79€)
Stripe factura desde Irlanda → inversión sujeto pasivo
```
(626) Servicios bancarios     0,79
(472) HP IVA soportado        0,17  (21% de 0,79 - autorepercutido)
    (5721) Banco Stripe              0,79
    (477) HP IVA repercutido         0,17  (autorepercutido = efecto neutro)
```

### 2.3 Pago al tutor autónomo (factura con IRPF 15%, exento IVA)
Tutor exento IVA (Art. 20.Uno.10º LIVA) — da clases de materia del SE
```
(410) Acreedores tutor      24,00
    (572) Bancos                    20,40
    (4751) HP ret. IRPF practicadas  3,60
```

### 2.4 Pago al tutor autónomo (factura con IVA 21% + IRPF 15%)
Tutor NO exento (materia fuera del SE, o es empresa)
```
(410) Acreedores tutor      24,00
(472) HP IVA soportado       5,04
    (572) Bancos                    25,44
    (4751) HP ret. IRPF practicadas  3,60
```

### 2.5 Payout de Stripe al banco (transferencia semanal)
```
(5720) Banco operativo     [importe neto]
    (5721) Banco Stripe           [importe neto]
```

## 3. Gastos operativos

### 3.1 Hosting mensual (ej: 50€ + IVA, proveedor España)
```
(629) Otros servicios        50,00
(472) HP IVA soportado       10,50
    (572) Bancos                    60,50
```

### 3.2 Hosting/SaaS proveedor UE (ej: AWS Irlanda, 100€)
Inversión sujeto pasivo:
```
(629) Otros servicios       100,00
(472) HP IVA soportado       21,00
    (572) Bancos                   100,00
    (477) HP IVA repercutido        21,00  (autorepercutido)
```
Nota: el IVA se autorepercute y se deduce → efecto neutro, pero debe declararse en 303

### 3.3 Suscripción Claude (200€/mes, proveedor Anthropic USA)
Importación de servicios extracumunitarios → sujeto pasivo es la S.L.
```
(629) Otros servicios       200,00
(472) HP IVA soportado       42,00
    (572) Bancos                   200,00
    (477) HP IVA repercutido        42,00  (autorepercutido)
```

### 3.4 Publicidad Google Ads (ej: 300€, Google Ireland)
```
(627) Publicidad            300,00
(472) HP IVA soportado       63,00
    (572) Bancos                   300,00
    (477) HP IVA repercutido        63,00
```

### 3.5 Cuota autónomo societario (380€/mes, co-CEO 1)
Si la S.L. asume la cuota:
```
(642) SS a cargo empresa    380,00
    (476) Organismos SS            380,00

(476) Organismos SS         380,00
    (572) Bancos                   380,00
```

### 3.6 Factura de abogado (500€ + IVA, retención 15%)
```
(623) Servicios profesionales  500,00
(472) HP IVA soportado         105,00
    (572) Bancos                      530,00
    (4751) HP ret. IRPF practicadas    75,00
```

## 4. Liquidaciones fiscales

### 4.1 Liquidación IVA trimestral (a ingresar)
```
(477) HP IVA repercutido    [total T]
    (472) HP IVA soportado         [total T]
    (4750) HP acreedora IVA        [diferencia a ingresar]

(4750) HP acreedora IVA     [importe]
    (572) Bancos                   [importe]
```

### 4.2 Liquidación IVA trimestral (a compensar)
```
(477) HP IVA repercutido    [total T]
(4700) HP deudora IVA       [diferencia a compensar]
    (472) HP IVA soportado         [total T]
```

### 4.3 Ingreso retenciones IRPF (Modelo 111)
```
(4751) HP ret. IRPF         [total retenciones T]
    (572) Bancos                   [importe]
```

### 4.4 Pago fraccionado IS (Modelo 202)
```
(473) HP retenciones y pagos a cuenta  [importe]
    (572) Bancos                              [importe]
```

### 4.5 Provisión IS anual (al cierre del ejercicio)
```
(6300) Impuesto sobre beneficios  [cuota IS estimada]
    (4752) HP acreedora IS               [cuota IS estimada]
```

## 5. Cierre del ejercicio

### 5.1 Regularización de ingresos y gastos (asiento de cierre)
```
(705) Prestación servicios  [total anual]
(759) Otros ingresos        [total]
    (621,623,626,627,628,629,640,642,681,682,...) Gastos  [total]
    (129) Resultado del ejercicio                         [diferencia]
```

### 5.2 Amortización anual del software (33% anual, o 66% ERD)
```
(681) Amort. inmov. intangible   [cuota anual]
    (280) Amort. acum. inmov. intangible  [cuota anual]
```
Ejemplo: Software CTO 300€ × 66% (ERD) = 198€ primer año
```
(681) Amort. inmov. intangible   198,00
    (280) Amort. acum. inmov. intangible  198,00
```

### 5.3 Dotación a reserva legal (10% del beneficio si 129 > 0)
Art. 274 LSC: obligatorio destinar 10% a reserva legal hasta que alcance el 20% del capital (600€)
```
(129) Resultado ejercicio    [10% del beneficio]
    (112) Reserva legal            [10% del beneficio]
```
