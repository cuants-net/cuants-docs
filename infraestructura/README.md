# Infraestructura para Trading Cuantitativo

Esta sección aborda los aspectos técnicos y operativos necesarios para implementar, ejecutar y monitorear estrategias de trading algorítmico en un entorno real o simulado.

Desde el manejo de datos hasta la ejecución en brokers, pasando por APIs, logging y automatización, cada capítulo está pensado para ser progresivo, claro y aplicable.

---

## 📗 Capítulos Básicos

Fundamentos para trabajar con datos y entornos reproducibles.

- [Fuentes de datos: tipos, licencias y calidad](fuentes_de_datos.md)
- [Carga y limpieza de datos financieros con pandas](carga_y_limpieza_datos.md)
- [Manejo de fechas y series temporales](manejo_fechas_series.md)
- [Descarga automática desde Yahoo Finance y yfinance](yfinance_basico.md)
- [Organización de notebooks y control de versiones con Git](estructura_y_git.md)

---

## 📘 Capítulos Intermedios

Integración con APIs, gestión de datos históricos y flujos automatizados.

- [Uso de APIs REST para datos financieros (ej: Polygon, Binance)](apis_financieras_basicas.md)
- [Construcción de pipelines de datos reproducibles](pipelines_reproducibles.md)
- [Almacenamiento eficiente con Parquet y SQLite](almacenamiento_datos.md)
- [Programación de tareas periódicas (cron, Prefect)](tareas_periodicas.md)
- [Logging y monitoreo básico de sistemas](logging_monitor.md)

---

## 📙 Capítulos Avanzados

Ejecución algorítmica real y diseño de infraestructura resiliente.

- [Conexión a brokers mediante API (Alpaca, IBKR, Binance)](api_brokers.md)
- [Ejecución en vivo vs paper trading: diferencias críticas](ejecucion_en_vivo.md)
- [Gestión de órdenes, slippage y reconexión](gestion_ordenes_slippage.md)
- [Despliegue de sistemas en servidores cloud (Docker, VPS)](despliegue_cloud.md)
- [Monitoreo de rendimiento y alertas operativas](monitoreo_estrategias.md)

---
