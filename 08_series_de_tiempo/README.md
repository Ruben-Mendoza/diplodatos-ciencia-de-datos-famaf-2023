# Series de Tiempo en Finanzas

> Trabajo práctico — **Series de Tiempo en Finanzas**  
> Diplomatura en Ciencia de Datos, Aprendizaje Automático y sus Aplicaciones · Edición 2023  
> FaMAFyC, Universidad Nacional de Córdoba

---

## Descripción

Análisis y modelado de series temporales aplicado a datos reales de demanda energética y series financieras. El proyecto cubre desde la exploración y visualización de patrones temporales hasta la modelización de la volatilidad con modelos GARCH, pasando por técnicas de descomposición y visualización circular/radial.

---

## Estructura

```
08_series_de_tiempo/
├── README.md
└── notebooks/
    ├── 01_demanda_energia_visualizacion.ipynb   ← análisis de demanda eléctrica (Victoria)
    ├── 02_entregable_2.ipynb                    ← modelado de series y predicción
    └── 03_garch_volatilidad.ipynb               ← modelos GARCH para series financieras
```

---

## Notebooks

### `01_demanda_energia_visualizacion.ipynb` — Demanda de Energía Eléctrica
**Dataset:** Demanda mensual de energía eléctrica en Victoria (Australia).

- Carga y exploración de la serie temporal de demanda.
- **Visualizaciones avanzadas** siguiendo el estilo de la notebook de referencia de la cátedra:
  - **Gráfico de radar** (spider chart): comparación de la demanda mensual por año.
  - **Gráfico de barra circular** (circular bar chart): distribución de demanda por mes.
  - **Gráfico de ploteo radial:** representación polar de la estacionalidad.
  - Composición de una imagen única uniendo los gráficos anuales para cada tipo.
- Análisis de **estacionalidad** y **tendencia**.
- Generación de la imagen final con `PIL` concatenando los subplots.

### `02_entregable_2.ipynb` — Modelado de Series de Tiempo
- Descomposición de la serie en tendencia, estacionalidad y residuo.
- Análisis de **autocorrelación** (ACF) y autocorrelación parcial (PACF).
- Prueba de estacionariedad: **test de Dickey-Fuller aumentado**.
- Diferenciación para lograr estacionariedad.
- Ajuste y evaluación de modelos:
  - **ARIMA** (AutoRegressive Integrated Moving Average)
  - **SARIMA** (ARIMA con componente estacional)
- Predicción y evaluación con MAE, RMSE.

### `03_garch_volatilidad.ipynb` — Modelos GARCH
**Dataset:** Series de retornos financieros.

- Introducción a la modelización de la **volatilidad** en finanzas.
- Estilizados hechos de las series financieras (fat tails, clustering de volatilidad).
- Análisis de los retornos: distribución, ACF de los cuadrados de los retornos.
- Ajuste del modelo **GARCH(p,q)** con la librería `arch`.
- Selección de órdenes p y q por criterio de información (AIC, BIC).
- Diagnóstico de residuos estandarizados.
- Estimación y visualización de la volatilidad condicional.

---

## Datasets

| Dataset | Descripción |
|---|---|
| Demanda eléctrica Victoria | Serie mensual de consumo de electricidad en el estado de Victoria, Australia |
| Series financieras | Precios de cierre y retornos logarítmicos de activos financieros |

---

## Técnicas aplicadas

- Visualización polar/radial con `matplotlib` (radar charts, circular bar charts)
- Descomposición de series temporales (`statsmodels.tsa.seasonal`)
- ACF y PACF (`statsmodels.graphics.tsaplots`)
- Test de Dickey-Fuller (`statsmodels.tsa.stattools.adfuller`)
- Modelos ARIMA y SARIMA (`statsmodels.tsa.arima`)
- Modelos GARCH (`arch.arch_model`)
- Composición de imágenes con `PIL`

---

## Tecnologías

- **Lenguaje:** Python 3
- **Bibliotecas:** `pandas`, `numpy`, `matplotlib`, `seaborn`, `plotly`, `statsmodels`, `arch`, `PIL`

---

## Contexto académico

Trabajo realizado para la materia **Series de Tiempo en Finanzas** de la Diplomatura en Ciencia de Datos, Aprendizaje Automático y sus Aplicaciones (FaMAFyC, UNC, Edición 2023).
