# 🛒 Retail Data Pipeline & Strategic Analytics (Microsoft Fabric)

## 📋 Resumen del Proyecto
Este proyecto implementa una arquitectura **Lakehouse End-to-End** de alto rendimiento en **Microsoft Fabric**. Se transformó un dataset masivo de retail (~170MB) en un activo estratégico, aplicando estándares de ingeniería de software para garantizar la integridad, escalabilidad y observabilidad de los datos.

## 🛠️ Stack Tecnológico
* **Data Lake:** Azure OneLake (Arquitectura Medallion).
* **Ingeniería de Datos:** PySpark (Notebooks de Microsoft Fabric).
* **Almacenamiento:** Delta Tables con transaccionalidad ACID.
* **Visualización:** Power BI con conexión **Direct Lake** (Baja latencia).

## 🚀 Arquitectura Robusta (Nivel Producción)
A diferencia de un ETL convencional, este pipeline integra controles avanzados de ingeniería:

1.  **Data Quality Gate (Checkpoint):** Implementé un motor de validación post-transformación que audita la salud del dato en tiempo real. Se filtran automáticamente registros inconsistentes (como costos ≤ 0) antes de la persistencia, asegurando un **Índice de Salud del Dato** óptimo para el negocio.
2.  **Carga Incremental (Delta Merge):** Optimizamos el consumo de cómputo mediante lógica de **UPSERT**. El sistema identifica transacciones nuevas y actualiza registros existentes basándose en el `Transaction_ID`, eliminando la necesidad de re-procesar el dataset completo.
3.  **Capa Gold (Curated):** Los datos finales se alojan en el esquema `dbo` del Lakehouse, listos para un consumo seguro y gobernado vía SQL o Power BI.

## 📊 Dashboard de Negocios e Insights
El informe interactivo permite una toma de decisiones basada en evidencia:
* **Dependencia Promocional:** El 66% de las ventas dependen de descuentos (BOGO/Discount).
* **Performance Geográfica:** Análisis de ingresos por ciudad con alta granularidad.
* **Salud Operativa:** Monitoreo de la calidad de los datos procesados.

### Vista Previa del Dashboard
![Vista General del Dashboard](dashboard_general.png)

## 📥 Recursos del Proyecto
* **Notebook de Ingeniería:** [Ver código PySpark (.ipynb)](./01_ETL_Procesamiento_Ventas.ipynb)
* **Archivo Power BI:** [Descargar .pbix para revisión local](./Dashboard%20Ejecutivo%20de%20Ventas%20Retail%20Análisis%20Multidimensional.pbix)
* **Dataset:** Transacciones de Retail (Kaggle). *Nota: Por seguridad y volumen, el origen crudo se procesa directamente en OneLake.*

---
**Bastian Soto Morales** *Ingeniero Civil en Informática y Telecomunicaciones | Universidad Finis Terrae*
