# Big Data — Programación Distribuida con Apache Spark

> Trabajo práctico — **Programación Distribuida sobre Grandes Volúmenes de Datos**  
> Diplomatura en Ciencia de Datos, Aprendizaje Automático y sus Aplicaciones · Edición 2023  
> FaMAFyC, Universidad Nacional de Córdoba

---

## Descripción

Introducción al procesamiento distribuido de datos con **Apache Spark** usando el entorno **Apache Zeppelin**. El proyecto cubre desde los conceptos fundamentales de Spark (RDDs, DataFrames) hasta la construcción de pipelines de Machine Learning con **MLlib** y el análisis de grafos sociales a gran escala con **GraphFrames**.

---

## Estructura

```
06_big_data/
├── README.md
└── notebooks/                              ← notebooks de Apache Zeppelin (.zpln)
    ├── 01_introduccion_spark.zpln          ← conceptos fundamentales de Spark
    ├── 02_spark_core.zpln                  ← RDDs y operaciones core
    ├── 03_sql.zpln                         ← Spark SQL y consultas sobre DataFrames
    ├── 04_dataframes_tablas.zpln           ← DataFrames, esquemas y tablas temporales
    ├── 05_machine_learning.zpln            ← ML con MLlib
    ├── 06_ml_pipelines.zpln                ← Pipelines de ML con Transformers y Estimators
    └── 08_grafos_sociales.zpln             ← análisis de grafos sociales con GraphFrames
```

> **Nota:** Los notebooks `.zpln` son el formato nativo de Apache Zeppelin (JSON). Para visualizarlos correctamente se necesita un entorno Zeppelin o pueden convertirse a `.ipynb` con herramientas como `zeppelin-converter`.

---

## Notebooks

### `01_introduccion_spark.zpln` — Introducción a Apache Spark
- Arquitectura de Spark: Driver, Executors, Cluster Manager.
- Instalación y configuración del entorno local con Docker.
- Creación del primer `SparkContext` y `SparkSession`.
- Conceptos de lazy evaluation y DAG de ejecución.

### `02_spark_core.zpln` — Spark Core: RDDs
- Creación de **RDDs** (Resilient Distributed Datasets) desde colecciones y archivos.
- Transformaciones: `map`, `filter`, `flatMap`, `reduceByKey`, `groupByKey`.
- Acciones: `collect`, `count`, `take`, `reduce`.
- Diferencia entre transformaciones lazy y acciones que disparan ejecución.
- Persistencia y caché de RDDs.

### `03_sql.zpln` — Spark SQL
- Registro de DataFrames como tablas temporales (`createOrReplaceTempView`).
- Ejecución de consultas SQL sobre datos distribuidos con `spark.sql()`.
- Comparación entre API de DataFrame y SQL para las mismas operaciones.
- Joins, agregaciones y funciones de ventana en Spark SQL.

### `04_dataframes_tablas.zpln` — DataFrames y Tablas
- Creación de DataFrames desde CSV, JSON y Parquet.
- Definición explícita de esquemas con `StructType`.
- Operaciones sobre DataFrames: `select`, `filter`, `groupBy`, `agg`, `join`.
- Funciones built-in de Spark: `col`, `lit`, `when`, `udf`.
- Escritura de resultados en distintos formatos.

### `05_machine_learning.zpln` — Machine Learning con MLlib
- Introducción a la API de **MLlib**: Vectors, Features, Labels.
- Preparación de datos: `VectorAssembler`, `StringIndexer`.
- Entrenamiento de modelos de clasificación y regresión distribuidos.
- Evaluación de modelos con `BinaryClassificationEvaluator` y `MulticlassClassificationEvaluator`.

### `06_ml_pipelines.zpln` — ML Pipelines
- Concepto de Pipeline en MLlib: cadena de **Transformers** y **Estimators**.
- Construcción de un pipeline end-to-end: preprocesamiento → modelo → evaluación.
- **Cross-validation** y **train-validation split** distribuidos.
- `ParamGridBuilder` para búsqueda de hiperparámetros a escala.
- Guardado y carga de modelos entrenados.

### `08_grafos_sociales.zpln` — Análisis de Grandes Grafos Sociales
- Introducción a **GraphFrames**: representación de grafos con DataFrames de Spark.
- Construcción de grafos desde datasets de relaciones.
- Algoritmos de grafos:
  - **PageRank** para identificar nodos influyentes.
  - **Connected Components** para detección de comunidades.
  - **BFS** (Breadth-First Search) distribuido.
- Análisis de métricas del grafo: grado de entrada/salida, diámetro.

---

## Entorno de ejecución

```bash
# Levantar el entorno con Docker (según instrucciones de la cátedra)
cd diplodatos_bigdata
git pull
./docker/zeppelin.sh
```

- **Apache Spark:** 3.x
- **Apache Zeppelin:** 0.10+
- **Lenguaje:** PySpark (Python) y Scala (algunos ejemplos)
- **Docker:** requerido para el entorno local

---

## Conceptos clave abordados

| Concepto | Descripción |
|---|---|
| RDD | Estructura de datos distribuida base de Spark |
| DataFrame | Abstracción tabular distribuida con esquema |
| Spark SQL | Motor de consultas SQL sobre datos distribuidos |
| MLlib | Biblioteca de ML distribuido de Spark |
| Pipeline | Cadena de transformaciones y estimadores reproducible |
| GraphFrames | Procesamiento de grafos a escala con Spark |
| Lazy Evaluation | Las transformaciones se ejecutan solo cuando se llama una acción |

---

## Tecnologías

- **Apache Spark** 3.x con **PySpark**
- **Apache Zeppelin** (entorno de notebooks)
- **MLlib** (Machine Learning distribuido)
- **GraphFrames** (análisis de grafos)
- **Docker** (entorno de desarrollo)

---

## Contexto académico

Trabajo realizado para la materia **Programación Distribuida sobre Grandes Volúmenes de Datos** de la Diplomatura en Ciencia de Datos, Aprendizaje Automático y sus Aplicaciones (FaMAFyC, UNC, Edición 2023).
