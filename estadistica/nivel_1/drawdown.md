# Drawdown

**Cómo medir las caídas máximas de una estrategia de trading**

***

## ¿Qué es un drawdown?

El **drawdown** es una métrica que mide la **caída máxima desde un punto alto hasta un punto bajo** en una curva de capital (equity curve). En términos simples:

¿Cuánto tuviste que “aguantar” de pérdida antes de que la estrategia se recuperara?

El drawdown es fundamental para evaluar el **riesgo real percibido** por un trader o inversor. No mide la volatilidad diaria, sino las caídas sostenidas.

***

## Tipos de drawdown

* **Drawdown absoluto**: pérdida desde el punto más alto hasta el más bajo (en valor absoluto).

* **Drawdown porcentual (máximo)**: caída porcentual desde el pico hasta el valle.

* **Duración del drawdown**: cuántos períodos tardó en recuperarse desde el pico anterior.

***

## ¿Por qué importa en trading cuantitativo?

* Ayuda a **medir el riesgo psicológico**: un sistema con drawdown severo es difícil de sostener, incluso si es rentable.

* Permite **comparar estrategias con el mismo retorno**: una puede tener menor drawdown y ser preferible.

* Es crítico en **gestión de capital** y cálculo de tamaño de posición.

* Complementa al Sharpe ratio: una estrategia con alto Sharpe pero drawdowns profundos puede ser inviable.

***

## Ejemplo visual (conceptual)

Supongamos una curva de capital:

* Sube de 100 a 120

* Baja de 120 a 90 → **Drawdown del 25%**

* Luego sube hasta 130 → **se recupera**

***

## Código en Python

```python
import numpy as np
import pandas as pd

# Simulación de una curva de capital
equity = pd.Series([100, 105, 110, 108, 115, 107, 120, 95, 100, 130])

# Calcular máximos acumulados
max_acumulado = equity.cummax()

# Calcular drawdown
drawdown = (equity - max_acumulado) / max_acumulado

drawdown_max = drawdown.min()
print(f"Máximo drawdown: {drawdown_max:.2%}")

```

***

## ¿Qué representa un alto drawdown?

* Posible **fragilidad estructural** de la estrategia

* Necesidad de más capital o menor apalancamiento

* Posible **abandono emocional** por parte del operador (aunque la estrategia sea buena)

Una estrategia no se abandona por falta de ganancias, sino por un drawdown que no se puede soportar.
