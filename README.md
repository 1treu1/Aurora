# Aurora

Pipeline de ingeniería de datos de extremo a extremo que ingeste datos climáticos, usando una arquitectura de medallón (Bronze, Silver, Gold) para automatizar procesos.

## Documentación del Proyecto

### Descripción General
Aurora es un pipeline de datos diseñado para la ingesta, procesamiento y análisis de datos climáticos. Utiliza una arquitectura de medallón para garantizar la calidad y trazabilidad de los datos a través de las capas Bronze, Silver y Gold.

### Arquitectura

- **Bronze**: Ingesta de datos crudos desde fuentes externas (APIs, archivos CSV, etc.). Los datos se almacenan sin transformación.
- **Silver**: Limpieza, transformación y enriquecimiento de los datos. Se eliminan duplicados, se corrigen errores y se generan columnas adicionales.
- **Gold**: Datos listos para análisis y consumo por usuarios finales o aplicaciones. Incluye agregaciones, métricas y reportes.

### Componentes

- **Ingesta**: Scripts y notebooks para la extracción de datos climáticos.
- **Procesamiento**: Transformaciones usando PySpark/SQL para limpiar y enriquecer los datos.
- **Almacenamiento**: Uso de Delta Lake para gestionar versiones y calidad de datos.
- **Automatización**: Jobs programados en Databricks para ejecutar el pipeline de manera recurrente.

### Flujo de Trabajo

1. **Ingesta**: Los datos se extraen y almacenan en la capa Bronze.
2. **Transformación**: Los datos pasan a la capa Silver tras ser limpiados y transformados.
3. **Agregación**: Los datos se procesan y almacenan en la capa Gold para análisis avanzado.

### Requisitos

- Databricks Runtime
- PySpark
- Delta Lake

### Notebooks
- ../src/notebooks/brz_ingest_weather_api_raw
- ../src/notebooks/gold_business_metrics
- ../src/notebooks/silver_transfor_weather