# Título de la Sesión: Campo eléctrico. Tipos de condensadores. Funcionamiento en AC y DC. Prueba con el multímetro. Circuitos en serie y paralelo. Aplicaciones prácticas

## Introducción
Los condensadores almacenan energía en forma de campo eléctrico y son imprescindibles en filtrado, desacoplo, temporización, arranque de motores, corrección de factor de potencia y procesamiento de señales. Comprender su comportamiento diferencial en corriente continua y alterna permite interpretar fenómenos de carga, descarga, desfase y respuesta frecuencial, todos fundamentales en el diseño eléctrico y electrónico.

## Objetivo de Aprendizaje
Calcular, comparar y verificar experimentalmente el comportamiento de condensadores en DC y AC, incluyendo su asociación serie-paralelo y su evaluación básica con multímetro.

## Desarrollo del Tema (Explicación de la tecnología)
Un condensador ideal está formado por dos conductores separados por un dieléctrico. Su capacitancia se define como:

$$
C = \frac{Q}{V}
$$

Para placas paralelas:

$$
C = \varepsilon \frac{A}{d}
$$

donde $\varepsilon=\varepsilon_r\varepsilon_0$ es la permitividad del dieléctrico, $A$ el área de placas y $d$ la separación.

La relación constitutiva temporal es:

$$
i(t) = C\frac{dv(t)}{dt}
$$

y, de forma equivalente,

$$
v(t) = \frac{1}{C}\int i(t)\,dt + v(0)
$$

Estas expresiones muestran que la tensión en un condensador no puede cambiar instantáneamente sin requerir corriente impulsiva infinita.

### Funcionamiento en DC
Si una fuente de tensión continua $V_s$ se conecta a un capacitor inicialmente descargado a través de una resistencia $R$, la carga responde según:

$$
v_C(t) = V_s\left(1-e^{-t/RC}\right)
$$

$$
i(t) = \frac{V_s}{R}e^{-t/RC}
$$

La constante de tiempo es:

$$
\tau = RC
$$

Aproximadamente en $5\tau$ el condensador alcanza más del $99\%$ de su valor final. En estado estacionario DC ideal, el condensador se comporta como circuito abierto.

### Funcionamiento en AC
Para una excitación senoidal de frecuencia angular $\omega$, la impedancia capacitiva es:

$$
Z_C = \frac{1}{j\omega C}
$$

Su magnitud es la reactancia capacitiva:

$$
X_C = \frac{1}{\omega C}
$$

La corriente adelanta a la tensión en $90^\circ$, propiedad esencial en redes de fase, filtros y compensación reactiva. A mayor frecuencia, menor oposición al paso de la corriente alterna.

### Tipos de condensadores
- **Cerámicos:** baja ESR, adecuados para alta frecuencia y desacoplo.
- **Electrolíticos:** alta capacitancia volumétrica; polarizados; útiles en filtrado de fuentes.
- **Película plástica:** buena estabilidad y bajas pérdidas.
- **Tantalio:** alta densidad capacitiva y mejores tolerancias, pero sensibles a sobretensiones.
- **Supercapacitores:** muy alta capacitancia para almacenamiento de energía de corto plazo.

### Asociación serie y paralelo
En paralelo:

$$
C_{eq} = \sum_{k=1}^{n} C_k
$$

En serie:

$$
\frac{1}{C_{eq}} = \sum_{k=1}^{n}\frac{1}{C_k}
$$

En serie, la carga es común y el voltaje se reparte; en paralelo, el voltaje es común y la carga total se suma.

### Prueba con multímetro
Con un multímetro digital pueden verificarse:
- continuidad anómala por cortocircuito interno,
- valor de capacitancia si el equipo dispone de escala correspondiente,
- polaridad en condensadores electrolíticos,
- comportamiento de carga transitoria en modo ohmímetro, observando la variación temporal aparente de la resistencia.

El multímetro no sustituye a un medidor ESR ni a un puente LCR cuando se requiere diagnóstico profundo.

```mermaid
flowchart TD
    A[Fuente DC] --> B[Resistencia R]
    B --> C[Condensador C]
    C --> D[Tierra]
    A --> E[Observación de vc(t)]
    F[Fuente senoidal] --> G[Impedancia Zc = 1/jωC]
    G --> H[Desfase: i adelanta a v]
    H --> I[Filtros y acoplamiento]
```

## Preguntas Orientadoras
1. ¿Por qué un condensador bloquea la corriente continua en estado estacionario, pero permite el paso de corriente alterna?
2. ¿Qué implicaciones prácticas tiene la ESR de un condensador en una fuente rectificada o un convertidor?
3. ¿Cómo cambia el comportamiento de un capacitor real al incrementar la frecuencia más allá de su rango de operación?
4. ¿Qué riesgos implica conectar un condensador electrolítico con polaridad invertida?
5. ¿Por qué una asociación en serie de condensadores requiere considerar balanceo de tensión en aplicaciones de alta tensión?

## Ejercicios Propuestos
1. Un capacitor de $100\,\mu\text{F}$ se carga desde $12\,\text{V}$ a través de una resistencia de $2.2\,\text{k}\Omega$. Calcule $\tau$, la corriente inicial y el voltaje del capacitor en $t=0.1\,\text{s}$.
2. Determine la reactancia de un capacitor de $470\,\text{nF}$ a $60\,\text{Hz}$, $1\,\text{kHz}$ y $100\,\text{kHz}$. Interprete la tendencia física.
3. Calcule la capacitancia equivalente de tres capacitores de $10\,\mu\text{F}$, $22\,\mu\text{F}$ y $47\,\mu\text{F}$ conectados: a) en paralelo, b) en serie.
4. En un circuito RC serie conectado a una fuente senoidal de $10\,\text{V}_{rms}$ y $1\,\text{kHz}$, con $R=1\,\text{k}\Omega$ y $C=100\,\text{nF}$, calcule la impedancia total, la corriente RMS y el ángulo de fase.
5. Un condensador de filtro alimenta una carga de $100\,\text{mA}$ en una fuente rectificada de onda completa a $120\,\text{Hz}$. Estime el rizado si $C=1000\,\mu\text{F}$ usando $\Delta V \approx I/(fC)$.

## Actividad en Clase (Hands-on)
**Práctica guiada: carga, descarga y verificación de condensadores**

1. Identificar visualmente condensadores cerámicos, electrolíticos y de película.
2. Medir capacitancia nominal con multímetro y comparar con el valor marcado.
3. Armar un circuito RC y registrar $v_C(t)$ durante la carga y descarga.
4. Estimar experimentalmente la constante de tiempo a partir del instante en que $v_C(t)=0.632V_s$.
5. Montar dos bancos de condensadores: serie y paralelo, y verificar $C_{eq}$.
6. Discutir por qué el modelo ideal difiere de la medición real debido a fugas, ESR y tolerancia.

## Recursos Adicionales
- Nilsson, J. W., & Riedel, S. A. *Electric Circuits*. Pearson.
- Sedra, A. S., & Smith, K. C. *Microelectronic Circuits*. Oxford University Press.
- Murata. Notas de aplicación sobre capacitores cerámicos: https://article.murata.com/
- KEMET / Yageo. Guías técnicas de selección de capacitores: https://www.yageo.com/en/Product/Capacitors
- Hojas de datos sugeridas para consulta crítica: capacitor electrolítico radial de $1000\,\mu\text{F}$, MLCC de $100\,\text{nF}$ X7R, capacitor de película de polipropileno para AC.
