# Intervalos de confianza

## Definición

Un **intervalo de confianza** es un rango de valores dentro del cual esperamos que se encuentre un **parámetro desconocido de la población** (como la media), con cierto nivel de confianza (por ejemplo, 95%).

En lugar de decir “la media es 0.015”, decimos: La media poblacional está entre 0.012 y 0.018 con un 95% de confianza.

***

## ¿Por qué usamos intervalos?

Porque cuando trabajamos con muestras, **no sabemos el valor exacto** del parámetro poblacional. Solo lo estimamos. El intervalo nos da una **margen de error razonable** en esa estimación.

Un intervalo de confianza no dice que el parámetro “tiene 95% de probabilidad de estar ahí” (eso sería enfoque bayesiano), sino que “si repitiéramos el experimento muchas veces, el 95% de los intervalos obtenidos contendrían el valor real”.

***

## ¿Cómo se calcula?

Para un intervalo de confianza para la media con varianza conocida (caso clásico):

$IC = \hat x ± z_{α/2}​ * \frac {\sigma}{\sqrt n}$

* $\hat{x}$: media muestral

* $\sigma$: desviación estándar poblacional

* $n$: tamaño de la muestra

* $z_{\alpha/2}$: valor crítico de la normal estándar según el nivel de confianza

En la práctica, como no conocemos $\sigma$, usamos la **desviación muestral** y distribuimos con t de Student.

## Aplicación al trading cuantitativo

Los intervalos de confianza nos permiten:

* Estimar la **rentabilidad real esperada** de una estrategia, en vez de confiar en una única media muestral.

* Comparar estrategias: si los intervalos no se superponen, hay evidencia de diferencia.

* Evaluar la **robustez** de resultados en backtests.

* Aplicar tests de hipótesis: son equivalentes a ciertos tests estadísticos.

***

## Ejemplo aplicado

Supongamos que una estrategia arroja un retorno medio diario de 0.1% con desviación de 1.5% y $n = 50$ días.

```python
import numpy as np
from scipy import stats

media = 0.001
std = 0.015
n = 50
confianza = 0.95

# Usamos t-Student porque sigma es estimada
t_critico = stats.t.ppf((1 + confianza) / 2, df=n-1)
margen_error = t_critico * std / np.sqrt(n)

ic_inf = media - margen_error
ic_sup = media + margen_error
print(f"Intervalo de confianza del 95%: ({ic_inf:.4f}, {ic_sup:.4f})")

```

