# Evaluación del Módulo 2: Taller de diseño y diagnóstico de una fuente regulada DC

## Formato de evaluación
Taller integrador con diseño cuantitativo, montaje o simulación funcional e informe técnico individual o en parejas.

## Objetivos a evaluar
1. Aplicar la relación de espiras, tensión y corriente en el análisis de transformadores utilizados en fuentes de alimentación.
2. Diseñar la etapa rectificadora adecuada y estimar su tensión promedio disponible considerando no idealidades.
3. Dimensionar el filtro capacitivo a partir de requisitos de corriente y rizado.
4. Seleccionar y justificar una estrategia de regulación DC con Zener o regulador lineal.
5. Diagnosticar fallas o insuficiencias de diseño a partir de mediciones y criterios eléctricos.

## Instrucciones detalladas
1. A partir de una especificación de salida dada por el docente, diseñe una fuente regulada DC completa compuesta por transformador, rectificador, filtro y etapa reguladora.
2. Presente el esquema del circuito, identifique cada componente crítico y justifique los valores seleccionados.
3. Calcule el voltaje secundario requerido, el voltaje pico rectificado, el rizado esperado y la tensión mínima disponible para regulación.
4. Verifique la capacidad de corriente de diodos, regulador y transformador, así como la potencia disipada en los elementos más exigidos.
5. Implemente el circuito en protoboard, simulador o banco de laboratorio y registre mediciones en vacío y bajo al menos dos condiciones de carga.
6. Analice si la regulación se mantiene y explique cualquier discrepancia entre teoría y práctica.
7. Responda un apartado de diagnóstico donde se le presenta una falla hipotética o una medición anómala y debe identificar la etapa más probable del problema.

## Desarrollo sugerido de la sesión evaluativa
- **15 min:** lectura de la especificación y planteamiento del diseño.
- **25 min:** cálculos de transformador, rectificación y filtrado.
- **25 min:** implementación o simulación.
- **20 min:** medición y diagnóstico.
- **15 min:** conclusiones y entrega.

## Entregables requeridos
1. Esquema completo de la fuente regulada.
2. Memoria de cálculo con ecuaciones, unidades y supuestos.
3. Tabla de mediciones en vacío y en carga.
4. Análisis de disipación y seguridad de componentes.
5. Diagnóstico razonado de una falla o condición anómala.
6. Conclusión final sobre desempeño de la fuente diseñada.

## Rúbrica o criterios explícitos de calificación

| Criterio | Descripción | Ponderación |
|---|---|---:|
| Diseño eléctrico | Coherencia entre especificación, topología elegida y valores de componentes | 25% |
| Cálculo y justificación | Desarrollo matemático completo, uso correcto de ecuaciones y unidades | 25% |
| Implementación o simulación | Calidad del montaje, orden de trabajo y consistencia de mediciones | 20% |
| Diagnóstico técnico | Capacidad para identificar fallas, explicar no idealidades y proponer correcciones | 20% |
| Comunicación | Claridad del informe, organización de resultados y sustento final | 10% |

## Criterios de desempeño
- **Excelente (90-100):** diseña una fuente funcional y bien justificada, cuantifica márgenes eléctricos y térmicos, e interpreta con precisión el comportamiento real del sistema.
- **Bueno (80-89):** presenta un diseño correcto con leves omisiones de detalle, mediciones consistentes y diagnóstico razonable.
- **Satisfactorio (70-79):** resuelve el esquema principal, pero con debilidades en dimensionamiento fino, análisis de rizado o disipación.
- **Insuficiente (<70):** evidencia errores conceptuales en la cadena de conversión AC-DC o falta de soporte técnico suficiente.

## Observaciones para el docente
- Valorar especialmente si el estudiante distingue entre magnitudes RMS, pico y promedio DC.
- Revisar que la selección de componentes incluya límites de corriente, voltaje y potencia.
- Exigir que toda conclusión de regulación o falla esté respaldada por ecuaciones y mediciones.
