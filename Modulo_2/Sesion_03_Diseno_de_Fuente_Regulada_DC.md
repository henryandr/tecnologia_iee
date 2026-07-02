# Título de la Sesión: Diseño e implementación de una fuente regulada de corriente directa.

## Introducción
El diseño de una fuente regulada DC integra todos los conceptos del módulo: transformación, rectificación, filtrado y regulación. Este bloque es una síntesis de ingeniería aplicada porque obliga a traducir especificaciones funcionales en decisiones cuantitativas sobre devanados, diodos, condensadores, disipación y estabilidad del voltaje de salida.

## Objetivo de Aprendizaje
Diseñar y justificar una fuente regulada de corriente directa a partir de una especificación de tensión y corriente de salida, integrando criterios de rectificación, filtrado y regulación.

## Desarrollo del Tema (Explicación de la tecnología)
Una fuente lineal regulada clásica puede dividirse en cuatro etapas:
1. **Transformación:** adapta el nivel de tensión AC.
2. **Rectificación:** convierte AC en DC pulsante.
3. **Filtrado:** reduce el rizado.
4. **Regulación:** estabiliza la tensión de salida frente a perturbaciones.

```mermaid
flowchart LR
    A[Red AC] --> B[Transformador]
    B --> C[Puente rectificador]
    C --> D[Condensador de filtro]
    D --> E[Regulador]
    E --> F[Salida DC]
    F --> G[Carga]
```

### Selección del transformador
Si la salida deseada es $V_o$, el secundario RMS debe elegirse considerando el valor pico tras rectificación:

$$
V_{pico} = \sqrt{2}V_{s,rms}
$$

En un puente rectificador, el capacitor se carga aproximadamente hasta:

$$
V_{C,max} \approx \sqrt{2}V_{s,rms} - 2V_D
$$

La tensión mínima sobre el condensador bajo carga es aproximadamente:

$$
V_{C,min} \approx V_{C,max} - \Delta V
$$

Para que un regulador lineal mantenga regulación, debe cumplirse:

$$
V_{C,min} \ge V_o + V_{dropout}
$$

### Dimensionamiento del filtro
Usando una aproximación de corriente constante en la carga:

$$
\Delta V \approx \frac{I_L}{f_r C}
$$

Luego,

$$
C \approx \frac{I_L}{f_r \Delta V}
$$

Esta ecuación orienta la selección inicial del condensador, que luego debe revisarse por tolerancia, ESR y corriente de rizado.

### Regulación
Puede emplearse un Zener para bajas corrientes o un regulador integrado para mayor estabilidad. En un regulador integrado lineal, la potencia disipada es:

$$
P_{reg} = (V_{in}-V_o)I_o
$$

por lo que el diseño térmico es crítico. Si se usa un Zener:

$$
R_s = \frac{V_{in}-V_Z}{I_L+I_Z}
$$

seleccionando el peor caso de carga y asegurando la corriente mínima de regulación.

### Rectificación y selección de diodos
Cada diodo debe soportar la corriente media esperada y la tensión inversa repetitiva adecuada. En una topología de puente, la caída en conducción reduce el margen disponible y eleva la disipación.

### Criterios de diseño real
- margen de seguridad en voltaje y corriente,
- disipación térmica en regulador y diodos,
- tensión máxima del condensador superior al pico esperado,
- polaridad correcta y respeto de tierra de referencia,
- compatibilidad entre frecuencia de red y especificación del transformador.

## Preguntas Orientadoras
1. ¿Cómo se determina el voltaje RMS mínimo del secundario para garantizar regulación bajo carga?
2. ¿Qué ventajas y desventajas tiene una fuente lineal frente a una conmutada en aplicaciones de laboratorio?
3. ¿Por qué un condensador muy grande no siempre resuelve por completo el problema del rizado?
4. ¿Qué riesgo implica diseñar sin considerar disipación térmica en el regulador?
5. ¿Cómo cambia el diseño si la carga consume corriente variable en lugar de constante?

## Ejercicios Propuestos
1. Diseñe una fuente de $5\,\text{V}$ y $500\,\text{mA}$ usando puente rectificador, filtro capacitivo y regulador lineal de caída mínima $2\,\text{V}$. Determine un valor adecuado del secundario RMS y del capacitor si se tolera un rizado de $1\,\text{V}$ pico a pico.
2. Para una fuente con secundario de $12\,\text{V}_{rms}$ y puente rectificador, calcule el voltaje máximo aproximado del condensador si cada diodo cae $0.8\,\text{V}$.
3. Si una fuente regulada entrega $12\,\text{V}$ a $1\,\text{A}$ y el regulador recibe $18\,\text{V}$ promedio, determine la potencia disipada por el regulador.
4. Dimensione un capacitor de filtro para $I_L=0.25\,\text{A}$, frecuencia de red de $60\,\text{Hz}$ y rizado máximo de $0.5\,\text{V}$ en un rectificador de onda completa.
5. Analice qué sucede si la tensión de red cae un $10\%$ respecto del valor nominal del transformador.

## Actividad en Clase (Hands-on)
**Práctica guiada: diseño y puesta en marcha de una fuente regulada lineal**

1. Definir una especificación objetivo de salida DC.
2. Seleccionar el transformador con base en la tensión mínima requerida por la regulación.
3. Armar el puente rectificador y medir la tensión sin filtrar.
4. Incorporar el condensador de filtro y medir el rizado.
5. Añadir la etapa reguladora y verificar estabilidad frente a cambios de carga.
6. Elaborar balance de potencia disipada en diodos y regulador.
7. Documentar diferencias entre cálculo previo y medición final.

## Recursos Adicionales
- Horowitz, P., & Hill, W. *The Art of Electronics*. Cambridge University Press.
- Rashid, M. H. *Power Electronics: Circuits, Devices, and Applications*. Pearson.
- Texas Instruments. Guías de reguladores lineales: https://www.ti.com/power-management/linear-regulators/overview.html
- STMicroelectronics. Notas de aplicación de rectificación y filtrado: https://www.st.com/
- Hojas de datos sugeridas: 7805, LM317, puente rectificador de 2 A, capacitor electrolítico de filtro de baja ESR.
