# Distribución muestral y ley de los grandes números

## Definición clara

La **distribución muestral** describe cómo varía un estimador (como la media) cuando se toman múltiples muestras aleatorias de una población. Es la base para entender el error de estimación y la construcción de intervalos de confianza.

La **Ley de los grandes números** afirma que, a medida que aumenta el tamaño de la muestra, la media muestral se aproxima a la media poblacional. Esto justifica el uso de estadísticas muestrales como estimaciones consistentes.

### Aplicación al trading cuantitativo

Al analizar resultados de estrategias, los retornos promedio que observamos están basados en una muestra (por ejemplo, 300 operaciones). Comprender cómo varían esos promedios entre muestras ayuda a evaluar si una estrategia es realmente robusta o si fue suerte.

En Cuants, se usa esta idea para enseñar que **una buena performance en backtest no garantiza que el estimador se mantenga igual en la operativa real**.

#### Ejemplo aplicado (con código en Python)

```python
import numpy as np
import matplotlib.pyplot as plt

# Simulamos 1000 medias de muestras de tamaño 30
np.random.seed(42)
true_mean = 0.001
returns = np.random.normal(loc=true_mean, scale=0.02, size=(1000, 30))
sample_means = np.mean(returns, axis=1)

plt.hist(sample_means, bins=30, alpha=0.7, color='steelblue')
plt.axvline(true_mean, color='red', linestyle='--', label='Media real')
plt.title("Distribución muestral de la media de retornos")
plt.legend()
plt.show()
```

