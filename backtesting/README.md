# Backtesting y Validación de Estrategias

Esta sección explora las técnicas y principios para simular y validar estrategias sobre datos históricos de forma crítica, realista y reproducible. El objetivo no es solo medir performance, sino evitar sesgos, errores metodológicos y falsas ilusiones de robustez.

Los capítulos están organizados por nivel de complejidad, desde lo esencial hasta los enfoques más rigurosos y adaptativos.

---

## 📗 Capítulos Básicos

Conceptos iniciales para validar una estrategia simple.

- [¿Qué es un backtesting y cuales son los errores más comunes?](que_es_backtesting.md)
- [Estructura mínima de un motor de backtesting](estructura_motor_basico.md)
- [Sesgos comunes: look-ahead y survivorship](sesgos_basicos.md)
- [Simulación simple con pandas: lógica evento a evento](simulacion_basica_pandas.md)
- [Evaluación con métricas simples: retorno, drawdown, winrate](metricas_basicas_backtest.md)

---

## 📘 Capítulos Intermedios

Validaciones más sofisticadas, segmentación temporal y análisis robusto.

- [Segmentación temporal: holdout, walk-forward, rolling](segmentacion_temporal.md)
- [Frameworks de backtesting en Python: vectorbt, bt, backtrader](frameworks_backtesting.md)
- [Análisis de sensibilidad y robustez](analisis_robustez.md)
- [Métricas compuestas y ajustadas al riesgo](metricas_ajustadas_backtest.md)
- [Validación cruzada en series temporales](crossval_temporal.md)

---

## 📙 Capítulos Avanzados

Técnicas para validar estrategias complejas o adaptativas.

- [Purged K-Fold y embargos temporales](purged_kfold.md)
- [Backtesting de portafolios multi-activo](backtesting_portafolios.md)
- [Simulación con eventos asincrónicos y condiciones múltiples](backtesting_eventos_asincronicos.md)
- [Testeo de hipótesis operativas vs aleatoriedad](testeo_vs_random.md)
- [Backtest de estrategias con cambio de régimen](backtest_regimenes.md)

---
