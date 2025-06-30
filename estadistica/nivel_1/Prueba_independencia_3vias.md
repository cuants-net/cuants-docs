# Prueba de Chi-Cuadrado a 3 vías (CMH)

## Ejemplo aplicado: ¿influye el tipo de señal en el resultado, según el horario?

Un trader quiere evaluar si el **tipo de señal intradía** influye en el **resultado de la operación** (ganancia o pérdida). Pero sospecha que este efecto **puede depender del horario del día** en que se toma la posición (mañana o tarde).

### Variables:

* **Resultado** (Variable dependiente): Ganancia (G) o Pérdida (P).
* **Tipo de señal** (Variable explicativa): Señal A o Señal B.
* **Horario** (Variable de estratificación): Mañana (H1) o Tarde (H2).

El trader registra los resultados de 200 operaciones divididas equitativamente entre mañana y tarde:

---

## Paso 1. Tabla marginal (global)

| Señal     | Ganancia | Pérdida | Total |
| --------- | -------- | ------- | ----- |
| A         | 50       | 30      | 80    |
| B         | 40       | 80      | 120   |
| **Total** | 90       | 110     | 200   |

**Test de chi-cuadrado de Pearson** sobre esta tabla da:

* χ² = 14.1
* p-valor < 0.001 → se rechaza H₀

Esto sugiere que hay una relación entre el tipo de señal y el resultado. **Pero ¿será real o está influida por el horario?**

---

## Paso 2. Análisis estratificado por horario

### Horario: Mañana (H1)

| Señal | Ganancia | Pérdida |
| ----- | -------- | ------- |
| A     | 30       | 10      |
| B     | 20       | 40      |

### Horario: Tarde (H2)

| Señal | Ganancia | Pérdida |
| ----- | -------- | ------- |
| A     | 20       | 20      |
| B     | 20       | 40      |

El trader aplica la **prueba de Cochran-Mantel-Haenszel (CMH)** para combinar los dos horarios y evaluar si la asociación se mantiene al controlar este factor.

**Resultados de la prueba CMH:**

* χ² CMH = 10.9
* p-valor = 0.0009 → significativa
* OR ajustado = 3.0 con IC95% = \[1.6 ; 5.6]

### Interpretación

* La asociación entre tipo de señal y resultado **sigue siendo significativa** al controlar el horario.
* El uso de la Señal A **triplica las chances de ganar** respecto a la Señal B, ajustando por horario.

---

## Paso 3. Comparación de OR por estrato

### Mañana (H1)

* OR = (30*40)/(10*20) = 6.0 → fuerte asociación

### Tarde (H2)

* OR = (20*40)/(20*20) = 2.0 → moderada asociación

Ambos estratos muestran que la Señal A es mejor, pero el **efecto es más fuerte por la mañana**. Esto valida el uso de la CMH, porque **los OR tienen la misma dirección**, aunque con diferente magnitud.

---

## Conclusión

Este ejemplo muestra cómo una relación aparente entre una regla de trading y su rendimiento puede ser **mejor comprendida al considerar un tercer factor**, como el horario.

La prueba de CMH permite determinar si esa relación es **genuina o un efecto compuesto**. En este caso, el tipo de señal influye significativamente en el resultado, incluso al controlar por horario.

> En Cuants, siempre que detectes una asociación entre variables categóricas, preguntate: ¿podría haber una tercera variable que esté ocultando o exagerando esa relación?

# Prueba de Chi-Cuadrado a 3 vías (CMH)

## ¿Cuándo se usa?

Cuando tenés que analizar si hay **relación entre dos variables categóricas**, pero sospechás que una **tercera variable (estrato)** podría estar ocultando esa relación.

## Objetivo

Ver si la relación entre las dos variables **sigue existiendo cuando se controla o ajusta por la tercera**.

**Controlar** significa **mantener fija** o **ajustar estadísticamente** esa variable para **evitar que distorsione las conclusiones**.

---

## Paso 1. Tabla marginal (global)

### ¿Qué se hace?

* Se combinan todos los datos **ignorando la variable de control** (el estrato).
* Se arma una única **tabla de contingencia 2×2** con las dos variables principales.
* Se aplica el **test de chi-cuadrado de Pearson** para evaluar si hay evidencia de asociación global.

### ¿Para qué sirve?

* Para obtener una **visión preliminar** de la asociación entre las variables.

### Precaución importante

* Esta prueba **no considera el contexto**. Puede mostrar una asociación que **no es real** o que **cambia de dirección** al analizar por separado.
* Esto puede llevar a errores como la **Paradoja de Simpson**.

### Análisis realizados

* **Test de chi-cuadrado de Pearson**.
* (Opcional) **Odds Ratio marginal**: puede calcularse, pero **no se recomienda** si los estratos son heterogéneos.

---

## Paso 2. Prueba de Cochran-Mantel-Haenszel (CMH)

### ¿Qué se hace?

* Se aplica la prueba **CMH**, que combina la información de **varias tablas 2×2** (una por cada estrato).
* Se calcula un **odds ratio ajustado**, que resume la asociación entre las variables principales **ajustada por la variable de control**.
* Se realiza un **test de hipótesis** para evaluar si esa asociación persiste al controlar el estrato.

### ¿Cuál es el objetivo?

* Determinar si la asociación entre las variables principales **es genuina** o era una ilusoria por efecto del estrato.

### Hipótesis

* **H₀ (nula):** No hay asociación entre las variables principales **una vez controlado el estrato** (OR ajustado ≈ 1).
* **H₁ (alternativa):** Hay una **asociación real** que persiste incluso después de controlar por el estrato.

### Requisitos

* Todas las tablas deben ser **2×2**.
* Los OR por estrato deben ser **similares entre sí**. Si son muy distintos, NO usar CMH (mejor analizar por separado).

### Resultados esperados

* **Estadístico χ² CMH**.
* **p-valor** correspondiente.
* **OR ajustado** con **intervalo de confianza (IC)**.

### Interpretación

| Resultado                  | Interpretación                                                |
| -------------------------- | ------------------------------------------------------------- |
| OR ajustado ≈ 1            | No hay asociación real. Podría ser efecto del estrato.        |
| OR ajustado claramente ≠ 1 | Hay asociación genuina entre las variables principales.       |
| p-valor < α                | Se **rechaza H₀**. Hay evidencia significativa de asociación. |
| p-valor ≥ α                | No se rechaza H₀. No hay evidencia suficiente.                |

---

## Paso 3. Análisis por estrato

### ¿Qué se hace?

* Se generan **tablas separadas** por cada nivel del estrato.
* En cada tabla, se analiza la relación entre las variables.

### Objetivo

* Ver si la asociación detectada se **mantiene, se refuerza o desaparece** en los distintos estratos.
* Evaluar si hay **consistencia o heterogeneidad** entre los grupos.

### Análisis recomendados en cada tabla

* **Chi-cuadrado de Pearson**: para test de independencia por estrato.
* **Odds Ratio (OR)**: para medir fuerza y dirección de la asociación.
* **IC del OR**: si **no contiene 1**, la asociación es significativa.
* **Comparación entre OR de los estratos**: si son muy distintos, **no conviene aplicar CMH**.

---

## Cierre conceptual

La prueba de Cochran-Mantel-Haenszel es una herramienta clave para evitar conclusiones erróneas cuando hay una variable de estratificación relevante. Resume información de forma ajustada, pero requiere que los efectos por estrato sean coherentes. Siempre que se use, debe ir acompañada de una exploración por separado para entender la variabilidad interna.
