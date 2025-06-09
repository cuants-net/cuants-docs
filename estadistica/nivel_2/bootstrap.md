# Bootstrap y métodos de remuestreo

## Definición

El **Bootstrap** es un método estadístico que consiste en **generar nuevas muestras aleatorias** a partir de una muestra original, mediante remuestreo con reemplazo. Permite estimar la variabilidad de un estimador **sin depender de fórmulas teóricas**.

En lugar de suponer una distribución, el Bootstrap **la simula** directamente desde los datos.

***

## ¿Para qué sirve?

* Estimar la **distribución muestral** de una estadística (media, mediana, Sharpe ratio…)

* Calcular **intervalos de confianza** sin asumir normalidad

* Evaluar la **robustez** de resultados frente a variaciones aleatorias

* Validar estimadores en contextos donde las fórmulas teóricas no aplican bien

***

## ¿Cómo funciona?

1. Se toma una muestra original de tamaño $n$

2. Se generan muchas (por ejemplo, 1000) muestras **de tamaño $n$ con reemplazo**

3. Se calcula la estadística de interés en cada muestra

4. Se analiza la distribución de esas estadísticas (media, varianza, percentiles…)

***

## Aplicación al trading cuantitativo

* Estimar intervalos de confianza para **retornos, drawdowns, ratios**

* Validar si el **Sharpe ratio** observado es estable

* Verificar la estabilidad de una estrategia frente a pequeñas variaciones en los datos

* Evaluar la dispersión de resultados posibles con el mismo historial de precios

***

## Ejemplo en Python

```python
import numpy as np

# Supongamos retornos observados
retornos = np.array([0.01, 0.02, -0.005, 0.015, -0.01])
bootstrap_samples = 1000
medias = []

for _ in range(bootstrap_samples):
    muestra = np.random.choice(retornos, size=len(retornos), replace=True)
    medias.append(np.mean(muestra))

# Intervalo de confianza empírico (percentil 2.5 y 97.5)
ic_95 = np.percentile(medias, [2.5, 97.5])
print(f"Intervalo de confianza del 95%: {ic_95}")

```
## Ventajas

* No requiere supuestos fuertes (como normalidad)

* Fácil de implementar

* Se adapta bien a muestras pequeñas o problemas complejos

## Limitaciones

* Costoso computacionalmente para grandes muestras o estrategias complejas

* No siempre representa bien la estructura temporal de los datos (riesgo en series)
