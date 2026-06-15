# diplodatos-ciencia-de-datos-famaf-2023# Diplomatura en Ciencia de Datos, Aprendizaje Automático y sus Aplicaciones

> **DiploDatos 2023 · FaMAFyC, Universidad Nacional de Córdoba**  
> Proyectos y trabajos prácticos desarrollados a lo largo de la diplomatura.

---

## Sobre la diplomatura

La [Diplomatura en Ciencia de Datos, Aprendizaje Automático y sus Aplicaciones](https://diplodatos.famaf.unc.edu.ar/) (DiploDatos) es un programa de posgrado dictado por la Facultad de Matemática, Astronomía, Física y Computación (FaMAFyC) de la Universidad Nacional de Córdoba. Cada materia culmina con un proyecto integrador aplicado a datasets reales.

---

## Estructura del repositorio

```
diplodatos-2023/
│
├── 01_analisis_visualizacion/          → Análisis y Visualización de Datos
├── 02_analisis_exploratorio/           → Análisis Exploratorio y Curación de Datos
├── 03_introduccion_aprendizaje_automatico/  → Introducción al Aprendizaje Automático
├── 04_aprendizaje_supervisado/         → Aprendizaje Supervisado
├── 05_aprendizaje_no_supervisado/      → Aprendizaje No Supervisado
├── 06_big_data/                        → Programación Distribuida sobre Big Data (Spark)
├── 07_aprendizaje_profundo/            → Introducción al Aprendizaje Profundo
├── 08_series_de_tiempo/                → Series de Tiempo en Finanzas
└── 09_mentoria/                        → Proyecto Final de Mentoría
```

---

## Proyectos

### 01 · Análisis y Visualización de Datos
**Dataset:** Encuesta de sueldos sysarmy 2022 (industria IT argentina)  
**Objetivo:** Determinar qué lenguajes de programación se asocian a los mejores salarios e investigar diferencias salariales por género mediante inferencia estadística.  
**Técnicas:** Análisis descriptivo, estimación por intervalos de confianza, test de hipótesis de Welch.  
[→ Ver proyecto](./01_analisis_visualizacion/README.md)

---

### 02 · Análisis Exploratorio y Curación de Datos
**Dataset:** Melbourne Housing (precios de propiedades) + Airbnb Melbourne + Northwind (SQLite)  
**Objetivo:** Aplicar el pipeline completo de exploración y curación de datos: desde SQL hasta imputación, encoding y reducción de dimensionalidad.  
**Técnicas:** SQL (SQLite/SQLAlchemy), EDA, imputación de valores faltantes, PCA, RandomForest para importancia de features.  
[→ Ver proyecto](./02_analisis_exploratorio/README.md)

---

### 03 · Introducción al Aprendizaje Automático
**Dataset:** California Housing Dataset + Loan Data  
**Objetivo:** Experimentar con distintos modelos de regresión y clasificación, comparar su desempeño y comprender los fundamentos del flujo de ML.  
**Técnicas:** Regresión lineal, polinomial, regularización, pipelines de sklearn, validación cruzada.  
[→ Ver proyecto](./03_introduccion_aprendizaje_automatico/README.md)

---

### 04 · Aprendizaje Supervisado
**Dataset:** Diabetes Prediction Dataset (Kaggle)  
**Objetivo:** Construir modelos de clasificación para predecir diabetes a partir de datos clínicos y demográficos, superando un baseline en competencia Kaggle.  
**Técnicas:** Decision Tree, Random Forest, Gradient Boosting, SVM, GridSearchCV, métricas de clasificación.  
[→ Ver proyecto](./04_aprendizaje_supervisado/README.md)

---

### 05 · Aprendizaje No Supervisado
**Dataset:** FIFA 23 — Female Players Dataset (Kaggle)  
**Objetivo:** Descubrir grupos naturales entre jugadoras de FIFA 23 mediante técnicas de clustering y reducción de dimensionalidad.  
**Técnicas:** K-Means, DBSCAN, PCA, embeddings, imputación, análisis de clusters.  
[→ Ver proyecto](./05_aprendizaje_no_supervisado/README.md)

---

### 06 · Big Data con Apache Spark
**Entorno:** Apache Spark sobre Apache Zeppelin (notebooks `.zpln`)  
**Objetivo:** Procesar grandes volúmenes de datos usando computación distribuida; construir pipelines de ML con MLlib y analizar grafos sociales.  
**Técnicas:** RDDs, DataFrames, Spark SQL, MLlib Pipelines, GraphX / GraphFrames.  
[→ Ver proyecto](./06_big_data/README.md)

---

### 07 · Aprendizaje Profundo
**Objetivo:** Aplicar redes neuronales profundas a problemas de clasificación y/o visión por computadora.  
**Técnicas:** Redes fully connected, CNNs, transfer learning, regularización, optimizadores.  
[→ Ver proyecto](./07_aprendizaje_profundo/README.md)

---

### 08 · Series de Tiempo en Finanzas
**Dataset:** Demanda de energía eléctrica (Victoria) + datos financieros  
**Objetivo:** Analizar y modelar series temporales aplicando técnicas clásicas y modelos de volatilidad financiera.  
**Técnicas:** Descomposición de series, ACF/PACF, modelos ARIMA, GARCH, visualización radial/circular.  
[→ Ver proyecto](./08_series_de_tiempo/README.md)

---

### 09 · Mentoría — Predicción de Demanda de Ventas
**Dataset:** Datos históricos de ventas de materiales por país y zona (empresa proveedora)  
**Objetivo:** Proyecto integrador end-to-end: desde el análisis exploratorio hasta la construcción de modelos supervisados para predecir la demanda mensual.  
**Técnicas:** EDA completo, curación de datos, feature engineering para series de tiempo, modelos supervisados aplicados a datos temporales.  
[→ Ver proyecto](./09_mentoria/README.md)

---

## Stack tecnológico

| Área | Herramientas |
|---|---|
| Lenguaje | Python 3 |
| Manipulación de datos | `pandas`, `numpy` |
| Visualización | `matplotlib`, `seaborn`, `plotly` |
| Machine Learning | `scikit-learn` |
| Deep Learning | `PyTorch` / `TensorFlow` |
| Series de tiempo | `statsmodels`, `arch` (GARCH) |
| Big Data | `Apache Spark`, `PySpark`, `Apache Zeppelin` |
| Bases de datos | `SQLite`, `SQLAlchemy` |
| Entorno | `Jupyter Notebook`, `Google Colab` |

---
