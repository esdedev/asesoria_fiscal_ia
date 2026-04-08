# Verifactu — Facturación Electrónica Obligatoria

## Marco normativo

- **RD 1007/2023**, de 5 de diciembre — Reglamento que establece los requisitos de los sistemas informáticos de facturación (Reglamento Verifactu)
- **Orden HAC/1177/2024** — Especificaciones técnicas del sistema Verifactu
- **Ley 18/2022 (Ley Crea y Crece)**, Art. 12 — Establece la obligación de facturación electrónica B2B

## Qué es Verifactu

Verifactu es el sistema de la AEAT que exige que todos los programas de facturación:
1. **Registren** cada factura emitida de forma inalterable (hash encadenado)
2. **Envíen** los registros de facturación a la AEAT (en tiempo real o en plazo)
3. **Garanticen** la integridad de la información (no se pueden borrar ni modificar facturas sin traza)

Es distinto de la facturación electrónica B2B (que obliga a emitir y recibir facturas en formato estructurado entre empresas). Verifactu afecta al **software de facturación**; la facturación electrónica B2B afecta a las **facturas entre empresas**.

## Calendario de implantación

### Obligación del software (Verifactu — RD 1007/2023)
- **Desarrolladores de software**: deben adaptar sus programas antes del **29 de julio de 2025**
- **Empresarios y profesionales (usuarios)**: obligados a usar software adaptado. La fecha de obligación para los usuarios depende de la publicación de la orden ministerial de desarrollo — a fecha de abril 2026, pendiente de confirmación definitiva.
- **Estimación**: los contribuyentes estarán obligados a partir de **2026-2027**, dependiendo del volumen de facturación.

### Facturación electrónica B2B (Ley Crea y Crece)
- **Empresas con facturación >8M€**: obligadas a emitir factura electrónica a partir de la fecha que establezca el reglamento (previsto 2026-2027)
- **Resto de empresas y autónomos**: obligadas en un plazo posterior (previsto 2027-2028)
- **La S.L. como startup nueva**: probablemente en el segundo tramo (<8M€)

## Qué implica para la S.L.

### Impacto inmediato (pre-constitución)
1. **Al elegir software de facturación** (Holded, A3, Contasol, etc.): verificar que el software ya cumple o tiene previsto cumplir con Verifactu.
2. Holded ha anunciado compatibilidad con Verifactu — verificar estado actual al momento de la constitución.

### Impacto cuando esté en vigor
1. Cada factura emitida por la S.L. generará un registro firmado digitalmente
2. Los registros se enviarán a la AEAT automáticamente (el software lo hace)
3. No se podrán emitir facturas "en B" ni modificar facturas sin traza
4. Las facturas rectificativas deben seguir el procedimiento formal (Art. 15 RD 1619/2012)

### Factura electrónica B2B
1. Cuando entre en vigor, las facturas entre la S.L. y los tutores autónomos deberán ser electrónicas (formato Facturae o equivalente)
2. Las facturas al consumidor final (estudiantes) **no se ven afectadas inicialmente** por la obligación B2B
3. El software de facturación deberá soportar envío/recepción de facturas electrónicas estructuradas

## Requisitos técnicos esenciales (Verifactu)

| Requisito | Descripción |
|-----------|-------------|
| Registro de facturación | Cada factura genera un registro con huella digital (hash) |
| Hash encadenado | Cada registro incluye el hash del registro anterior — forma una cadena inmutable |
| Envío a AEAT | Los registros se envían telemáticamente (API de la AEAT) |
| Inalterabilidad | No se pueden borrar ni modificar registros sin dejar traza |
| Conservación | Los registros deben conservarse durante el plazo de prescripción (4 años) |

## Acción requerida

**Al constituir la S.L.:**
1. Verificar que el software de facturación elegido es compatible con Verifactu (o tiene fecha comprometida de adaptación)
2. No usar hojas de cálculo ni sistemas manuales para facturar — no cumplirán con Verifactu
3. Si se elige Holded: confirmar que la versión contratada incluye el módulo de Verifactu

**Cuando entre en vigor la facturación electrónica B2B:**
1. Configurar el software para emitir facturas en formato Facturae
2. Comunicar a los tutores autónomos que deberán poder recibir facturas electrónicas
3. Verificar que el flujo de facturación del marketplace (ver `marketplace-educativo/flujo-facturacion.md`) es compatible
