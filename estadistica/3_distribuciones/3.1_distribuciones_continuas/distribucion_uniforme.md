# Distribución uniforme
Generar aleatoriedad pura para simulaciones y pruebas en trading.

*** 

## ¿Qué es la distribución uniforme?
Una variable aleatoria tiene distribución uniforme cuando todos los valores posibles en un intervalo tienen la misma probabilidad de ocurrir.

### Hay dos versiones:

🔹 Uniforme continua: cualquier número real entre dos límites
Ej: entre 0 y 1, cualquier número decimal tiene la misma probabilidad

🔹 Uniforme discreta: enteros equidistantes entre dos valores
Ej: lanzar un dado → valores 1 a 6, todos con 1/6 de probabilidad

### ¿Para qué sirve en trading cuantitativo?
La distribución uniforme no modela datos financieros reales, pero es esencial para tareas auxiliares:

#### 1. Simulación aleatoria sin sesgo
Generar decisiones “a ciegas” para comparar con estrategias reales

Ej: ¿una estrategia tiene mejor rendimiento que una elección aleatoria?

#### 2. Generación de ruido
Crear perturbaciones aleatorias para testear sensibilidad

Usar como fuente base en modelos más complejos

#### 3. Monte Carlo y bootstrapping
Es la base para seleccionar aleatoriamente muestras o caminos posibles

Genera resultados probabilísticos cuando no hay una distribución específica

Código en Python
```python
import numpy as np
import matplotlib.pyplot as plt

# 1000 valores uniformes entre 0 y 1
uniformes = np.random.uniform(0, 1, size=1000)

plt.hist(uniformes, bins=30, density=True, alpha=0.7)
plt.title("Distribución uniforme entre 0 y 1")
plt.xlabel("Valor")
plt.ylabel("Densidad")
plt.show()
```

### Visualización conceptual

Intervalo	Probabilidad
0.0–0.1	10%
0.1–0.2	10%
...	...
0.9–1.0	10%

Todos los subintervalos tienen la misma probabilidad → ninguna preferencia

#### Precauciones
* No usarla para modelar retornos o precios reales.
* Usarla como referencia neutral o herramienta auxiliar.

*** 

La distribución uniforme no representa lo que pasa en el mercado. Pero te ayuda a saber si lo que pasa es mejor que el puro azar.
