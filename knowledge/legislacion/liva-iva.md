# IVA — Ley 37/1992 (LIVA) — Aplicación al Marketplace Educativo

## Régimen general

La S.L. opera en régimen general de IVA. Obligaciones:
- Repercutir IVA en sus facturas
- Deducir IVA soportado en sus compras/gastos
- Liquidar trimestralmente la diferencia (Modelo 303)

## Tipos impositivos (Art. 90-91 LIVA)

| Tipo | Porcentaje | Ejemplos |
|------|-----------|----------|
| General | 21% | Servicios de intermediación, comisiones, software, hosting |
| Reducido | 10% | Alimentos, transporte, hostelería |
| Superreducido | 4% | Pan, leche, libros, periódicos |

**La comisión de intermediación del marketplace tributa al 21%.**

## ⚠️ Exención de IVA en enseñanza — Art. 20.Uno.9º LIVA

### Texto legal (resumen)
Están exentas de IVA:
> "La educación de la infancia y de la juventud, la guarda y custodia de niños [...] la enseñanza escolar, universitaria y de postgraduados, la enseñanza de idiomas y la formación y reciclaje profesional, realizadas por **entidades de derecho público o entidades privadas autorizadas** para el ejercicio de dichas actividades."

### Análisis para vuestro marketplace

**¿Aplica esta exención a la S.L.?**

**PROBABLEMENTE NO**, por tres razones:

1. **La S.L. no imparte enseñanza**: Es un intermediario/marketplace. Quien enseña es el tutor, no la plataforma. La S.L. cobra una comisión de intermediación.

2. **"Entidad privada autorizada"**: La exención requiere que la entidad sea un centro educativo autorizado por la administración competente (Consejería de Educación). Un marketplace no es un centro educativo autorizado.

3. **Doctrina DGT**: La DGT ha sido restrictiva con esta exención. Consultas V0180-20, V2314-18: la exención no se extiende a servicios accesorios de intermediación.

### Consecuencia práctica
- La S.L. **debe repercutir IVA al 21%** sobre su comisión de intermediación
- Si el tutor es autónomo y factura a la S.L., esa factura llevará IVA 21% (soportado deducible para la S.L.)
- Si el tutor está exento de IVA (por ser persona física que imparte enseñanza particular — Art. 20.Uno.10º LIVA), su factura será sin IVA

### IVA del tutor como persona física
**Art. 20.Uno.10º LIVA**: Exentas las clases particulares por personas físicas sobre materias incluidas en planes de estudios del sistema educativo.
- Si el tutor da clases de matemáticas (incluida en plan de estudios) → **exento de IVA**
- Si el tutor da clases de guitarra (no en plan de estudios) → **IVA 21%**
- **Esto afecta al IVA soportado por la S.L.**: las facturas de tutores exentos no generan IVA deducible

## Modelo 303 — Autoliquidación trimestral IVA

### Estructura del cálculo
```
IVA REPERCUTIDO (ventas/servicios)
+ IVA facturado a estudiantes sobre comisión de intermediación
= Total IVA devengado (casilla 03)

IVA SOPORTADO (compras/gastos)
+ IVA de facturas de proveedores (hosting, software, servicios profesionales)
+ IVA de facturas de tutores (solo los no exentos)
= Total IVA deducible (casilla 29)

RESULTADO = Devengado - Deducible
- Si positivo → a ingresar
- Si negativo → a compensar en trimestres siguientes (o solicitar devolución en T4)
```

### Casillas clave del 303
| Casilla | Concepto |
|---------|----------|
| 01-03 | IVA devengado al 21% (base + cuota) |
| 04-06 | IVA devengado al 10% (si aplica) |
| 07-09 | IVA devengado al 4% (si aplica) |
| 28-29 | Total IVA deducible por cuotas soportadas |
| 46 | Resultado del período |
| 64-65 | A compensar / resultado a ingresar |
| 66 | Solo en T4: a devolver |

### Plazos de presentación
| Trimestre | Período | Plazo |
|-----------|---------|-------|
| T1 (enero-marzo) | 1-20 abril | 20 abril |
| T2 (abril-junio) | 1-20 julio | 20 julio |
| T3 (julio-septiembre) | 1-20 octubre | 20 octubre |
| T4 (octubre-diciembre) | 1-30 enero | 30 enero (+ Modelo 390) |

## Modelo 390 — Resumen anual IVA

- Se presenta junto con el T4 (enero)
- Resumen de los 4 trimestres
- Deben cuadrar los datos con los 4 Modelos 303 presentados
- Plazo: 1-30 de enero del año siguiente

## Reglas de facturación IVA

### Requisitos de factura (RD 1619/2012, Art. 6)
Toda factura debe contener:
1. Número y serie (correlativo)
2. Fecha de expedición
3. NIF y datos del emisor
4. NIF y datos del destinatario
5. Descripción de la operación
6. Base imponible
7. Tipo impositivo
8. Cuota de IVA
9. Importe total
10. Si aplica exención: artículo de ley que la ampara

### Factura simplificada (ticket)
- Solo para importes <400€ (o <3.000€ en ciertos sectores)
- No requiere datos del destinatario
- **Para el marketplace**: probablemente no aplica, ya que se necesita factura completa para deducciones

## IVA en operaciones intracomunitarias
- Si contratáis servicios de empresas de la UE (ej: hosting en Irlanda, SaaS de Alemania):
  - Inversión del sujeto pasivo (Art. 84.Uno.2º LIVA)
  - Autorrepercutís IVA (casillas 10-11 del 303) + lo deducís (efecto neutro)
  - Obligación de presentar Modelo 349 (operaciones intracomunitarias)
- Daos de alta en el ROI (Registro de Operadores Intracomunitarios) si usáis SaaS europeo

## SII (Suministro Inmediato de Información)
- Obligatorio para empresas >6M€ de facturación
- **No aplica a vuestra S.L. inicialmente**, pero Holded lo soporta si crecéis

## Verifactu / Facturación electrónica (RD 1007/2023)
- Desde 2026: todos los empresarios deben usar software de facturación que garantice integridad
- Holded ya está adaptándose a Verifactu
- Verificar el calendario exacto de entrada en vigor para PYMES
