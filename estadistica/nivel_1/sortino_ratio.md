### Sortino Ratio: rendimiento penalizado solo por pérdidas

**Definición clara**

El **Sortino Ratio** es una variación del Sharpe Ratio que mide el rendimiento ajustado al riesgo, pero solo penaliza la volatilidad negativa (las pérdidas), en lugar de toda la desviación estándar. La lógica es simple: si una estrategia es volátil pero solo hacia arriba, no debería ser penalizada por eso.

Fórmula:

$Sortino Ratio = \frac {R_p - R_f}{\sigma_d}$​

donde:

* Rp​: rendimiento promedio del portafolio

* Rf​: rendimiento libre de riesgo

* σd​: desviación estándar de los retornos negativos (downside deviation)

**Aplicación al trading cuantitativo**

En estrategias que muestran picos de retorno o asimetría positiva, el Sharpe Ratio puede subestimar su calidad. El Sortino Ratio corrige esta distorsión y ofrece una visión más matizada del riesgo, enfocándose en las pérdidas reales. Es útil en etapas de evaluación fina de estrategias, o cuando el perfil de riesgo del trader prioriza evitar drawdowns.

Esta métrica ayuda a diferenciar estrategias con retorno similar pero distintos comportamientos ante la pérdida. Una estrategia con alto Sortino pero bajo Sharpe puede seguir siendo válida si el perfil de riesgo lo permite.

### **Ejemplo aplicado (con código en Python)**

```python
import numpy as np

def sortino_ratio(returns, risk_free_rate=0):
    downside_returns = returns[returns < risk_free_rate]
    downside_std = np.std(downside_returns) if len(downside_returns) > 0 else np.nan
    excess_return = np.mean(returns - risk_free_rate)
    return excess_return / downside_std if downside_std > 0 else np.nan

# Simulación
np.random.seed(42)
daily_returns = np.random.normal(loc=0.001, scale=0.02, size=252)
sortino = sortino_ratio(daily_returns)
print(f"Sortino Ratio diario: {sortino:.2f}")
print(f"Sortino Ratio anualizado: {sortino * np.sqrt(252):.2f}")
```

