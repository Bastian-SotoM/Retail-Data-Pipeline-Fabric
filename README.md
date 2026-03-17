# 🛒 Tejido de Canalización de Datos Retail (Microsoft Fabric End-to-End)

## 📋 Resumen del Proyecto
Este proyecto implementa una arquitectura **Lakehouse** completa en **Microsoft Fabric**. El objetivo es transformar un dataset masivo de transacciones de retail (~170MB) en un activo estratégico de información. El flujo abarca desde la ingesta en **OneLake** y el procesamiento distribuido con **PySpark**, hasta la entrega de un dashboard ejecutivo en **Power BI** utilizando la tecnología de vanguardia **Direct Lake**.

## 🛠️ Stack Tecnológico
* **Entorno:** Microsoft Fabric (SaaS).
* **Data Lake:** Azure OneLake (Arquitectura Medallion).
* **Ingeniería de Datos:** PySpark (Notebooks de Fabric).
* **Almacenamiento:** Delta Tables (ACID compliant).
* **Visualización:** Power BI (Direct Lake Mode).

## 🚀 Arquitectura de Datos (Medallion)
Para asegurar la integridad y escalabilidad, el pipeline se divide en tres capas lógicas:

1.  **Capa Bronze (Raw):** Almacenamiento del archivo CSV original en su estado nativo.
2.  **Capa Silver (Cleansed):** Limpieza de esquemas, normalización de tipos de datos, manejo de valores nulos y estandarización mediante **PySpark**.
3.  **Capa Gold (Curated):** Tablas Delta optimizadas y modelo semántico diseñado para el consumo analítico de alta performance.

## 📊 Dashboard Ejecutivo e Insights
El informe final proporciona una visión 360° de la operación:

* **Ventas por Ciudad:** Identificación de mercados líderes como Dallas y Boston (~$5.2M cada una).
* **Análisis de Promociones:** Hallazgo crítico donde el 66% de las ventas dependen de incentivos (BOGO/Descuento).
* **Mix de Formatos:** Comparativa de rentabilidad entre Pharmacy, Supermarket y Warehouse Club.
* **Filtros Dinámicos:** Segmentación por temporadas (`Season`) y años para análisis de estacionalidad.

### Vista Previa del Dashboard
![Vista General del Dashboard](dashboard_general.png)

## 📥 Recursos y Archivos
* **Código de Ingeniería:** [Ver Notebook de PySpark (01_ETL_Procesamiento_Ventas.ipynb)](./01_ETL_Procesamiento_Ventas.ipynb)
* **Archivo de Power BI:** [Descargar .pbix para visualización local](./Dashboard%20Ejecutivo%20de%20Ventas%20Retail%20Análisis%20Multidimensional.pbix)
* **Fuente de Datos:** Dataset de retail de 170MB (Kaggle). *Por razones de seguridad y límites de almacenamiento, el archivo crudo no se aloja en este repositorio.*

## 💡 Conclusión Técnica
La implementación de este pipeline reduce la latencia de datos al utilizar **Direct Lake**, permitiendo que los cambios en el Lakehouse se reflejen instantáneamente en Power BI sin procesos de refresco tradicionales. Esto demuestra una solución de **Big Data** moderna, eficiente y lista para producción en entornos corporativos.

---
**Desarrollado por:** **Bastian Soto Morales** *Ingeniero Civil en Informática y Telecomunicaciones* *Universidad Finis Terrae*
