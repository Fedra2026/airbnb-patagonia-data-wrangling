# Data Wrangling | Airbnb Patagonia Argentina

## 📌 Descripción del proyecto

Proyecto de **Data Wrangling desarrollado con Python** sobre datos de alojamientos de Airbnb correspondientes a distintas localidades de la Patagonia Argentina.

El objetivo fue integrar y transformar múltiples fuentes de datos en un dataset consistente y preparado para análisis, abordando problemas habituales de calidad de datos como **duplicados, valores faltantes, formatos inconsistentes, información semiestructurada y valores atípicos**.

Además de realizar las transformaciones necesarias, el proyecto pone énfasis en **analizar y justificar las decisiones tomadas durante el proceso de limpieza**, preservando la trazabilidad de los datos.

---

## 🎯 Objetivos

* Integrar cuatro fuentes de datos en un único dataset.
* Evaluar la calidad y coherencia de los datos.
* Detectar duplicados exactos y potenciales mediante reglas multivariables.
* Analizar y tratar valores faltantes.
* Comparar diferentes estrategias de imputación.
* Estandarizar formatos y tipos de datos.
* Crear nuevas variables mediante **Feature Engineering**.
* Analizar la distribución de precios y detectar outliers.
* Comparar estrategias de discretización.
* Extraer información desde variables semiestructuradas.
* Enriquecer el dataset mediante una **API REST**.
* Explorar la relación entre las características de los alojamientos y sus precios.

---

## 🛠️ Tecnologías utilizadas

* Python
* Pandas
* NumPy
* SciPy
* Matplotlib
* Seaborn
* Plotly
* Requests
* REST API
* Google Colab / Jupyter Notebook

---

## 🔄 Pipeline de Data Wrangling

**Integración → Perfilado → Duplicados → Valores faltantes → Estandarización → Feature Engineering → Outliers → Enriquecimiento mediante API → Análisis**

### Dataset inicial

* **1.080 registros**
* **12 variables**
* **4 fuentes de datos**

### Dataset final

* **1.007 registros**
* **26 variables**
* **73 registros redundantes eliminados**

---

## 🔍 Principales etapas

### 1. Integración y evaluación de calidad

Se consolidaron cuatro fuentes de datos en una única estructura y se realizó un análisis inicial para identificar problemas de calidad, inconsistencias y valores faltantes.

### 2. Detección y tratamiento de duplicados

La identificación de registros redundantes no se limitó a buscar filas exactamente iguales.

Se analizaron múltiples atributos para diferenciar entre posibles duplicados y observaciones similares pero válidas, evitando eliminar información únicamente por la coincidencia de un identificador.

Como resultado del proceso se eliminaron **73 registros redundantes**, reduciendo el dataset de 1.080 a 1.007 observaciones.

### 3. Tratamiento de valores faltantes

Se analizó la distribución de valores faltantes y se aplicaron diferentes estrategias según las características de cada variable.

En determinados casos se compararon alternativas de imputación, como **media y mediana segmentada**, evaluando cómo la distribución de los datos y la presencia de valores extremos podían afectar el resultado.

### 4. Limpieza y transformación

Se estandarizaron variables como precios y ratings, convirtiendo información almacenada en formatos no adecuados para análisis en variables estructuradas y numéricas.

Siempre que resultó conveniente se conservaron los datos originales y se generaron nuevas variables procesadas para mantener la **trazabilidad de las transformaciones**.

### 5. Feature Engineering

Se generaron nuevas características a partir de las variables originales para aumentar su utilidad analítica.

Entre ellas, se extrajeron variables como:

* `beds`
* `bedrooms`
* `bathrooms`

a partir de información originalmente almacenada como texto semiestructurado.

### 6. Discretización de precios

Se compararon estrategias de segmentación mediante **intervalos de igual ancho** e **intervalos de igual frecuencia**.

La comparación permitió evaluar qué alternativa representaba mejor la distribución real de los precios y generaba segmentos más útiles para el análisis.

### 7. Análisis de outliers

Los valores atípicos fueron evaluados en su contexto antes de decidir su tratamiento.

El objetivo fue evitar eliminar automáticamente observaciones extremas que podían corresponder a alojamientos reales con características particulares.

### 8. Sanity checks

Se realizaron controles de coherencia para evaluar si las distribuciones y valores obtenidos después del procesamiento resultaban razonables dentro del contexto de los datos analizados.

Estos controles permitieron complementar las validaciones estadísticas con una evaluación de la consistencia general de los resultados.

### 9. Enriquecimiento mediante API

El dataset fue enriquecido con información externa de **amanecer y atardecer** mediante una API REST.

Se implementaron solicitudes mediante `requests` y mecanismos para evitar llamadas innecesariamente repetidas, mejorando la eficiencia del proceso.

### 10. Análisis de relaciones entre variables

Finalmente, se exploró la relación entre el precio y diferentes características de los alojamientos, incluyendo cantidad de baños, dormitorios y camas.

Entre las variables analizadas, la cantidad de **baños presentó la asociación lineal positiva más fuerte con el precio**, con una correlación de Pearson aproximada de **r ≈ 0,67**.

Esta asociación se interpreta como descriptiva y no implica causalidad.

---

## 💡 Principales aprendizajes

Uno de los principales aprendizajes del proyecto fue comprobar que el **Data Wrangling no consiste simplemente en eliminar datos incompletos, duplicados o valores extremos**.

Muchas decisiones requieren investigar las anomalías, comprender el contexto y establecer criterios que permitan diferenciar entre errores reales y observaciones válidas.

El proyecto también permitió aplicar conceptos relacionados con **calidad de datos, trazabilidad, ingeniería de variables, integración de fuentes externas y validación de resultados**.

---

## 🚀 Competencias demostradas

`Python` · `Pandas` · `Data Wrangling` · `Data Cleaning` · `Data Quality` · `Feature Engineering` · `Missing Data` · `Duplicate Detection` · `Outlier Analysis` · `Data Validation` · `API Integration` · `Exploratory Data Analysis`

---

## 📂 Notebook

El análisis completo, incluyendo código, visualizaciones, decisiones metodológicas y resultados, se encuentra disponible en:

**`Data_Wrangling_Airbnb_Patagonia.ipynb`**

---

## 📊 Resultado

El proceso permitió transformar cuatro fuentes de datos con diferentes problemas de calidad en un dataset final de **1.007 registros y 26 variables**, preparado para análisis.

El foco del proyecto no estuvo únicamente en ejecutar transformaciones con Python y Pandas, sino también en **investigar anomalías, justificar las decisiones de limpieza y preservar la trazabilidad durante todo el proceso de Data Wrangling**.
