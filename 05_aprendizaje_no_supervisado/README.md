# Aprendizaje No Supervisado — Clustering de Jugadoras FIFA 23

> Trabajo práctico — **Aprendizaje No Supervisado**  
> Diplomatura en Ciencia de Datos, Aprendizaje Automático y sus Aplicaciones · Edición 2023  
> FaMAFyC, Universidad Nacional de Córdoba

---

## Descripción

Aplicación de técnicas de aprendizaje no supervisado sobre el dataset de jugadoras femeninas de FIFA 23. El proyecto busca descubrir agrupaciones naturales entre las jugadoras a partir de sus atributos de juego, sin utilizar etiquetas predefinidas. Se combinan técnicas de curación, reducción de dimensionalidad y clustering para encontrar perfiles de jugadoras significativos.

---

## Estructura

```
05_aprendizaje_no_supervisado/
├── README.md
├── notebooks/
│   ├── 01_curacion_imputacion.ipynb    ← limpieza e imputación del dataset
│   └── 02_clustering.ipynb             ← reducción de dimensionalidad y clustering
└── data/
    ├── female_players.csv              ← dataset original (FIFA 23 female players)
    └── df_clean.csv                    ← dataset curado generado en notebook 01
```

---

## Notebooks

### `01_curacion_imputacion.ipynb` — Curación e Imputación
- Carga del dataset de jugadoras femeninas de FIFA 23 (Kaggle).
- Exploración inicial: tipos de variables, valores faltantes, distribuciones.
- Selección de atributos relevantes para el análisis de perfiles de juego.
- Estrategias de imputación:
  - Variables numéricas: imputación por mediana o por grupo (posición de la jugadora).
  - Variables categóricas: imputación por moda.
- Análisis de correlaciones entre atributos de juego.
- Exportación del dataset limpio (`df_clean.csv`) para el análisis de clustering.

### `02_clustering.ipynb` — Reducción de Dimensionalidad y Clustering
- Carga del dataset curado.
- **Reducción de dimensionalidad:**
  - Aplicación de **PCA** para visualización 2D/3D y para reducir ruido.
  - Análisis de varianza explicada por componente.
- **Clustering:**
  - **K-Means:** determinación del número óptimo de clusters con el método del codo (Elbow) y el coeficiente de Silhouette.
  - **DBSCAN:** exploración de parámetros `eps` y `min_samples`; detección de outliers.
  - Comparación de resultados entre métodos.
- **Interpretación de clusters:**
  - Perfil de cada cluster: estadísticos descriptivos por atributo.
  - Visualización de clusters en espacio reducido (PCA 2D).
  - Caracterización de perfiles de jugadoras (ej.: porteras, delanteras de velocidad, defensoras físicas).
- **Aprendizaje semi-supervisado:** exploración de técnicas que aprovechan las etiquetas de posición como señal débil.

---

## Dataset

**Fuente:** [Kaggle — FIFA 23 Complete Player Dataset](https://www.kaggle.com/datasets/stefanoleone992/fifa-23-complete-player-dataset)  
**Subset utilizado:** `female_players.csv` — jugadoras de la edición femenina de FIFA 23.

**Variables de juego utilizadas (ejemplos):**

| Variable | Descripción |
|---|---|
| `overall` | Valoración global de la jugadora |
| `pace` | Velocidad |
| `shooting` | Capacidad de remate |
| `passing` | Precisión de pase |
| `dribbling` | Habilidad de regate |
| `defending` | Capacidad defensiva |
| `physic` | Condición física |
| `player_positions` | Posición(es) en el campo |

---

## Técnicas aplicadas

- Curación e imputación de datos faltantes
- Análisis de correlaciones
- Reducción de dimensionalidad con **PCA**
- Clustering con **K-Means** y **DBSCAN**
- Métricas de evaluación de clustering: Elbow Method, Silhouette Score
- Visualización de alta dimensionalidad en 2D
- Interpretación y caracterización de clusters

---

## Tecnologías

- **Lenguaje:** Python 3
- **Bibliotecas:** `pandas`, `numpy`, `matplotlib`, `seaborn`, `scikit-learn`

---

## Contexto académico

Trabajo realizado para la materia **Aprendizaje No Supervisado** de la Diplomatura en Ciencia de Datos, Aprendizaje Automático y sus Aplicaciones (FaMAFyC, UNC, Edición 2023).
