# Aprendizaje Supervisado — Predicción de Diabetes

> Trabajo práctico — **Aprendizaje Supervisado**  
> Diplomatura en Ciencia de Datos, Aprendizaje Automático y sus Aplicaciones · Edición 2023  
> FaMAFyC, Universidad Nacional de Córdoba

---

## Descripción

Competencia de clasificación en Kaggle: construir el mejor modelo posible para predecir si un paciente tiene diabetes a partir de su historial médico y datos demográficos. El objetivo fue superar el puntaje del baseline provisto por la cátedra usando al menos tres modelos distintos.

---

## Estructura

```
04_aprendizaje_supervisado/
├── README.md
├── notebooks/
│   ├── 00_baseline.ipynb                   ← baseline provisto por la cátedra
│   └── 01_diabetes_prediction.ipynb        ← análisis exploratorio + modelos finales
└── data/
    ├── diabetes_prediction_dataset_train-labeled.csv
    └── diabetes_prediction_dataset_test.csv
```

---

## Notebooks

### `00_baseline.ipynb` — Baseline de la cátedra
- Implementación de referencia con **Árbol de Decisión** y `GridSearchCV`.
- Generación del archivo `submission.csv` para Kaggle.
- Sirve como punto de partida y piso mínimo a superar.

### `01_diabetes_prediction.ipynb` — Solución del grupo
- **Análisis exploratorio de datos (EDA):**
  - Distribución de la variable target (desbalance de clases).
  - Análisis de correlaciones y distribuciones por clase.
  - Detección de outliers en BMI, HbA1c y glucosa en sangre.
- **Preprocesamiento:**
  - Encoding de variables categóricas (`gender`, `smoking_history`).
  - Escalado de features numéricas.
  - Estrategia para manejo del desbalance de clases.
- **Modelos entrenados y comparados:**
  - Árbol de Decisión (baseline)
  - **Random Forest**
  - **Gradient Boosting (XGBoost / sklearn)**
  - **Support Vector Machine (SVM)**
  - Regresión Logística
- **Optimización:**
  - `GridSearchCV` y `RandomizedSearchCV` para búsqueda de hiperparámetros.
  - Validación cruzada estratificada (k-fold).
- **Evaluación:**
  - Accuracy score (métrica de la competencia Kaggle).
  - Precision, recall, F1-score, AUC-ROC.
  - Matrices de confusión comparativas.

---

## Dataset

**Fuente:** [Kaggle — Diabetes Prediction Dataset](https://www.kaggle.com/datasets/iammustafatz/diabetes-prediction-dataset)

| Variable | Tipo | Descripción |
|---|---|---|
| `gender` | categórica | Sexo biológico (`Male`, `Female`, `Other`) |
| `age` | numérica | Edad del paciente (0–80) |
| `hypertension` | binaria | Presencia de hipertensión (0/1) |
| `heart_disease` | binaria | Presencia de enfermedad cardíaca (0/1) |
| `smoking_history` | categórica | Historial de tabaquismo (5 categorías) |
| `bmi` | numérica | Índice de masa corporal (10.16–71.55) |
| `HbA1c_level` | numérica | Nivel de hemoglobina glicosilada (indicador de glucemia promedio) |
| `blood_glucose_level` | numérica | Nivel de glucosa en sangre |
| `diabetes` | binaria | **Variable target** — presencia de diabetes (0/1) |

**Split:** ~80% entrenamiento / ~20% test (formato Kaggle)

---

## Resultados

| Modelo | Accuracy (CV) |
|---|---|
| Árbol de Decisión (baseline) | — |
| Random Forest | — |
| Gradient Boosting | — |
| SVM | — |

> Los valores exactos están en el notebook `01_diabetes_prediction.ipynb`.

---

## Técnicas aplicadas

- Análisis exploratorio de datos con visualizaciones
- Encoding de variables categóricas (`LabelEncoder`, `OrdinalEncoder`)
- Manejo de desbalance de clases (class_weight, oversampling)
- Modelos de ensemble (Random Forest, Gradient Boosting)
- Optimización de hiperparámetros con `GridSearchCV`
- Validación cruzada estratificada
- Métricas de clasificación completas (accuracy, F1, AUC-ROC)

---

## Tecnologías

- **Lenguaje:** Python 3
- **Bibliotecas:** `pandas`, `numpy`, `matplotlib`, `seaborn`, `scikit-learn`, `xgboost`

---

## Contexto académico

Trabajo realizado para la materia **Aprendizaje Supervisado** de la Diplomatura en Ciencia de Datos, Aprendizaje Automático y sus Aplicaciones (FaMAFyC, UNC, Edición 2023). Competencia en [Kaggle](https://www.kaggle.com/t/ffbd02f08a14443194f84dff7b8c2f1f).
