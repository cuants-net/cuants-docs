# Profit Factor, Win Rate y Hit Rate: métricas operativas básicas

## Definición clara

Estas tres métricas describen la **estructura estadística de los resultados operativos** de una estrategia:

### Profit Factor (PF)

Relación entre la suma total de ganancias y la suma total de pérdidas (en valor absoluto):

$Profit Factor=\frac{∑ganancias}{∑perdidas}$

Un PF a de ble; PF < 1 indica que las pérdidas superan a las ganancias.

### Win Rate (tasa de aciertos)

Proporción$ de operaciones ganadoras respecto al total:

$Win Rate = \frac{nº de trades ganadores}{nº total de trades}$ ​


### Hit Rate (sinónimo de Win Rate)

A veces se usa como sinónimo, aunque en algunos contextos se reserva “Hit Rate” para **detección correcta de señales** (ej. en modelos de clasificación). En trading discrecional o sistemático suelen ser equivalentes.

## Aplicación al trading cuantitativo

Estas métricas son muy utilizadas por traders para evaluar rápidamente una estrategia, pero **malinterpretarlas es frecuente**:

* Una estrategia puede tener **Win Rate alto pero ser perdedora** si el payoff es bajo (muchas ganancias chicas, una pérdida grande).

* Un Profit Factor de 1.5 no significa que la estrategia es buena: depende de la consistencia, número de operaciones y contexto.

En Cuants, estas métricas se enseñan **como punto de partida**, no como criterio único. Sirven para explorar la forma del sistema, no para decidir sin validación.

## Ejemplo aplicado (con código en Python)

```python
ganancias = [120, 100, 80, 150, 90]
perdidas = [-50, -40, -60, -45, -55, -50]

trades = ganancias + perdidas
num_ganadores = len(ganancias)
num_total = len(trades)

# Cálculos
profit_factor = sum(ganancias) / abs(sum(perdidas))
win_rate = num_ganadores / num_total

print(f"Profit Factor: {profit_factor:.2f}")
print(f"Win Rate: {win_rate:.2%}")
```
