# 🎬 Netflix Data Visualization — Exploratory Insights

*[English](#english) | [Español](#español)*

---

## English

### 📊 Project Overview

Using a dataset with detailed information about Netflix titles (type, release year, country, duration, genre, rating, votes, director, and more), I perform an exploratory data analysis (EDA) with a focus on clear and informative visual storytelling using **Matplotlib** and **Seaborn**.

### 🎯 Objectives

- Practice data visualization skills using Matplotlib and Seaborn.
- Gain insights into the distribution of Netflix content over time and across countries.
- Provide a visual reference that could inform marketing, production, or business strategy.


### 🧰 Technologies used

- Python 3
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Jupyter Notebook

### 🔍 Methodology

1. Load the Excel dataset and define a Netflix-inspired color palette for consistent visuals.
2. Initial exploration: shape, sample rows, dtypes, and summary statistics.
3. **Data cleaning**: remove duplicate rows; fill missing `duracion_minutos` values with the genre-specific median (more robust to outliers than the mean); fill missing `director` values with `"Unknown"` to preserve the rows.
4. Exploratory analysis across content volume over time, content type, genre, ratings vs. votes, duration, country/language, and director-level breakdowns.
5. Visual storytelling with Matplotlib and Seaborn (bar charts, stacked histograms, boxplots, scatter plots).
6. Key insights and business recommendations at the end (bilingual EN/ES notebook).

### 📈 Key findings

- Netflix's catalog is dominated by **movies**, especially titles released between **1995 and 2002** (peaking around 2002 with 450+ releases); there's a modest resurgence after 2010, likely tied to Netflix Originals.
- **Comedy, Documentary, and Drama** are the most common genres (1,100+ titles each), while Reality-TV, Mystery, Sport, and Fantasy are the least represented.
- **Shorts and mini series** tend to have the highest and most consistent ratings, while movies show the widest spread in rating quality.
- The **United States** dominates the catalog (3,500+ titles) and **English** is by far the most common language (4,500+ titles), though international content is growing.
- **Kevin Dunn** is the most prolific director (30+ titles, mostly Sport/Action) but only ranks 6th by average rating among prolific directors; the highest-rated directors overall (e.g. Tane Langton, Sy Cody White) typically have just one or two titles, often documentaries or shorts — quality over quantity.
- Many well-rated titles receive relatively few votes, suggesting under-exposed but high-quality content that could benefit from better discovery/recommendation surfacing.

---

## Español

### 📊 Descripción del proyecto

Usando un dataset con información detallada sobre títulos de Netflix (tipo, año de lanzamiento, país, duración, género, rating, votos, director y más), realizo un análisis exploratorio de datos (EDA) enfocado en contar una historia visual clara e informativa con **Matplotlib** y **Seaborn**.

### 🎯 Objetivos

- Practicar habilidades de visualización de datos con Matplotlib y Seaborn.
- Obtener información sobre la distribución del contenido de Netflix a lo largo del tiempo y entre países.
- Ofrecer una referencia visual que pueda orientar decisiones de marketing, producción o estrategia de negocio.

### 🧰 Herramientas utilizadas

- Python 3
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Jupyter Notebook

### 🔍 Metodología

1. Cargar el dataset de Excel y definir una paleta de colores inspirada en Netflix para visuales consistentes.
2. Exploración inicial: dimensiones, muestra de filas, tipos de dato y estadísticas descriptivas.
3. **Limpieza de datos**: eliminar filas duplicadas; rellenar los valores faltantes de `duracion_minutos` con la mediana específica de cada género (más robusta ante outliers que el promedio); rellenar los valores faltantes de `director` con `"Unknown"` para conservar las filas.
4. Análisis exploratorio sobre el volumen de contenido a lo largo del tiempo, tipo de contenido, género, ratings vs. votos, duración, país/idioma y desglose por director.
5. Narrativa visual con Matplotlib y Seaborn (gráficos de barras, histogramas apilados, boxplots, diagramas de dispersión).
6. Hallazgos clave y recomendaciones de negocio al final (notebook bilingüe EN/ES).

### 📈 Hallazgos principales

- El catálogo de Netflix está dominado por **películas**, especialmente títulos lanzados entre **1995 y 2002** (con un pico alrededor de 2002 con más de 450 lanzamientos); hay un repunte moderado después de 2010, probablemente ligado a los Netflix Originals.
- **Comedy, Documentary y Drama** son los géneros más comunes (más de 1,100 títulos cada uno), mientras que Reality-TV, Mystery, Sport y Fantasy son los menos representados.
- Los **shorts y las mini series** tienden a tener los ratings más altos y consistentes, mientras que las películas muestran la mayor dispersión en la calidad del rating.
- **Estados Unidos** domina el catálogo (más de 3,500 títulos) y el **inglés** es por mucho el idioma más común (más de 4,500 títulos), aunque el contenido internacional está creciendo.
- **Kevin Dunn** es el director más prolífico (30+ títulos, principalmente Sport/Action), pero ocupa apenas el puesto 6 en rating promedio entre los directores prolíficos; los directores mejor calificados en general (p. ej. Tane Langton, Sy Cody White) suelen tener solo uno o dos títulos, a menudo documentales o cortometrajes: calidad sobre cantidad.
- Muchos títulos bien calificados reciben relativamente pocos votos, lo que sugiere contenido de alta calidad pero poco expuesto que podría beneficiarse de un mejor descubrimiento/recomendación.
