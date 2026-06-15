# Análisis y Visualización de Salarios en la Industria IT Argentina

> Trabajo práctico — **Análisis y Visualización de Datos**  
> Diplomatura en Ciencia de Datos, Aprendizaje Automático y sus Aplicaciones · Edición 2023  
> FaMAFyC, Universidad Nacional de Córdoba

---

## Descripción

Análisis exploratorio, estadístico e inferencial de los salarios en la industria de tecnología argentina, a partir de la encuesta de sueldos **sysarmy 2022**. El trabajo se estructura en tres etapas: preprocesamiento del dataset crudo, análisis descriptivo y de distribuciones, e inferencia estadística sobre diferencias salariales por género.

La pregunta central que guía el análisis es: **¿cuáles son los lenguajes de programación asociados a los mejores salarios?** A partir de ella se desprenden preguntas secundarias sobre distribuciones, asociaciones entre variables y diferencias entre subpoblaciones.

---

## Estructura del repositorio

```
analisis-visualizacion-salarios/
├── README.md
├── datos/
│   └── preprocessed_salaries_dataset.csv   ← dataset preprocesado (3343 filas × 7 columnas)
└── notebooks/
    ├── 01_preprocessing.ipynb              ← limpieza, formateo y construcción del dataset
    ├── 02_entregable_parte1.ipynb          ← análisis descriptivo y visualización
    └── 03_entregable_parte2.ipynb          ← estimación e inferencia estadística
```

> **Orden de ejecución:** correr primero `01_preprocessing.ipynb` o usar directamente el CSV en `datos/` para ejecutar las notebooks 02 y 03.

---

## Contenido de cada notebook

### `01_preprocessing.ipynb` — Preprocesamiento

Exploración inicial y construcción del dataset limpio a partir del dataset original de sysarmy 2022.

- **Selección de columnas** de interés: salarios (bruto y neto), lenguajes de programación, género, años de experiencia, nivel de estudio, dedicación laboral y plataformas.
- **Formateo de tipos:** conversión de años de experiencia a variable categórica ordenada (`0-1`, `1-2`, `3-5`, `6-10`, `10+`); transformación de columnas con listas de herramientas a tipo `list`.
- **Validación de lenguajes:** verificación de que los strings corresponden a lenguajes de programación reconocidos, contrastando contra la lista de Wikipedia.
- **Análisis bruto vs. neto:** detección y tratamiento de inconsistencias donde salario bruto < neto; ajuste de modelo lineal y análisis de su comportamiento por rango salarial.
- **Segmentación full-time / part-time:** los dos grupos se tratan por separado dada la diferencia estructural entre sus distribuciones.
- **Outliers inferiores:** descarte por debajo del salario mínimo vital y móvil de Argentina (ARS 61.953 para 2022, según el Consejo Nacional del Empleo).
- **Outliers superiores:** criterio basado en el top de tecnologías mejor pagas de la encuesta Stack Overflow 2022, descartando entradas con ratio salarial > 1.3 respecto a ese benchmark.
- **Conversión a dólares:** los salarios se expresan en USD usando un valor promedio entre cotización oficial y blue durante 2022.
- **Exportación:** el resultado es el archivo `preprocessed_salaries_dataset.csv`.

---

### `02_entregable_parte1.ipynb` — Análisis descriptivo

**Ejercicio 1 · ¿Qué lenguajes de programación están asociados a los mejores salarios?**

- Selección y limpieza de columnas relevantes; imputación y combinación de salario bruto y neto en una única variable.
- Detección y eliminación de outliers (eliminación del 10% de los datos originales).
- Explosión de la columna de lenguajes (un lenguaje por fila) y conteo de frecuencias.
- Estadísticos descriptivos por lenguaje: media, mediana, desvío estándar, percentiles.
- Visualización comparativa de distribuciones de salario para los 10 lenguajes más usados.

**Ejercicio 2 · Densidades y múltiples variables**

- **Densidad conjunta:** visualización de tres variables numéricas y dos categóricas; descripción del comportamiento del dataset.
- **Asociación:** análisis de correlación entre salario bruto y neto; decisión sobre redundancia de columnas.
- **Densidad condicional:** distribución del salario según nivel de estudios; comparación de histogramas entre dos subpoblaciones e independencia estadística.

---

### `03_entregable_parte2.ipynb` — Estimación e inferencia

El análisis se centra en **diferencias salariales entre varones cis (grupo A) y otros géneros (grupo B)**, separando full-time de part-time.

**Pretratamiento**
- Segmentación del DataFrame en full-time y part-time.
- Justificación del uso de la **mediana** como estimador (distribuciones asimétricas).
- Extracción de submuestra representativa del grupo mayoritario para comparación equilibrada.

**Ejercicio 1 · Estimación puntual e intervalo de confianza**

- Estimación de la diferencia de medias salariales netas (grupo A − grupo B).
- Cálculo bajo distribución **t de Student** (muestras grandes: ~N por TLC; muestras pequeñas: t explícita).
- Full-time: diferencia estimada entre **~USD 285 y USD 295**.
- Part-time: diferencia estimada entre **~USD 40 y USD 130** (mayor incertidumbre por n < 30).

**Ejercicio 2 · Test de hipótesis**

- Formalización: H₀: μ_A = μ_B vs. H_a: μ_A ≠ μ_B.
- Aplicación del **test de Welch** (`scipy.stats.ttest_ind`) con α = 0.05.
- Resultado: p-valor < α → rechazo de H₀; hay evidencia estadística de diferencia salarial por género.
- Visualización de los resultados mediante gráfico de barras comparativo.
- *[Opcional]* Cálculo de potencia del test y tamaño muestral necesario para potencias de 0.8, 0.9 y 0.95 con `tt_ind_solve_power`.

**Ejercicio 3 · Comunicación y visualización**

- Diseño de una visualización orientada a comunicar el resultado más relevante del análisis a una audiencia no técnica.

---

## Dataset

**Fuente original:** [Encuesta de sueldos sysarmy 2022](https://raw.githubusercontent.com/DiploDatos/AnalisisyVisualizacion/master/sysarmy_survey_2022_processed.csv)

**Dataset preprocesado (`preprocessed_salaries_dataset.csv`):**

| Columna | Tipo | Descripción |
|---|---|---|
| `work_dedication` | categórica | `full-time` / `part-time` |
| `salary_comparison_last_semester` | int | Comparación salarial respecto al semestre anterior |
| `profile_level_study` | categórica | Nivel de estudios alcanzado |
| `profile_gender` | categórica | Género del encuestado |
| `profile_experience_range` | categórica ordenada | Rango de años de experiencia (`0-1`, `1-2`, `3-5`, `6-10`, `10+`) |
| `list_of_normalized_languages` | lista (str) | Lenguajes de programación validados contra lista de Wikipedia |
| `usd_monthly_gross_salary` | float | Salario bruto mensual en USD |

3343 filas tras el preprocesamiento (partiendo de 5352 filas originales).

---

## Tecnologías

- **Lenguaje:** Python 3
- **Bibliotecas:** `pandas`, `numpy`, `matplotlib`, `seaborn`, `scipy`

---

## Contexto académico

Trabajo realizado para la materia **Análisis y Visualización de Datos** de la Diplomatura en Ciencia de Datos, Aprendizaje Automático y sus Aplicaciones (FaMAFyC, UNC, Edición 2023). El objetivo fue aplicar el flujo completo de análisis de datos: desde la limpieza y exploración del dataset hasta la comunicación de resultados con inferencia estadística.
