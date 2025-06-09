# Expectancy y Payoff Ratio: evaluar la estructura de una estrategia

## Definición clara

La **expectancy** de una estrategia mide el retorno promedio que se espera por operación, considerando tanto ganancias como pérdidas y su frecuencia. Se calcula como:

$Expectancy=(Pg​ * G)−(Pp​ * L)$

donde:

* Pg​: probabilidad de ganar

* G: ganancia promedio por trade ganador

* Pp​: probabilidad de perder

* L: pérdida promedio por trade perdedor

El **payoff ratio** es la relación entre ganancia y pérdida promedio:

$Payoff Ratio=\frac {G}{L}​$

Ambas métricas ayudan a **entender cómo funciona internamente una estrategia**, más allá de su curva de equity.

## Aplicación al trading cuantitativo

Estas métricas permiten responder preguntas como:

* ¿Mi estrategia necesita muchas operaciones ganadoras para ser rentable?

* ¿Puedo ganar con una tasa de acierto baja si mi payoff es alto?

* ¿Cuál es la estructura interna que sostiene mi rentabilidad?

En Cuants usamos expectancy para mostrar que **una estrategia puede ser consistente aun con bajo win rate**, si las ganancias compensan las pérdidas. O viceversa.

## Ejemplo aplicado (con código en Python)

```python
# Datos simulados de una estrategia
ganancias = [120, 100, 80, 150, 90]
perdidas = [-50, -40, -60, -45, -55, -50]

P_ganar = len(ganancias) / (len(ganancias) + len(perdidas))
P_perder = 1 - P_ganar
G = sum(ganancias) / len(ganancias)
L = abs(sum(perdidas) / len(perdidas))

expectancy = (P_ganar * G) - (P_perder * L)
payoff_ratio = G / L

print(f"Expectancy por operación: {expectancy:.2f}")
print(f"Payoff Ratio: {payoff_ratio:.2f}")

```


