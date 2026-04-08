# Falsos Autónomos — Riesgo Inspección de Trabajo

## ⚠️ EL MAYOR RIESGO LEGAL DE VUESTRO MODELO DE NEGOCIO

## Contexto

La Inspección de Trabajo puede considerar que los tutores que trabajan a través del marketplace NO son autónomos reales, sino **trabajadores por cuenta ajena disfrazados de autónomos** ("falsos autónomos").

**Consecuencia si se confirma**: la S.L. debería haberlos contratado como trabajadores, con todas las obligaciones:
- Alta en Seguridad Social (cuota empresa ~30% del salario)
- Convenio colectivo aplicable
- Vacaciones, indemnización por despido, etc.
- **Liquidación retroactiva de cuotas SS no cotizadas + recargo del 100-150%**
- **Sanción: 3.126€ a 10.000€ POR CADA trabajador** (Art. 40.1.d) LISOS)

## Base legal

### Art. 1.1 Estatuto de los Trabajadores
> "La presente ley será de aplicación a los trabajadores que voluntariamente presten sus servicios retribuidos por cuenta ajena y dentro del ámbito de organización y dirección de otra persona, física o jurídica, denominada empleador o empresario."

### Indicios de laboralidad (jurisprudencia TS)

**STS 25/09/2020 (caso Glovo/riders)** — Sentencia referencia:

| Indicio | Peso | Descripción |
|---------|------|-------------|
| **Ajenidad en los frutos** | ALTO | Los frutos del trabajo benefician al empresario, no al trabajador |
| **Ajenidad en los riesgos** | ALTO | El trabajador no asume riesgo empresarial |
| **Dependencia organizativa** | ALTO | El empresario organiza el trabajo (horarios, métodos, etc.) |
| **Control de precios** | ALTO | El empresario fija el precio, no el trabajador |
| **Herramientas del empresario** | MEDIO | El trabajador usa medios del empresario (plataforma, marca) |
| **Exclusividad de facto** | MEDIO | El trabajador depende económicamente del empresario |
| **Imposibilidad de rechazo** | MEDIO | No puede rechazar encargos sin penalización |
| **Uniformidad de servicio** | BAJO | El empresario impone estándares de calidad/vestimenta |

### Ley Rider (RDL 9/2021) — Presunción de laboralidad en plataformas digitales

> Disposición adicional 23ª ET: "se presume incluida en el ámbito de esta ley la actividad de las personas que presten servicios retribuidos consistentes en el reparto o distribución de cualquier producto de consumo o mercancía, por parte de empleadoras que ejercen las facultades empresariales de organización, dirección y control de forma directa, indirecta o implícita, mediante la gestión algorítmica del servicio o de las condiciones de trabajo, a través de una plataforma digital."

**Nota**: Esta presunción es específica para **reparto/distribución**, no para tutorías. PERO la Inspección de Trabajo usa la misma lógica para CUALQUIER plataforma que controle el servicio.

## Análisis de riesgo para VUESTRO marketplace

### Indicios que os PERJUDICAN (sugieren laboralidad)

| Indicio | Situación en vuestro marketplace | Riesgo |
|---------|--------------------------------|--------|
| La plataforma fija el precio | ¿La S.L. decide cuánto cobra el tutor? | ALTO si sí |
| La plataforma controla el matching | Algoritmo asigna tutor → control organizativo | MEDIO |
| Penalización por rechazo/cancelación | ¿Bajan en ranking si rechazan clases? | ALTO si sí |
| El pago pasa por la plataforma | Sí (pasarela de pago) → la S.L. controla el flujo | MEDIO |
| Marca de la plataforma | El tutor actúa "como parte" de la plataforma | BAJO-MEDIO |
| No puede usar la marca libremente | El tutor no puede presentarse como "de [marca]" fuera | BAJO |

### Indicios que os FAVORECEN (sugieren autonomía real)

| Indicio | Cómo implementarlo | Importancia |
|---------|-------------------|-------------|
| **Tutor fija su propio precio** | El tutor decide su tarifa por hora | CRÍTICO |
| **Tutor elige sus horarios** | Sin horarios fijos ni mínimos de disponibilidad | CRÍTICO |
| **Tutor puede rechazar encargos** | Sin penalización por rechazar alumnos | ALTO |
| **Tutor trabaja para múltiples plataformas** | No exclusividad | ALTO |
| **Tutor usa sus propios medios** | Su ordenador, su conexión, su espacio | MEDIO |
| **Tutor tiene su propia cartera** | Puede captar alumnos por su cuenta | ALTO |
| **Contrato mercantil** (no laboral) | Contrato de intermediación, no de trabajo | MEDIO |
| **Tutor factura** | Emite factura como autónomo/persona física | MEDIO |

## Arquitectura operativa para MINIMIZAR el riesgo

### 1. Precio libre
- **El tutor fija su tarifa**. La S.L. NO impone precios mínimos ni máximos.
- La S.L. solo cobra un % de comisión sobre lo que el tutor decide cobrar.
- Mostrar claramente en las condiciones: "Cada tutor establece su propia tarifa."

### 2. Horarios libres
- **El tutor decide cuándo está disponible**. La S.L. NO impone horarios ni jornada mínima.
- No penalizar por inactividad o baja disponibilidad.
- No hay "turnos" ni "obligación de dar X clases/semana".

### 3. Libertad de rechazo
- **El tutor puede rechazar cualquier solicitud** sin consecuencia negativa.
- No bajar en rankings ni perder visibilidad por rechazar.
- NUNCA asignar automáticamente clases sin confirmación del tutor.

### 4. No exclusividad
- **Permitir explícitamente** que el tutor trabaje en otras plataformas.
- Incluir cláusula en contrato: "El Prestador es libre de trabajar para terceros."
- NUNCA incluir cláusula de exclusividad.

### 5. Contrato de intermediación
- **Contrato mercantil de prestación de servicios de intermediación**, NO contrato de trabajo.
- El contrato establece que la S.L. es intermediario, no empleador.
- El tutor es un profesional independiente que usa la plataforma como canal.

### 6. Facturación correcta
- Si el tutor tiene >3.005,06€/año de ingresos: debería darse de alta como autónomo y facturar.
- Si los ingresos son esporádicos y bajos: posible declarar como rendimiento de actividad económica sin alta en RETA (umbral discutido, pero posible si no es actividad habitual).
- **La S.L. debe guardar las facturas** de TODOS los tutores.

### 7. Flujo de pago
- Opción A: **El estudiante paga a la S.L.**, la S.L. retiene comisión, el resto se transfiere al tutor → más control pero más riesgo de laboralidad
- Opción B: **El estudiante paga al tutor directamente** y la S.L. cobra la comisión por separado → menos control, menos riesgo
- **Recomendación**: Opción A (necesario para el modelo de negocio), pero documentar que es puramente un servicio de cobro/pasarela.

## Documentación defensiva

### Qué documentar y guardar
1. **Contrato de intermediación** firmado con cada tutor
2. **Condiciones de uso de la plataforma** que establezcan la relación como intermediación
3. **Evidencia de libertad de precios** (historial de precios fijados por tutores diferentes)
4. **Evidencia de libertad de horarios** (captura de disponibilidad variable)
5. **Evidencia de no exclusividad** (tutores que trabajan en otras plataformas)
6. **Facturas de tutores** o documentos equivalentes
7. **Comunicación con tutores** que confirme la naturaleza independiente

### Lo que NUNCA hacer
- ❌ Imponer precio o descuentos sin consentimiento del tutor
- ❌ Exigir horarios fijos de disponibilidad
- ❌ Penalizar por rechazar clases o cancelar
- ❌ Obligar a usar uniforme o scripts de la plataforma
- ❌ Evaluar "rendimiento" como si fuera un empleado
- ❌ Dar instrucciones sobre CÓMO dar la clase (solo facilitar el medio)
- ❌ Cláusula de exclusividad
- ❌ Pagar la SS del tutor (eso confirma laboralidad)
