# Retorno simple vs Retorno logarítmico

En trading cuantitativo, un **retorno** es una forma de expresar el cambio relativo en el valor de un activo entre dos momentos.

## ¿Cómo se calculan?

Dado un precio inicial  $P_t$ y uno final $P_{t+1}$:

* **Retorno simple:** mide el cambio porcentual directo entre precios
  $$R_t = \frac{P_{t+1}}{P_t} = \frac{P_{t+1}}{P_t} - 1$$
* **Retorno logarítmico:** transforma ese cambio en escala logarítmica, lo que permite sumar retornos consecutivos y facilita análisis estadísticos.
$$r_t = ln(\frac{P_{t+1}}{P_t})$$
Se usan los retornos logarítimicos porque tiene propiedades utiles:

* Es **aditivo en el tiempo** (sumar retornos logarítmicos equivale a multiplicar precios)

* Facilita cálculos cuando trabajamos con modelos continuos

Ambos retornos son casi iguales si los cambios son pequeños, pero difieren cuando hay grandes movimientos.

***

## ¿Cómo se aplica al trading cuantitativo?

Los **retornos simples** son más intuitivos: 2% de ganancia significa lo que parece.

Los **log-returns** se prefieren para análisis estadístico:
* Se pueden sumar fácilmente en el tiempo
* Se comportan mejor en modelos de probabilidad y series temporales
 
En backtesting y evaluación de estrategias:
* Los log-returns son ideales para calcular retornos acumulados:
* Si necesitás volver al precio final:

***

## Ejemplo numérico

| Día	| Precio	| Retorno simple (%)	| Retorno log (%) |
|---------|------------|------------------------------|----|
|1	| 100	| –	| –|
|2	|105	|5.00%	|4.88% |
|3	|103	|-1.90%	|-1.94%

Ambos tipos de retorno indican lo mismo: subió, luego bajó.

Pero si sumamos los retornos simples:
5%+(−1.9%)=3.1%

Mientras que los logarítmicos suman:
4.88%+(−1.94%)=2.94%

Y esto se traduce en:
ln⁡(103/100)=ln⁡(1.03)≈2.94%

Los retornos logarítmicos se ajustan mejor al cambio acumulado real.

## ¿Cuál usamos en trading cuantitativo?

* **Retorno simple**:

  * Bueno para interpretación humana

  * Útil en estrategias de horizonte corto o ejecución realista

* **Retorno logarítmico**:

  * Mejor para análisis estadístico

  * Útil en modelos matemáticos, simulaciones, optimización

**Conclusión:** en Cuants usaremos retornos logarítmicos como estándar de cálculo, a menos que se indique lo contrario.


## Ejemplo aplicado (opcional)

```python
import numpy as np
import pandas as pd

precios = pd.Series([100, 101.5, 98, 99])
retorno_simple = precios.pct_change().dropna()
retorno_log = np.log(precios / precios.shift(1)).dropna()

print("Retornos simples:")
print(retorno_simple)
print("\nRetornos logarítmicos:")
print(retorno_log)
```

***

## Enlaces internos

* [Media de retornos](#)

* [Varianza y desviación estándar](#)

* [Medidas de rendimiento acumulado](#)

* [Simulación de estrategias](#)

***
