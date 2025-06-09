# Procedimiento de documentación

Este documento define el método de trabajo para desarrollar progresivamente la documentacion en Cuants, basada en estadística aplicada al trading cuantitativo. El objetivo es construir un corpus educativo modular, claro, riguroso y directamente aplicable.

***

## 1. Estructura principal

### 📚 Eje pedagógico (progresivo)

* Organizado por **niveles de complejidad** (básico, intermedio, avanzado)

* Cada módulo aborda un **concepto estadístico clave**, explicado con claridad

* En cada caso, se incluye una **aplicación concreta al trading cuantitativo**

***

## 2. Método de desarrollo

1. **Partir desde lo aprendido**

   * Se documenta inicialmente el conocimiento tal como fue aprendido en la licenciatura o la experiencia previa

   * Se permite incluir ejercicios clásicos o ejemplos no financieros

2. **Transformar hacia lo aplicado**

   * Se agregan secciones que contextualizan el concepto en trading

   * Se introducen series temporales, estrategias, métricas reales, etc.

3. **Estructurar cada módulo con plantilla fija**

   * Permite desarrollar de forma progresiva y mantener claridad para el lector

4. **Agregar conectores y enlaces**

   * Cada módulo debe vincularse con:

     * Módulos previos y posteriores

     * Posibles notebooks, visuales, ejemplos en código

5. **Iterar, no cerrar**

   * Cada entrada puede ampliarse, corregirse o reformularse a medida que Cuants evoluciona

   * Lo importante es tener un punto de partida claro y útil

***

## 3. Plantilla para cada módulo

```markdown
# [Título del módulo]

## ¿Qué es esto? (definición clara y concisa)
Explicación directa del concepto desde el punto de vista estadístico.

---

## ¿Cómo se calcula o se usa?
Fórmulas básicas (si aplica) y ejemplos sencillos.

---

## ¿Cómo se aplica al trading cuantitativo?
Ejemplos con series temporales reales o estrategias comunes.

---

## Ejemplo aplicado (opcional)
Caso práctico, visual o fragmento de código.

---


## Enlaces internos en Cuants
Módulos relacionados.
```
## Sistema de tags

Divididos por tipo de uso:

***

### **Tipo de contenido**

* `#concepto-base` → definición fundamental (media, varianza, probabilidad)

* `#herramienta-estadistica` → algo que se usa para análisis (sharpe, drawdown, test)

* `#modelo` → cuando aparezcan modelos probabilísticos, bayesianos, etc.

* `#visualizacion` → gráficos, histograms, curvas

***

### **Función dentro del trading cuantitativo**

* `#medida-de-rendimiento` → media, sharpe, retorno acumulado

* `#medida-de-riesgo` → desviación, drawdown, VaR

* `#validacion-de-estrategias` → p-values, tests, errores de backtesting

* `#simulacion` → Monte Carlo, bootstraps, generadores aleatorios

* `#optimizacion` → cuando lleguemos a mejorar estrategias

* `#decision-de-inversion` → cuando analices señales o reglas de trading

***

### **Tipo de distribución o probabilidad**

* `#distribucion-normal`

* `#distribucion-binomial`

* `#distribucion-uniforme`

* `#distribucion-t-student` (más adelante)

***

### **Nivel del contenido**

(opcional, si querés marcarlo internamente)

* `#nivel-basico`

* `#nivel-intermedio`

* `#nivel-avanzado`

