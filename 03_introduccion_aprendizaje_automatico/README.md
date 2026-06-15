# Introducción al Aprendizaje Automático

> Trabajo práctico — **Introducción al Aprendizaje Automático**  
> Diplomatura en Ciencia de Datos, Aprendizaje Automático y sus Aplicaciones · Edición 2023  
> FaMAFyC, Universidad Nacional de Córdoba

---

## Descripción

Experimentación con algoritmos fundamentales de Machine Learning sobre dos datasets reales. El proyecto recorre el flujo completo de ML: exploración, selección y transformación de features, entrenamiento de modelos, evaluación y comparación. El foco está en entender el impacto de cada decisión de diseño sobre el desempeño del modelo.

---

## Estructura

```
03_introduccion_aprendizaje_automatico/
├── README.md
├── notebooks/
│   ├── 01_regresion_california.ipynb   ← regresión sobre California Housing
│   └── 02_clasificacion_loan.ipynb     ← clasificación sobre datos de préstamos
└── data/
    └── loan_data.csv
```

---

## Notebooks

### `01_regresion_california.ipynb` — Regresión: California Housing Dataset
**Problema:** Predecir el valor mediano de una vivienda en California a partir de datos del censo de 1990.

- Carga del dataset con `sklearn.datasets.fetch_california_housing`.
- Análisis exploratorio: distribuciones, correlaciones y visualización geográfica.
- Selección manual de atributos relevantes.
- Entrenamiento y comparación de modelos:
  - **Regresión Lineal** (baseline)
  - **Regresión Polinomial** (grado 2 y 3)
  - **Ridge** y **Lasso** (regularización L2 y L1)
- Evaluación con métricas: MSE, RMSE, R².
- Análisis del trade-off entre complejidad del modelo y generalización.
- Uso de `Pipeline` de sklearn para encadenar preprocesamiento y modelo.

### `02_clasificacion_loan.ipynb` — Clasificación: Loan Data
**Problema:** Predecir si un solicitante de préstamo tendrá dificultades para pagarlo.

- Exploración del dataset: distribución de clases, análisis de features.
- Preprocesamiento: escalado, encoding de variables categóricas, manejo de desbalance.
- Entrenamiento y comparación de clasificadores:
  - **Regresión Logística**
  - **Árbol de Decisión**
  - **K-Nearest Neighbors**
- Evaluación: accuracy, precision, recall, F1-score, matriz de confusión.
- Optimización de hiperparámetros con **GridSearchCV**.
- Análisis de curvas de aprendizaje.

---

## Dataset — California Housing

| Variable | Descripción |
|---|---|
| `MedInc` | Ingreso mediano del bloque (en decenas de miles de USD) |
| `HouseAge` | Antigüedad mediana de las viviendas del bloque |
| `AveRooms` | Promedio de habitaciones por vivienda |
| `AveBedrms` | Promedio de dormitorios por vivienda |
| `Population` | Población del bloque |
| `AveOccup` | Promedio de ocupantes por vivienda |
| `Latitude` | Latitud del bloque |
| `Longitude` | Longitud del bloque |
| `MedHouseVal` | **Valor mediano de la vivienda** (target, en cientos de miles de USD) |

20.640 instancias · 8 features · problema de regresión

---

## Técnicas aplicadas

- Análisis exploratorio y selección de features
- Pipelines de preprocesamiento con `sklearn.pipeline`
- Regresión lineal, polinomial y regularizada (Ridge, Lasso)
- Clasificación con árboles, KNN y regresión logística
- Validación cruzada y búsqueda de hiperparámetros con `GridSearchCV`
- Métricas de regresión (MSE, RMSE, R²) y clasificación (accuracy, F1, AUC)

---

## Tecnologías

- **Lenguaje:** Python 3
- **Bibliotecas:** `pandas`, `numpy`, `matplotlib`, `seaborn`, `scikit-learn`

---

## Contexto académico

Trabajo realizado para la materia **Introducción al Aprendizaje Automático** de la Diplomatura en Ciencia de Datos, Aprendizaje Automático y sus Aplicaciones (FaMAFyC, UNC, Edición 2023).
