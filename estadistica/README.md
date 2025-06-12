# Estadística para Trading Cuantitativo

Este índice organiza los contenidos del proyecto Cuants en tres niveles de complejidad, combinando el rigor conceptual de la estadística clásica con su aplicación directa al análisis de series temporales financieras. Cada módulo está diseñado para ser práctico, contextualizado y progresivo.

[Procedimiento de documentación](procedimiento_documentacion.md)

## Nivel 1 · Fundamentos con enfoque aplicado

Conceptos básicos explicados con ejemplos de cotizaciones y retornos reales.

* **Variables aleatorias y distribuciones**

  * Retornos como variables aleatorias

  * Distribuciones empíricas de precios

* **Medidas de tendencia y dispersión**

  * Media, mediana, moda, desviación estándar

  * Aplicación a retornos diarios y semanales

* **Eventos, probabilidad condicional e independencia**

  * Probabilidad de ganancia

  * Dependencia entre señales

* **Distribuciones comunes en trading**

  * Normal, binomial, lognormal, uniforme

  * Cuándo se usan y qué implican

* **Visualización y exploración de datos financieros**

  * Histogramas, boxplots, curvas de equity

  * Librerías y herramientas básicas en Python

***

## Nivel 2 · Inferencia y validación de estrategias

Se introducen herramientas estadísticas para evaluar estrategias y tomar decisiones con datos históricos.

* **Inferencia estadística: estimadores y sesgo**

  * Estimación puntual

  * Sesgo de selección y de supervivencia en backtesting

* **Intervalos de confianza y tests de hipótesis**

  * ¿Cuánto confío en que el rendimiento observado no fue suerte?

  * Cálculo e interpretación de p-values en estrategias

* **Comparación de estrategias**

  * Tests para diferencias de medias y proporciones

  * Pruebas no paramétricas: Sign test, Wilcoxon

* **Correlación y regresión lineal simple**

  * ¿Una variable explica la otra?

  * Aplicaciones: regresión de activos, beta de un portafolio

* **Simulación con NumPy**

  * Monte Carlo de precios y retornos

  * Estimación de drawdowns extremos

***

## Nivel 3 · Métodos avanzados y pensamiento estadístico

### Ejes principales:

1. **Validación avanzada**

   * Walk-forward

   * Monte Carlo

   * Pruebas out-of-sample reales

   * Robustez paramétrica

   * Degradación temporal de sistemas

2. **Reflexiones de diseño cuantitativo**

   * ¿Qué hace que una estrategia sea estructuralmente sólida?

   * ¿Cómo detectar sobreajuste con pocos datos?

   * ¿Cómo pensar en términos de _distribución de resultados_, no de promedio?

3. **Gestión de complejidad y antifragilidad**

   * Cómo simplificar sin perder potencia

   * Sistemas adaptativos vs sistemas rígidos

   * Tolerancia a error: cómo diseñar con fallas previstas

4. **Interacción entre intuición y validación**

   * ¿Cómo traducir hipótesis de un trader discrecional a tests estadísticos?

   * ¿Cómo preservar la creatividad sin autoengaño?


