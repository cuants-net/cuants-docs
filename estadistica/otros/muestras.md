# Muestras y poblaciones

**La diferencia entre lo que vemos y lo que realmente queremos conocer**

***

## ¿Qué es una población en estadística?

Una **población** es el conjunto completo de elementos sobre el que queremos sacar conclusiones.

En trading, puede ser:

* Todos los retornos posibles de una estrategia

* Todas las operaciones que podrías hacer con una regla

* Todos los días de cotización de un activo a lo largo de su existencia

La población es lo que nos gustaría conocer. Pero casi nunca la tenemos completa.

***

## ¿Qué es una muestra?

Una **muestra** es un subconjunto finito de la población, del cual extraemos información.

En trading, ejemplos de muestra pueden ser:

* Los últimos 100 trades

* Los retornos de 2022-2023

* Una simulación de Monte Carlo con 10.000 escenarios

La muestra debe ser **representativa** para que podamos generalizar conclusiones.

***

## ¿Por qué esta diferencia es clave en trading cuantitativo?

Porque todo lo que calculamos —media, desviación, Sharpe, win rate, drawdown— se hace sobre **muestras**, pero lo usamos para **decidir sobre el futuro** (la población).

El riesgo real está en la población. Nosotros solo tenemos una muestra limitada.

***

## Tipos de muestreo comunes

* **Aleatorio simple**: todos los elementos tienen la misma probabilidad de ser elegidos

* **Muestreo temporal**: usamos un período de tiempo fijo (muy común en trading)

* **Bootstrap**: remuestreo con reemplazo, para simular muchas muestras de una sola

***

## Código ilustrativo

```python
import numpy as np

# Supongamos que esta es la población real (pero la desconocemos)
poblacion = np.random.normal(0.001, 0.02, size=100000)

# Muestra aleatoria
muestra = np.random.choice(poblacion, size=100, replace=False)

print(f"Media poblacional (oculta): {np.mean(poblacion):.4%}")
print(f"Media muestral: {np.mean(muestra):.4%}")
```

***

## Conclusión

* Nunca tenemos todos los datos posibles → siempre trabajamos con **incertidumbre**

* La diferencia entre muestra y población es **la raíz de toda inferencia**

* Por eso necesitamos **estimadores, intervalos, tests, y validación cruzada**
