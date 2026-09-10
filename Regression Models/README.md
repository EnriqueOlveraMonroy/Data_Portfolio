# ⚽ Football Player Rating Prediction using Regression Models

*Español más abajo / Spanish version below*

---

## English

Final project for the Data Science Diploma Program at Instituto Artek, by **Enrique Olvera Monroy**.
The project builds and compares several regression models to predict a football player's **overall rating** from their physical and technical attributes.

### 🧠 Objective

Predict a player's **overall rating** from a set of physical and technical features, and identify which features matter most for that prediction.

### 📊 Dataset

The data comes from the [Kaggle Soccer Player Dataset](https://www.kaggle.com/datasets/hugomathien/soccer):

- **11,060 rows**
- **25 features** (after preprocessing)
- Extracted from a relational database with a SQL query joining the `Player` and `Player_Attributes` tables (see the query at the start of the notebook)
- Cleaned and engineered: missing-value imputation, an `Age` feature computed from `birthday`, and encoding of categorical variables (Label Encoding + One Hot Encoding)

### ⚙️ Tools & Technologies

- **Python** 🐍
- **Jupyter Notebook**
- **Scikit-learn** for preprocessing and model training
- **Pandas / NumPy** for data wrangling
- **Matplotlib** for visualization

### 🛠️ Modeling Steps

1. Load the data and inspect it (`df.info()`, missing values)
2. Feature engineering — compute `Age` from `birthday`
3. Clean invalid category values and impute missing values (most frequent / median / mean strategies)
4. Encode categorical variables (Label Encoder for `preferred_foot`, One Hot Encoder for the work-rate columns)
5. Split the data 75% train / 25% test
6. Scale features with `StandardScaler`
7. Train four regression models: **KNN**, **Linear Regression**, **Support Vector Regression (SVR)**, and **Decision Tree**
8. Evaluate every model with **R², Mean Squared Error, and Max Error**
9. Inspect feature importance from the Decision Tree

### 📈 Key Results

Comparing the R² score of the four models, **KNN** (K-Nearest Neighbors, n=5) gave the best result on the test set, ahead of Linear Regression, Decision Tree, and SVR.

The feature-importance analysis (from the Decision Tree) showed the three most influential attributes for predicting overall rating are:

- **Agility**
- **Weight**
- **Ball Control**


## Español

Proyecto final del Diplomado en Data Science del Instituto Artek, por **Enrique Olvera Monroy**.
El proyecto construye y compara varios modelos de regresión para predecir la **calificación general** de un jugador de fútbol a partir de sus atributos físicos y técnicos.

### 🧠 Objetivo

Predecir la **calificación general** de un jugador a partir de un conjunto de características físicas y técnicas, e identificar cuáles de ellas tienen mayor peso en dicha predicción.

### 📊 Conjunto de Datos

Los datos provienen del [Soccer Player Dataset de Kaggle](https://www.kaggle.com/datasets/hugomathien/soccer):

- **11,060 filas**
- **25 características** (después del preprocesamiento)
- Extraídos de una base de datos relacional mediante una consulta SQL que une las tablas `Player` y `Player_Attributes` (ver la consulta al inicio del notebook)
- Se realizó limpieza y creación de variables: imputación de valores faltantes, una característica `Age` calculada a partir de `birthday`, y codificación de variables categóricas (Label Encoding + One Hot Encoding)

### ⚙️ Herramientas y Tecnologías

- **Python** 🐍
- **Jupyter Notebook**
- **Scikit-learn** para el preprocesamiento y entrenamiento de modelos
- **Pandas / NumPy** para el manejo de datos
- **Matplotlib** para visualización

### 🛠️ Pasos del Modelado

1. Cargar los datos e inspeccionarlos (`df.info()`, valores faltantes)
2. Ingeniería de características — calcular `Age` a partir de `birthday`
3. Limpiar valores de categoría inválidos e imputar valores faltantes (estrategias de valor más frecuente / mediana / media)
4. Codificar variables categóricas (Label Encoder para `preferred_foot`, One Hot Encoder para las columnas de ritmo de trabajo)
5. Dividir los datos en 75% entrenamiento / 25% prueba
6. Escalar las características con `StandardScaler`
7. Entrenar cuatro modelos de regresión: **KNN**, **Regresión Lineal**, **Regresión de Vectores de Soporte (SVR)** y **Árbol de Decisión**
8. Evaluar cada modelo con **R², Error Cuadrático Medio y Error Máximo**
9. Analizar la importancia de las características a partir del Árbol de Decisión

### 📈 Resultados Principales

Al comparar el puntaje R² de los cuatro modelos, **KNN** (K-Vecinos Más Cercanos, n=5) obtuvo el mejor resultado sobre el conjunto de prueba, por encima de Regresión Lineal, Árbol de Decisión y SVR.

El análisis de importancia de características (a partir del Árbol de Decisión) mostró que los tres atributos más influyentes para predecir la calificación general son:

- **Agilidad**
- **Peso**
- **Control de Balón**

![Presentación del proyecto](assets/Decision_Tree_Model_Presentation.gif)