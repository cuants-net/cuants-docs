### Calmar Ratio: rendimiento ajustado por drawdown máximo

### **Definición clara**

El **Calmar Ratio** mide el rendimiento de una estrategia en relación a su peor caída histórica (drawdown máximo). Se define como:

$Calmar Ratio = \frac {R_a}{Max Drawdown}​​$

donde:

* Ra​: retorno anualizado de la estrategia

* Max Drawdown: caída porcentual más profunda desde un pico hasta un valle

### **Aplicación al trading cuantitativo**

A diferencia de Sharpe o Sortino, el Calmar Ratio no se enfoca en la varianza diaria, sino en la **resistencia del sistema en su peor momento**. Es crucial en sistemas que buscan estabilidad a largo plazo, especialmente cuando se gestiona dinero de terceros o se opera con apalancamiento.

Se promueve el uso del Calmar Ratio para entender la relación entre retorno y dolor soportado. Dos estrategias pueden tener el mismo retorno anual, pero si una sufre drawdowns del 40% y otra del 10%, el Calmar nos revela claramente cuál es más robusta.

### **Ejemplo aplicado (con código en Python)**

```python
import numpy as np

def calmar_ratio(cumulative_returns):
    high_water_mark = np.maximum.accumulate(cumulative_returns)
    drawdowns = 1 - cumulative_returns / high_water_mark
    max_drawdown = np.max(drawdowns)
    total_return = cumulative_returns[-1] / cumulative_returns[0] - 1
    annual_return = total_return  # Suponemos ya anualizado o período de 1 año
    return annual_return / max_drawdown if max_drawdown > 0 else np.nan

# Simulación de curva de equity (creciente con drawdowns)
equity = np.array([100, 120, 90, 130, 125, 140])
ratio = calmar_ratio(equity)
print(f"Calmar Ratio: {ratio:.2f}")
```

