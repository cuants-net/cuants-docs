# Distribución normal

***

## ¿Qué es la distribución normal?

La **distribución normal**, también llamada **gaussiana**, describe fenómenos donde los valores se agrupan alrededor de un valor medio y las desviaciones extremas son menos frecuentes. Tiene forma de **campana simétrica**.

Se define por dos parámetros:

* μ: la media

* σ: la desviación estándar

 En palabras simples: la normal nos dice que la mayoría de los datos están cerca de la media, y pocos están muy lejos.

***

## ¿Por qué es tan importante?

* Es la base del **Teorema Central del Límite**, que justifica su uso en muchas estadísticas, incluso cuando los datos no son normales.

* Muchos modelos financieros **asumen normalidad** para poder calcular riesgos, hacer inferencias o generar simulaciones.

* Es intuitiva y fácil de visualizar, lo que la hace una excelente introducción a la estadística.

***

## Aplicación en trading cuantitativo

* Se usa para modelar **retornos diarios** (aunque con precaución: los retornos reales tienen colas más pesadas).

* Es la base de muchos **tests de hipótesis** (t-test, z-test, p-values).

* Aparece en **simulaciones de estrategias** y en técnicas como Monte Carlo.

* Se usa para estimar rangos de precios esperados: Con 95% de confianza, el precio estará dentro de ±1.96σ de la media

***

## Visualización en Python

```python
import numpy as np
import matplotlib.pyplot as plt
from scipy.stats import norm

# Simular retornos normalmente distribuidos
mu, sigma = 0.001, 0.02
retornos = np.random.normal(mu, sigma, 1000)

# Histograma
plt.hist(retornos, bins=50, density=True, alpha=0.6, label="Retornos simulados")

# Curva teórica
x = np.linspace(mu - 4*sigma, mu + 4*sigma, 100)
plt.plot(x, norm.pdf(x, mu, sigma), 'k', label="PDF normal")
plt.title("Distribución normal de retornos simulados")
plt.legend()
plt.show()
```

***

## Precauciones

* La distribución normal **subestima eventos extremos** (colas finas). En la práctica, los retornos financieros muestran:

  * **Asimetría** (skewness)

  * **Curtosis** (colas más pesadas)

* Muchos errores de backtesting provienen de asumir normalidad sin verificarla

***

La distribución normal no es perfecta, pero es el punto de partida desde el que todo se construye, o se corrige.
