# Medias muestrales

## El problema

Tenés los resultados de una estrategia en 50 días:  
Retorno medio diario: **0.24%**

La pregunta es:  
¿Qué tan cerca está ese 0.24% del retorno *real* de la estrategia?

Ese 0.24% se calculó sobre una muestra. Sabemos que **debería estar cerca** del valor real,  
pero no tenemos forma de saber **cuán cerca**.  
No conocemos la media verdadera de la estrategia (ni nunca la conoceremos).

Lo que sí tenemos es una **media muestral**, que usamos como estimador de la **media poblacional**.


## ¿Cómo se calcula la media muestral?
$$
\bar{x} = \frac{1}{n} \sum_{i=1}^{n} x_i
$$
Donde:
- $x_i$: cada observación (por ejemplo, retorno diario)
- $n$: cantidad de observaciones

Estamos **usando un promedio de la muestra para estimar la media poblacional ($\mu$)**:

- Si la muestra representa bien al mercado, $\bar{x}$ estará cerca de $\mu$
- Si la muestra es sesgada o ruidosa, $\bar{x}$ puede ser engañosa

## ¿Cómo se comportan las medias muestrales?

Si tomaras muchas muestras diferentes del mercado y calcularas la media de cada una,  
obtendrías muchos valores distintos —pero **se agruparían alrededor de la media real ($\mu$)**.  
Y seguirían **una distribución aproximadamente normal**.

$$
\bar{X} \sim N \left( \mu, \frac{\sigma}{\sqrt{n}} \right)
$$

Esto sucede **aunque los datos originales no sigan una distribución normal**.  
Es un resultado general conocido como el **Teorema Central del Límite**:  
Las medias muestrales tienden a distribuirse normalmente cuando el tamaño de muestra es suficientemente grande*.

## ¿Qué significa eso en la práctica?

- Si **aumentás el tamaño de la muestra**, las medias muestrales se concentran más cerca de la media real.
- Cuanto más grande sea $n$, **menor será el error típico** al estimar $\mu$.

## Ejemplo aplicado

Querés estimar el retorno medio diario de una estrategia.

- Muestra: 100 días  
- Media muestral: 0.21%  
- Desviación estándar estimada: 1.6%

Error típico:

$$
\text{Error típico} \approx \frac{s}{\sqrt{n}} = \frac{1.6}{\sqrt{100}} = 0.16\%
$$

Eso significa que tu estimación de 0.21% tiene, en promedio, un error de ±0.16%.  
No es certeza. Pero sí es **una medida de cuánta fe le podés tener a lo que viste.**

## ¿Y si no conozco la desviación de la población?

En general, **no conocemos $\sigma$**, la desviación estándar poblacional.

Entonces usamos la **desviación estándar muestral ($s$)** como aproximación.  
Y la fórmula del error típico pasa a ser:

$$
\text{Error típico} \approx \frac{s}{\sqrt{n}}
$$
Esto introduce un poco más de incertidumbre.  
Más adelante, cuando construyamos intervalos de confianza, esto nos va a llevar a usar la **distribución $t$ de Student** en lugar de la normal.  
Pero por ahora alcanza con entender que:
**El error disminuye con el tamaño de muestra, pero nunca desaparece.**

## Nota conceptual

- La media muestral es un **estimador insesgado** de la media poblacional: en promedio, no exagera ni subestima.
- A medida que aumentás el tamaño de la muestra, el error se reduce, pero sigue habiendo incertidumbre.
- La distribución de las medias muestrales **nos habilita a usar herramientas inferenciales** como intervalos y test, incluso en mercados ruidosos.
