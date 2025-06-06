# Estadística para Trading Cuantitativo

Este índice organiza los contenidos del proyecto Cuants en tres niveles de complejidad, combinando el rigor conceptual de la estadística clásica con su aplicación directa al análisis de series temporales financieras. Cada módulo está diseñado para ser práctico, contextualizado y progresivo.

[Procedimiento de documentación](Procedimiento_documentacion.md)

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

Herramientas para quienes quieren construir modelos más robustos y adaptativos.

* **Inferencia bayesiana**

  * Priors, likelihood, posterior

  * Aplicación: estimar probabilidad de que una estrategia funcione

* **Modelos jerárquicos y agrupaciones**

  * Múltiples activos o estrategias

  * Pooling y shrinkage en escenarios reales

* **Distribuciones condicionales y conjuntas**

  * Modelado de dependencias

  * Copulas introductorias

* **Estadística robusta y manejo de outliers**

  * Medidas insensibles a eventos extremos

  * Aplicación: shock de liquidez o errores de ejecución

* **Bootstrap y remuestreo**

  * Validación de estrategias con pocos datos

  * Estimación de intervalos de confianza no paramétricos

***

