# Título de la Sesión: Trabajo práctico: integración final, pruebas y validación del robot.

## Introducción
La etapa final del proyecto consiste en ensamblar los subsistemas definidos, ejecutar pruebas funcionales y contrastar el comportamiento real del robot con las metas previstas. En esta fase se evalúan tanto el desempeño técnico como la calidad del proceso de integración, la interpretación de telemetría y la capacidad de diagnóstico ante fallas o desviaciones del diseño.

## Objetivo de Aprendizaje
Integrar y validar un robot móvil con telemetría mediante pruebas funcionales, análisis de desempeño y diagnóstico básico de fallas en sensores, alimentación o accionamiento.

## Desarrollo del Tema (Explicación de la tecnología)
La validación del robot requiere comprobar que cada subsistema funciona de manera individual y conjunta. Una estrategia ordenada reduce riesgos y facilita identificar el origen de fallas.

### Pruebas funcionales mínimas
Las pruebas deben cubrir al menos:
- encendido estable del sistema,
- lectura coherente del sensor de distancia,
- monitoreo correcto del voltaje de batería,
- estimación consistente de velocidad,
- reacción del robot ante obstáculo o condición crítica,
- transmisión de telemetría sin pérdida evidente de información.

### Análisis comparativo teoría-práctica
La integración real introduce desviaciones por ruido, fricción, caídas de tensión, latencia de comunicación y tolerancias de componentes. Por ello, se debe comparar:
- autonomía estimada versus autonomía observada,
- distancia esperada versus distancia medida,
- velocidad teórica versus velocidad real,
- umbral de batería calculado versus activación efectiva de la alarma.

### Indicadores de desempeño
Pueden adoptarse indicadores simples como:

$$
\text{error porcentual} = \frac{|x_{med} - x_{teo}|}{x_{teo}} \times 100\%
$$

para cuantificar discrepancias en variables relevantes cuando el valor teórico o de referencia esté disponible.

### Diagnóstico de fallas
Algunas fallas típicas incluyen:
- lectura errática del sensor por ruido o mala orientación,
- telemetría incompleta por problemas de enlace o formato,
- caída súbita de tensión al arrancar motores,
- conteo incorrecto de pulsos de velocidad,
- falta de respuesta ante obstáculo por error de umbral o acondicionamiento.

El diagnóstico debe apoyarse en mediciones, observación del comportamiento y análisis de interdependencia entre bloques.

```mermaid
flowchart LR
    A[Subsistemas validados por separado] --> B[Integración del robot]
    B --> C[Pruebas funcionales]
    C --> D[Mediciones y telemetría]
    D --> E[Comparación con diseño]
    E --> F[Diagnóstico y mejora]
```

## Preguntas Orientadoras
1. ¿Qué pruebas deben ejecutarse antes de considerar que el robot está listo para demostración?
2. ¿Cómo se diferencia una falla de sensor de una falla de procesamiento o comunicación?
3. ¿Por qué es importante comparar el comportamiento real con los cálculos preliminares del diseño?
4. ¿Qué variables permiten detectar primero una degradación de batería o una sobrecarga del sistema?
5. ¿Cómo debe organizarse la evidencia experimental para sustentar conclusiones técnicas?

## Ejercicios Propuestos
1. Proponga una secuencia lógica de pruebas para validar un robot móvil con telemetría antes de su operación completa.
2. Si la velocidad teórica es $0.8\,\text{m/s}$ y la medida es $0.68\,\text{m/s}$, calcule el error porcentual.
3. Describa dos causas posibles de que el robot se reinicie al arrancar los motores.
4. Explique cómo verificaría si una alarma de batería baja se activa en el umbral correcto.
5. Proponga un formato breve de registro de resultados para documentar pruebas y fallas observadas.

## Actividad en Clase (Hands-on)
**Práctica guiada: puesta en marcha y validación del proyecto**

1. Encender el sistema y verificar alimentación y consumo general.
2. Probar individualmente sensor de distancia, medición de batería y sensor de velocidad.
3. Integrar la telemetría y registrar variables durante movimiento controlado.
4. Ejecutar pruebas con obstáculo y con condición simulada de batería baja.
5. Documentar discrepancias respecto del diseño original.
6. Presentar conclusiones y propuestas de mejora técnica del robot.

## Recursos Adicionales
- Siegwart, R., Nourbakhsh, I. R., & Scaramuzza, D. *Introduction to Autonomous Mobile Robots*. MIT Press.
- Documentación técnica de sensores, drivers de motor y módulos de telemetría usados en el proyecto.
- Guías de validación de sistemas embebidos y prácticas de prueba incremental de prototipos mecatrónicos.
- Plantillas de bitácora de laboratorio para pruebas de integración y diagnóstico.
