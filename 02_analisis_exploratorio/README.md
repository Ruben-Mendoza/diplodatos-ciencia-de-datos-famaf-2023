# Análisis Exploratorio y Curación de Datos

> Trabajo práctico — **Análisis Exploratorio y Curación de Datos**  
> Diplomatura en Ciencia de Datos, Aprendizaje Automático y sus Aplicaciones · Edición 2023  
> FaMAFyC, Universidad Nacional de Córdoba

---

## Descripción

Aplicación del pipeline completo de exploración y curación de datos sobre el mercado inmobiliario de Melbourne y el mercado de alquileres temporarios (Airbnb). El proyecto cubre desde la consulta de datos relacionales en SQL hasta la preparación del dataset para su uso en modelos de Machine Learning, incluyendo imputación, encoding y reducción de dimensionalidad.

---

## Estructura

```
02_analisis_exploratorio/
├── README.md
├── notebooks/
│   ├── 01_ejercicio1_sqlite.ipynb              ← consultas SQL y construcción de DB
│   ├── 02_ejercicios2_3_exploracion.ipynb      ← EDA, visualización y curación
│   └── 03_entregable2_PCA.ipynb                ← imputación, encoding y PCA
└── data/
    └── melb_data.csv                           ← dataset principal (Melbourne Housing)
```

---

## Notebooks

### `01_ejercicio1_sqlite.ipynb` — SQL y bases de datos relacionales
- Creación de una base de datos SQLite con **SQLAlchemy** a partir del dataset Northwind.
- Escritura y ejecución de consultas SQL sobre datos relacionales con `ipython-sql`.
- Exploración de la estructura relacional: joins, agregaciones y filtros.

### `02_ejercicios2_3_exploracion.ipynb` — Exploración y curación
- Carga y exploración inicial del dataset Melbourne Housing (~13.000 propiedades).
- Análisis de valores faltantes: cuantificación por columna y estrategia de tratamiento.
- Selección de features relevantes para la predicción de precios de propiedades.
- Visualizaciones de distribuciones, correlaciones y relaciones entre variables clave (`Price`, `Rooms`, `Distance`, `Type`).
- Exploración cruzada con datos de Airbnb Melbourne (`cleansed_listings_dec18.csv`): análisis de precios por zona geográfica.
- Tratamiento de outliers y codificación de variables categóricas.

### `03_entregable2_PCA.ipynb` — Imputación, encoding y reducción de dimensionalidad
- Imputación de valores faltantes con estrategias diferenciadas por tipo de variable (mediana para numéricas, moda para categóricas).
- Encoding de variables categóricas ordinales y nominales.
- Análisis de importancia de features con **RandomForestRegressor**.
- Aplicación de **PCA** para reducción de dimensionalidad y análisis de varianza explicada.
- Construcción del dataset final curado, listo para modelado.

---

## Datasets

| Dataset | Descripción | Filas |
|---|---|---|
| `melb_data.csv` | Propiedades vendidas en Melbourne (2016–2018) | ~13.500 |
| `melbourne_housing_curated_data.csv` | Versión curada generada en el práctico | variable |
| `melbourne_housing_inputed_data.csv` | Versión con imputación completa | variable |
| `cleansed_listings_dec18.csv` | Listados de Airbnb Melbourne (dic 2018) | ~14.000 |
| `airbnb_price_by_zipcode.csv` | Precio promedio de Airbnb por código postal | ~100 |
| `northwind.sqlite3` | Base de datos relacional Northwind | — |

**Variables clave del dataset Melbourne Housing:**

| Variable | Tipo | Descripción |
|---|---|---|
| `Price` | numérica | Precio de venta de la propiedad (AUD) — *target* |
| `Rooms` | numérica | Cantidad de habitaciones |
| `Type` | categórica | Tipo de propiedad (`h` = house, `u` = unit, `t` = townhouse) |
| `Distance` | numérica | Distancia al CBD (km) |
| `Suburb` | categórica | Barrio |
| `YearBuilt` | numérica | Año de construcción |
| `Landsize` | numérica | Superficie del terreno (m²) |

---

## Técnicas aplicadas

- Consultas SQL con `SQLAlchemy` e `ipython-sql`
- Análisis exploratorio de datos (EDA)
- Detección y tratamiento de valores faltantes
- Visualización con `matplotlib` y `seaborn`
- Reducción de dimensionalidad con **PCA** (`sklearn.decomposition`)
- Importancia de features con **RandomForestRegressor**
- Encoding con `LabelEncoder` y `OrdinalEncoder`

---

## Tecnologías

- **Lenguaje:** Python 3
- **Bibliotecas:** `pandas`, `numpy`, `matplotlib`, `seaborn`, `scikit-learn`, `sqlalchemy`, `ipython-sql`

---

## Contexto académico

Trabajo realizado para la materia **Análisis Exploratorio y Curación de Datos** de la Diplomatura en Ciencia de Datos, Aprendizaje Automático y sus Aplicaciones (FaMAFyC, UNC, Edición 2023).
