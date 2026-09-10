# 📊 Análisis de Estadísticas de Deuda Internacional / International Debt Statistics Analysis

*[Español](#español) | [English](#english)*

---

## Español

Análisis exploratorio de datos de deuda externa de distintos países, utilizando **Python (pandas)** y **SQL (SQLite)** para responder preguntas de negocio sobre los niveles de endeudamiento a nivel global.

### 🎯 Objetivo

Explorar un dataset de deuda internacional para identificar qué países presentan mayor endeudamiento, qué tipos de deuda son más comunes en promedio, y qué país lidera cada categoría de deuda.

### 🗂️ Dataset

El dataset (`data/international_debt.csv`) contiene **2,357 registros** con las siguientes columnas:

| Columna | Descripción |
|---|---|
| `country_name` | Nombre del país o región |
| `country_code` | Código ISO del país |
| `indicator_name` | Nombre del indicador de deuda |
| `indicator_code` | Código del indicador |
| `debt` | Monto de la deuda (en USD corrientes) |

- **124** países / agrupaciones regionales
- **25** indicadores distintos de deuda externa (desembolsos, intereses, deuda bilateral/multilateral, etc.)
- Sin valores nulos

### 🛠️ Herramientas y tecnologías

- **Python**: `pandas`, `sqlite3`, `matplotlib`, `seaborn`
- **SQL**: consultas de agregación (`GROUP BY`, `SUM`, `AVG`, `MAX`, subconsultas/joins)
- **Jupyter Notebook** como entorno de trabajo

### 🔍 Metodología

1. Carga del archivo CSV con `pandas` desde `data/international_debt.csv`
2. Creación de una base de datos SQLite (`data/international_debt.db`) a partir del DataFrame
3. **Limpieza de datos**: separación de países individuales vs. agregados regionales del Banco Mundial (*South Asia*, *IDA only*, *Least developed countries*), que de otra forma distorsionan los rankings por país
4. Consultas SQL directamente sobre la base de datos para responder preguntas analíticas
5. Visualizaciones con `matplotlib` / `seaborn`
6. Interpretación de resultados en cada paso (notebook bilingüe ES/EN)

### ❓ Preguntas respondidas

**Básicas:**
1. ¿Qué países tienen la mayor deuda total registrada?
2. ¿Cuál es el promedio de deuda por tipo de indicador?
3. ¿Qué país tiene la mayor deuda para cada tipo de indicador?

**Profundizando el análisis:**
4. ¿Qué porcentaje de la deuda global concentran los países más endeudados?
5. ¿Los países más endeudados dependen más de acreedores bilaterales o multilaterales?
6. ¿Qué países pagan más en servicio de deuda de lo que reciben en nuevos desembolsos (ratio de riesgo)?
7. ¿Qué tan correlacionados están entre sí los distintos tipos de deuda?

### 📈 Hallazgos principales

- La deuda total registrada en el dataset (solo países individuales) ronda los **2.9 billones de USD**.
- **China** y **Brasil** encabezan la lista de mayor deuda acumulada, seguidos de Rusia, Turquía, India, México e Indonesia. Los top 10 países concentran cerca del **62% de la deuda global** del dataset.
- La mezcla de deuda **bilateral vs. multilateral** varía bastante entre los países más endeudados, lo que sugiere distintas estrategias de financiamiento.
- **Rusia** destaca con un ratio extremo de servicio de deuda (~2,440x): pagó cerca de $80B en principal + intereses mientras recibió apenas ~$33M en nuevos desembolsos de largo plazo.
- Los distintos tipos de deuda están, en general, altamente correlacionados entre países (refleja principalmente el tamaño económico de cada uno).

---

## English

Exploratory analysis of external debt data across different countries, using **Python (pandas)** and **SQL (SQLite)** to answer business questions about global debt levels.

### 🎯 Objective

Explore an international debt dataset to identify which countries carry the most debt, which debt types are largest on average, and which country leads each debt category.

### 🗂️ Dataset

The dataset (`data/international_debt.csv`) contains **2,357 records** with the following columns:

| Column | Description |
|---|---|
| `country_name` | Country or region name |
| `country_code` | ISO country code |
| `indicator_name` | Debt indicator name |
| `indicator_code` | Indicator code |
| `debt` | Debt amount (in current US$) |

- **124** countries / regional groupings
- **25** distinct external debt indicators (disbursements, interest, bilateral/multilateral debt, etc.)
- No null values

### 🛠️ Tools & technologies

- **Python**: `pandas`, `sqlite3`, `matplotlib`, `seaborn`
- **SQL**: aggregate queries (`GROUP BY`, `SUM`, `AVG`, `MAX`, subqueries/joins)
- **Jupyter Notebook** as the working environment

### 🔍 Methodology

1. Load the CSV file with `pandas` from `data/international_debt.csv`
2. Create a SQLite database (`data/international_debt.db`) from the DataFrame
3. **Data cleaning**: separate individual countries from World Bank regional aggregates (*South Asia*, *IDA only*, *Least developed countries*), which would otherwise distort the per-country rankings
4. Run SQL queries directly against the database to answer the analytical questions
5. Visualizations with `matplotlib` / `seaborn`
6. Interpretation of results at each step (bilingual ES/EN notebook)

### ❓ Questions answered

**Basic:**
1. Which countries have the highest total recorded debt?
2. What is the average debt by indicator type?
3. Which country has the highest debt for each indicator type?

**Going deeper:**
4. What percentage of global debt do the most indebted countries hold?
5. Do the most indebted countries rely more on bilateral or multilateral creditors?
6. Which countries pay more in debt service than they receive in new disbursements (risk ratio)?
7. How correlated are the different debt types with one another?

### 📈 Key findings

- Total recorded debt in the dataset (individual countries only) is around **US$2.9 trillion**.
- **China** and **Brazil** top the list of accumulated debt, followed by Russia, Turkey, India, Mexico, and Indonesia. The top 10 countries hold close to **62% of the dataset's global debt**.
- The **bilateral vs. multilateral** debt mix varies quite a bit among the most indebted countries, suggesting different financing strategies.
- **Russia** stands out with an extreme debt service ratio (~2,440x): it paid close to $80B in principal + interest while receiving only ~$33M in new long-term disbursements.
- Debt types are, overall, highly correlated across countries (mostly reflecting each country's economic size).
