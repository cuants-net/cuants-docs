# Visualización de tests y regiones de decisión

## Definición clara

Un **test estadístico** compara un valor observado con una distribución bajo la hipótesis nula para decidir si se acepta o se rechaza dicha hipótesis. Esta decisión puede visualizarse con:

* La **distribución bajo H₀**

* La **región crítica** (donde se rechaza H₀)

* El **valor observado** del estadístico

* El **p-valor**, como área bajo la curva desde el estadístico hacia la cola

Estas visualizaciones ayudan a entender el proceso de inferencia como una **decisión basada en probabilidades**, no como un veredicto definitivo.

## Aplicación al trading cuantitativo

En Cuants, promovemos el uso de visualizaciones para evaluar decisiones de validación de estrategias. Ver gráficamente:

* Dónde cae el estadístico de una estrategia

* Qué tanto se aleja de lo esperado bajo azar (H₀)

* Qué significa un p-valor "pequeño"

Esto reduce errores de interpretación comunes y facilita la explicación de resultados a otros (o a uno mismo).

## Ejemplo aplicado (con código en Python)

Visualizamos el resultado de un test z unilateral (media > 0) para una estrategia de trading.

```python
import numpy as np
import matplotlib.pyplot as plt
from scipy.stats import norm

mu_0 = 0
sigma = 0.01
n = 30
x_bar = 0.002  # media observada
alpha = 0.05

# Distribución bajo H0
se = sigma / np.sqrt(n)
x = np.linspace(-0.01, 0.01, 1000)
pdf = norm.pdf(x, mu_0, se)

# Valor crítico y p-valor
z_obs = (x_bar - mu_0) / se
p_valor = 1 - norm.cdf(z_obs)

plt.plot(x, pdf, label='H0', color='black')
plt.fill_between(x, 0, pdf, where=(x > x_bar), color='red', alpha=0.3, label=f'p-valor = {p_valor:.3f}')
plt.axvline(x_bar, color='blue', linestyle='--', label='Estadístico observado')
plt.title("Test de hipótesis: visualización del p-valor")
plt.legend()
plt.show()
```

