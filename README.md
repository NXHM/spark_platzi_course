# Curso de Platzi de Apache Spark

*Nota sacada en la evaluación: 20*

## ¿Qué es Apache Spark?

Apache Spark es un motor de análisis unificado para el procesamiento de datos a gran escala. Ofrece una interfaz para la programación en clústeres completos con paralelismo de datos implícito y tolerancia a fallos.

### Funcionamiento Interno

Apache Spark utiliza una arquitectura maestro-esclavo con un coordinador central (driver) y múltiples trabajadores (executors). El funcionamiento se basa en:

1. **DAG (Directed Acyclic Graph)**
   - Representación de las operaciones como un grafo dirigido
   - Optimización de las transformaciones antes de la ejecución
   - Minimización de shuffling y operaciones costosas

2. **RDD (Resilient Distributed Dataset)**
   - Abstracción fundamental de datos inmutable y distribuida
   - Tolerancia a fallos mediante linaje
   - Evaluación lazy para optimización

3. **Memory Management**
   - Almacenamiento en memoria para operaciones iterativas
   - Cache y persist para reutilización de datos
   - Spill to disk cuando sea necesario: Escribe en el disco duro si es que la memoria RAM no es suficiente


![image](https://github.com/user-attachments/assets/9dba8126-d80d-487f-88d9-f3ef2c8dcba0)

### Estructuras de Datos en Apache Spark

1. **RDD (Resilient Distributed Dataset)**
   - Colección distribuida de elementos
   - Operaciones básicas map/reduce
   - Ideal para datos no estructurados
   
2. **DataFrame**
   - Datos organizados en columnas nombradas
   - API más intuitiva y optimizada
   - Integración con Spark SQL
   - Mejor rendimiento que RDD

3. **Dataset**
   - Extensión tipada de DataFrame
   - Verificación de tipos en tiempo de compilación
   - Mejor para aplicaciones que necesitan type-safety

4. **Spark SQL**
   - Motor de procesamiento estructurado
   - Optimizador de consultas Catalyst
   - Compatible con fuentes de datos externas

## Alternativas a Apache Spark detalladas

### Hadoop MapReduce - HDFS
- **Descripción**: Framework de procesamiento distribuido para conjuntos de datos masivos.
- **Características principales**:
  - Procesamiento en disco
  - Alta tolerancia a fallos
  - Escalabilidad lineal
  - Procesamiento batch nativo
- **Casos de uso**:
  - ETL tradicional
  - Data warehousing
  - Análisis de logs
- **Empresas que lo usan**: Facebook, Yahoo, LinkedIn

### Apache Flink
- **Descripción**: Motor de procesamiento de datos distribuido unificado para batch y streaming.
- **Características principales**: 
  - Procesamiento de streams nativo
  - Bajo nivel de latencia
  - Garantías exactly-once
  - API para streams y datasets
- **Casos de uso**:
  - Procesamiento en tiempo real
  - Análisis de fraude
  - Análisis de series temporales
- **Empresas que lo usan**: Alibaba, ING Bank, King

### Apache Storm
- **Descripción**: Sistema distribuido de procesamiento en tiempo real.
- **Características principales**:
  - Procesamiento en tiempo real puro
  - Garantías at-least-once
  - Topologías de procesamiento
  - Integración con múltiples lenguajes
- **Casos de uso**:
  - Analítica en tiempo real
  - Procesamiento ETL continuo
  - Monitorización operacional
- **Empresas que lo usan**: Twitter, Spotify, WebMD

### Dask
- **Descripción**: Framework de computación paralela nativo de Python.
- **Características principales**:
  - Integración nativa con NumPy, Pandas
  - Escalado dinámico
  - Planificación de tareas distribuidas
  - API familiar para usuarios de Python
- **Casos de uso**:
  - Análisis científico
  - Machine Learning distribuido
  - Procesamiento de datos en Python
- **Empresas que lo usan**: NASA, NVIDIA, Capital One

## Comparación Detallada

| Característica | Spark | MapReduce | Flink | Storm | Dask |
|---------------|-------|-----------|-------|-------|------|
| Velocidad | Alta (memoria) | Baja (disco) | Alta | Alta | Media |
| Latencia | Segundos | Minutos | Milisegundos | Milisegundos | Segundos |
| Facilidad de uso | Alta | Media | Media | Baja | Alta |
| Tolerancia a fallos | Alta | Alta | Alta | Media | Media |
| Ecosistema | Muy amplio | Muy amplio | Creciendo | Limitado | Python-centric |
| Madurez | Alta | Muy alta | Media | Alta | Media |

## Métricas de Evaluación

1. **Rendimiento**:
   - Spark: 100x más rápido que MapReduce en memoria
   - Flink: Similar a Spark, mejor en streaming
   - Storm: Optimizado para latencia ultra-baja
   - Dask: Variable según el caso de uso

2. **Escalabilidad**:
   - Spark: Miles de nodos
   - MapReduce: Miles de nodos
   - Flink: Cientos de nodos
   - Storm: Cientos de nodos
   - Dask: Decenas a cientos de nodos

3. **Costos operativos**:
   - Spark: Medio-Alto (memoria)
   - MapReduce: Medio (disco)
   - Flink: Medio-Alto
   - Storm: Medio
   - Dask: Bajo-Medio

## Justificación de la Elección

Se elige Apache Spark por su capacidad de procesar datos a gran escala de forma rápida mediante el procesamiento en memoria. Su amplia adopción en la industria y su ecosistema maduro lo hacen ideal para aplicaciones de análisis de datos, aprendizaje automático y procesamiento en tiempo real.

## Usos de Apache Spark

- **Análisis de Big Data**: Procesamiento y análisis de grandes volúmenes de datos.
- **Aprendizaje Automático**: Construcción y escalado de modelos con MLlib.
- **Procesamiento en Tiempo Real**: Análisis de flujos de datos con Spark Streaming.
- **Consultas Interactivas**: Exploración de datos de forma rápida e interactiva.

## Recursos:
- Introducción express a Apache Spark: https://youtu.be/IELMSD2kdmk?si=-9Xo0PjTDprSIyOY
- Curso de Apache Spark de Platzi
- https://ieeexplore-ieee-org.ezproxy.ulima.edu.pe/document/10718602
- https://elmundodelosdatos.com/dominando-apache-spark-ii-funcionamiento-interno-y-arquitectura/
- https://gaurav98095.medium.com/delving-deep-into-data-spill-in-apache-spark-88c90c578f5a

## Alternativas:
- https://docs.coiled.io/blog/tpch.html?utm_source=dask.org&utm_medium=homepage
- https://docs.coiled.io/blog/spark-vs-dask.html?utm_source=dask.org&utm_medium=homepage
- https://docs.coiled.io/blog/tpch.html
- https://docs.coiled.io/blog/dask-dataframe-is-fast.html
- https://flink.apache.org/what-is-flink/use-cases/

## Para datasets pequeños
- Pandas
- Polars

### Comparación Pandas vs Polars 
- https://medium.com/@nandeda.narayan/data-processing-at-scale-comparison-of-pandas-polars-and-dask-333ae65c0a45
- https://medium.com/@husein2709/pandas-2-0-vs-polars-pvp-d8aec54c3fc8
- https://medium.com/@larissa.herrmann/pandas-and-large-files-20fae52d94ff
