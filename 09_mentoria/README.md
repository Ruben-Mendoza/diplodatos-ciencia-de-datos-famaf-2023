# Mentoría — Predicción de Demanda de Ventas con Machine Learning

> Proyecto Final de Mentoría  
> Diplomatura en Ciencia de Datos, Aprendizaje Automático y sus Aplicaciones · Edición 2023  
> FaMAFyC, Universidad Nacional de Córdoba  
> **Tutor:** Sebastián Ormaechea

---

## Descripción

Proyecto integrador end-to-end que aplica el ciclo completo de ciencia de datos a un problema de negocio real: **predecir la demanda mensual de materiales** en los distintos países y zonas donde opera una empresa proveedora. El proyecto atraviesa las tres grandes etapas del flujo de ML: análisis y visualización, exploración y curación, y modelado supervisado aplicado a datos de series temporales.

---

## Objetivo

> Construir un modelo capaz de predecir el próximo mes de ventas de materiales por país y zona, que sirva como herramienta de planificación para la empresa.

---

## Estructura

```
09_mentoria/
├── README.md
└── notebooks/
    ├── 01_analisis_visualizacion.ipynb         ← EDA y visualización del negocio
    ├── 02_exploracion_curacion.ipynb           ← curación y preparación del dataset
    └── 03_ml_supervisado_series_tiempo.ipynb   ← modelos supervisados para predicción
```

---

## Notebooks

### `01_analisis_visualizacion.ipynb` — Análisis y Visualización
- Exploración inicial del dataset de ventas históricas.
- Identificación de las variables más relevantes para el objetivo de predicción.
- **Análisis de distribuciones:** ventas por país, por zona, por categoría de material.
- **Identificación de correlaciones** entre variables del negocio.
- Detección de **outliers** y valores atípicos en los registros de ventas.
- Análisis del **problema de valores faltantes** y estrategias propuestas.
- Visualizaciones clave para comunicar el comportamiento de la demanda:
  - Evolución temporal de ventas por región.
  - Comparativas entre zonas geográficas.
  - Distribución de ventas por categoría de producto.

### `02_exploracion_curacion.ipynb` — Exploración y Curación de Datos
- Aplicación del proceso completo de curación sobre el dataset de ventas.
- Tratamiento de valores faltantes con estrategias diferenciadas por variable.
- Detección y manejo de **anomalías** en los registros históricos.
- **Feature engineering** orientado a series de tiempo:
  - Variables de lag (ventas del mes anterior, 3 meses antes, mismo mes del año anterior).
  - Variables de ventana deslizante (media móvil, desviación estándar).
  - Features de calendario: mes, trimestre, día de la semana, indicadores de temporada.
- Encoding de variables categóricas (país, zona, categoría).
- Exportación del dataset curado y enriquecido.

### `03_ml_supervisado_series_tiempo.ipynb` — Modelado Supervisado
- Formulación del problema de predicción de demanda como problema supervisado.
- **Split temporal** del dataset (respetando el orden cronológico para evitar data leakage).
- Entrenamiento y comparación de modelos:
  - **Regresión Lineal** (baseline)
  - **Random Forest Regressor**
  - **Gradient Boosting (XGBoost)**
- Evaluación con métricas de regresión: MAE, RMSE, MAPE.
- Análisis de importancia de features: qué variables predicen mejor la demanda.
- Visualización de predicciones vs. valores reales por zona geográfica.
- Discusión de limitaciones del enfoque y próximos pasos.

---

## Dataset

**Fuente:** Dataset interno de la empresa (proporcionado por el tutor de mentoría).

| Variable | Descripción |
|---|---|
| Fecha | Período mensual del registro de ventas |
| País | País de operación |
| Zona | Zona geográfica dentro del país |
| Categoría | Categoría de material vendido |
| Ventas | Unidades/monto vendido en el período (**target**) |

---

## Pipeline del proyecto

```
Datos históricos de ventas
        │
        ▼
[01] Análisis y Visualización
   → Entender el negocio y los datos
        │
        ▼
[02] Exploración y Curación
   → Dataset limpio + features de series de tiempo
        │
        ▼
[03] Modelado Supervisado
   → Modelo de predicción mensual por zona
        │
        ▼
Predicción del próximo mes de ventas
```

---

## Técnicas aplicadas

- Análisis exploratorio de datos orientado al negocio
- Curación e imputación de datos temporales
- Feature engineering para series de tiempo (lags, rolling windows, calendario)
- Split temporal sin data leakage
- Modelos de regresión: lineal, Random Forest, Gradient Boosting
- Métricas de regresión: MAE, RMSE, MAPE
- Análisis de importancia de features (feature importance)

---

## Tecnologías

- **Lenguaje:** Python 3
- **Bibliotecas:** `pandas`, `numpy`, `matplotlib`, `seaborn`, `scikit-learn`, `xgboost`
- **Entorno:** Google Colab

---

## Contexto académico

La mentoría es el proyecto integrador de la Diplomatura. Consiste en aplicar todas las herramientas aprendidas a lo largo del programa sobre un dataset y problema real, con el acompañamiento de un tutor experto de la industria. Esta mentoría fue guiada por **Sebastián Ormaechea** (FaMAFyC, UNC, Edición 2023).
