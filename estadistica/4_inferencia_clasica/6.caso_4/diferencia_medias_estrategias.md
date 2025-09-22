# Test de hipótesis para la diferencia de medias


## Introducción

Probaste dos estrategias de trading.  
Ambas parecen tener buen rendimiento… pero una te dio mejor resultado en la muestra.

La pregunta es:  
**¿Esa diferencia es real o fue solo suerte?**

La estadística tiene una herramienta para eso:  
el **test de hipótesis para diferencia de medias**.

## El problema concreto

Supongamos que:

- La estrategia A te dio en promedio un **0.18% diario**
- La estrategia B te dio un **0.27% diario**
- Las dos se probaron durante 50 días
- Querés saber si **realmente B es mejor**, o si esa diferencia podría haberse dado por azar

## ¿Cómo se evalúa?

Volvemos a la idea de los **intervalos de confianza**.

Podés construir un intervalo para la **diferencia de medias**,  
y ver si el **0 (ninguna diferencia)** queda dentro o fuera de ese intervalo.

- Si el intervalo **incluye el 0**, no tenés evidencia suficiente
- Si el intervalo **excluye el 0**, podés afirmar que hay diferencia real


## ¿Por qué usamos la diferencia?

Porque lo que importa no es si A y B son grandes o chicas,  
sino **cuánto se diferencian**.

Y si esa diferencia se sostiene **más allá del ruido del mercado**.


## Visualización

Imaginá que graficás los resultados medios de muchas repeticiones del experimento.  
Si **no hay diferencia real**, la diferencia de medias oscilará cerca de cero.

Pero si hay una ventaja real, esa diferencia se alejará del 0,  
y el intervalo te mostrará que esa diferencia es **estadísticamente significativa**.


## Ejemplo aplicado

Supongamos:

- $\bar{x}_A = 0.18\%$, $\bar{x}_B = 0.27\%$
- $s_A = 1.4$, $s_B = 1.6$
- $n_A = n_B = 50$

### Paso 1: Calcular la diferencia de medias
$$
\bar{d} = \bar{x}_B - \bar{x}_A = 0.27 - 0.18 = 0.09
$$
### Paso 2: Calcular el error típico

Si asumimos varianzas similares, el error típico (aproximado) es:

$$
SE = \sqrt{ \frac{s_A^2}{n_A} + \frac{s_B^2}{n_B} } = \sqrt{ \frac{1.96}{50} + \frac{2.56}{50} } ≈ \sqrt{0.0884} ≈ 0.297
$$

### Paso 3: Construir el intervalo de confianza (95%)

$$
IC = 0.09 \pm 2.00 \cdot 0.297 ≈ (–0.50,\ 0.68)
$$

### Interpretación

El intervalo **incluye el 0**, entonces **no podés afirmar que B es mejor**.


## ¿Y si el intervalo no incluyera el cero?

Entonces sí podrías decir:

- La diferencia no fue azarosa
- Hay una ventaja estadísticamente significativa


## ¿Qué factores afectan este análisis?

1. **Tamaño de la muestra**  
   Más datos → más precisión → intervalos más angostos

2. **Variabilidad de los resultados**  
   Más ruido → más incertidumbre

3. **Magnitud de la diferencia real**  
   Diferencias chicas necesitan más datos para detectarse



## Cierre

Comparar estrategias no es solo mirar cuál dio más. Es entender si la diferencia se sostiene más allá del ruido.

Y con un simple test de hipótesis para la diferencia de medias, podés evitar cambiar de rumbo por ilusiones estadísticas.

Porque en el trading, como en la vida, **no todo lo que parece mejor… realmente lo es.**
