# Plan de Cuentas PGC PYMES — Adaptado al Marketplace Educativo

## Grupo 1: Financiación básica

| Cuenta | Nombre | Uso en la S.L. |
|--------|--------|----------------|
| 100 | Capital social | 3.000€ (2.700 dinerario + 300 no dinerario) |
| 112 | Reserva legal | 10% del beneficio hasta llegar al 20% del capital |
| 113 | Reservas voluntarias | Beneficios no distribuidos |
| 120 | Remanente | Beneficios de ejercicios anteriores sin aplicar |
| 121 | Resultados negativos ejercicios anteriores | Pérdidas acumuladas |
| 129 | Resultado del ejercicio | Beneficio o pérdida del año en curso |

## Grupo 2: Inmovilizado

| Cuenta | Nombre | Uso |
|--------|--------|-----|
| 206 | Aplicaciones informáticas | Prototipo/beta aportado por CTO (300€) + software desarrollado |
| 217 | Equipos para procesos de información | Ordenadores, servidores |
| 218 | Elementos de transporte | Solo si la S.L. tiene vehículo |
| 280 | Amort. acum. inmov. intangible | Amortización del software |
| 281 | Amort. acum. inmov. material | Amortización equipos |

## Grupo 4: Acreedores y deudores por operaciones comerciales

| Cuenta | Nombre | Uso |
|--------|--------|-----|
| 400 | Proveedores | Proveedores generales (hosting, software, etc.) |
| 410 | Acreedores prestación servicios | Tutores pendientes de pago |
| 430 | Clientes | Estudiantes/familias con cobro pendiente |
| 4300 | Clientes — cobro pasarela | Importes en tránsito en Stripe |
| 465 | Remuneraciones pendientes de pago | Nóminas pendientes (cuando se paguen) |
| 470 | HP deudora por conceptos fiscales | IVA a compensar, IS a devolver |
| 4700 | HP deudora por IVA | IVA a compensar de trimestres anteriores |
| 4709 | HP deudora por IS | IS a devolver |
| 472 | HP IVA soportado | IVA de facturas de compras (transitoria) |
| 473 | HP retenciones y pagos a cuenta | Retenciones a favor de la S.L. |
| 475 | HP acreedora conceptos fiscales | IVA a ingresar, retenciones a pagar |
| 4750 | HP acreedora por IVA | IVA a ingresar (liquidación 303) |
| 4751 | HP acreedora por retenciones IRPF | Retenciones practicadas a tutores/empleados |
| 4752 | HP acreedora por IS | IS a pagar (Modelo 200) |
| 476 | Organismos SS acreedores | Cuotas SS pendientes de pago |
| 477 | HP IVA repercutido | IVA de facturas de ventas (transitoria) |

## Grupo 5: Cuentas financieras

| Cuenta | Nombre | Uso |
|--------|--------|-----|
| 570 | Caja | Efectivo (improbable en marketplace digital) |
| 572 | Bancos c/c | Cuenta corriente principal de la S.L. |
| 5720 | Banco — Cuenta operativa | Cuenta principal (Qonto/Revolut/banco) |
| 5721 | Banco — Stripe/Pasarela | Saldo en la pasarela de pago |
| 527 | Intereses a corto plazo de deudas | Intereses de préstamos (si los hay) |

## Grupo 6: Compras y gastos

| Cuenta | Nombre | Uso típico |
|--------|--------|-----------|
| 621 | Arrendamientos y cánones | Alquiler oficina/coworking |
| 622 | Reparaciones y conservación | Mantenimiento equipos |
| 623 | Servicios de profesionales independientes | Abogado, contable, consultor puntual |
| 624 | Transportes | Desplazamientos profesionales |
| 625 | Primas de seguros | Seguro RC, seguro ciber |
| 626 | Servicios bancarios y similares | Comisiones banco, Stripe, Redsys |
| 627 | Publicidad, propaganda y RRPP | Google Ads, Meta Ads, marketing contenidos |
| 628 | Suministros | Internet, teléfono, electricidad (proporción) |
| 629 | Otros servicios | Hosting, dominio, suscripciones SaaS, Claude, Holded |
| 631 | Otros tributos | IAE (exento <1M€), tasas RM |
| 640 | Sueldos y salarios | Nóminas (cuando se paguen) |
| 642 | Seguridad Social a cargo empresa | Cuota SS de administradores/empleados |
| 649 | Otros gastos sociales | Formación, eventos equipo |
| 662 | Intereses de deudas | Intereses de préstamos (ENISA, banco) |
| 681 | Amortización inmov. intangible | Amortización software |
| 682 | Amortización inmov. material | Amortización equipos |
| 694 | Pérdidas por deterioro créditos | Provisión insolvencias (1% global ERD) |

## Grupo 7: Ventas e ingresos

| Cuenta | Nombre | Uso |
|--------|--------|-----|
| 705 | Prestación de servicios | **Comisiones del marketplace** (ingreso principal) |
| 759 | Ingresos por servicios diversos | Otros ingresos (publicidad en la plataforma, etc.) |
| 769 | Otros ingresos financieros | Intereses bancarios |
| 778 | Ingresos excepcionales | Subvenciones, indemnizaciones |

## Cuentas especiales para el marketplace

### Flujo de pago Stripe → Banco

Cuando Stripe hace un payout (transfiere dinero acumulado al banco):
```
(5720) Banco cuenta operativa    [importe]
    (5721) Banco Stripe                [importe]
```

### Comisión de Stripe (cobrada automáticamente):
```
(626) Servicios bancarios    [comisión]
(472) IVA soportado          [IVA de la comisión - inversión sujeto pasivo]
    (5721) Banco Stripe             [comisión + IVA]
    (477) IVA repercutido           [IVA autorepercutido - inversión SP]
```
