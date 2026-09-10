# Credit Score Predictor

**EN** — Machine learning project that predicts bank customers' credit score using Linear Regression, K-Nearest Neighbors (KNN), and Decision Tree regressors.
**ES** — Proyecto de machine learning que predice el credit score de clientes bancarios utilizando Regresión Lineal, K-Nearest Neighbors (KNN) y Árbol de Decisión.

---


**EN** — The notebook reads the dataset from `data/credit_data.csv`. Make sure the CSV file is placed inside the `data/` folder before running the notebook.

**ES** — El notebook lee el dataset desde `data/credit_data.csv`. Asegúrate de colocar el archivo CSV dentro de la carpeta `data/` antes de ejecutar el notebook.

---

## 🎯 Goal / Objetivo

**EN** — Analyze bank customer data and build a machine learning model capable of accurately predicting the credit score (a value between 350 and 850) of future clients.

**ES** — Analizar los datos de clientes bancarios y construir un modelo de machine learning capaz de predecir con precisión el credit score (un valor entre 350 y 850) de futuros clientes.

---

## 📊 Dataset

**EN** — `credit_data.csv` contains **279,856 rows** and 12 columns describing bank customers:

| Column | Type | Description |
|---|---|---|
| `active_member` | binary | Whether the customer is currently an active bank member |
| `employment_profile` | categorical | Salaried, self-employed, freelancer, or unemployed |
| `gender` | categorical | Male, female, or other |
| `age` | numerical | Customer's age |
| `income` | numerical | Customer's income |
| `credit_history` | numerical | Customer's credit history score |
| `existing_loans` | numerical | Number of active loans |
| `loan_amount` | numerical | Total amount owed |
| `loan_tenure_months` | numerical | Months the customer has held debt |
| `LTV_ratio` | numerical | Loan-to-value ratio (loan amount vs. collateral value) |
| `profile_score` | numerical | Overall customer profile rating |
| `Credit_Score` | numerical (target) | Value between 350–850 indicating creditworthiness |

**ES** — `credit_data.csv` contiene **279,856 filas** y 12 columnas que describen a los clientes bancarios (ver tabla arriba con las mismas variables: miembro activo, perfil laboral, género, edad, ingreso, historial crediticio, préstamos existentes, monto del préstamo, duración del préstamo en meses, LTV ratio, profile score y Credit_Score como variable objetivo).

---

## 🔧 Methodology / Metodología

**EN**
1. **Data cleaning** — dropped 1 row with missing values; fixed data types (`active_member` → bool, `employment_profile`/`gender` → category, numeric columns → int).
2. **Exploratory Data Analysis (EDA)** — distribution plots (histograms, boxplots, violin plots, KDE) and correlation analysis for every variable against `Credit_Score`.
3. **Feature engineering** — One-Hot Encoding for `gender` and `employment_profile`; `StandardScaler` standardization for numerical features.
4. **Modeling** — 70/30 train-test split; three regression models trained and evaluated: Linear Regression, KNN (k=3), and Decision Tree.
5. **Evaluation** — MSE, RMSE, MAE, and R² for each model.

**ES**
1. **Limpieza de datos** — se eliminó 1 fila con valores faltantes; se corrigieron los tipos de datos (`active_member` → booleano, `employment_profile`/`gender` → categoría, columnas numéricas → entero).
2. **Análisis Exploratorio de Datos (EDA)** — gráficos de distribución (histogramas, boxplots, violin plots, KDE) y análisis de correlación de cada variable contra `Credit_Score`.
3. **Ingeniería de variables** — One-Hot Encoding para `gender` y `employment_profile`; estandarización con `StandardScaler` para las variables numéricas.
4. **Modelado** — división 70/30 entrenamiento-prueba; se entrenaron y evaluaron tres modelos de regresión: Regresión Lineal, KNN (k=3) y Árbol de Decisión.
5. **Evaluación** — MSE, RMSE, MAE y R² para cada modelo.

---

## 📈 Results / Resultados

| Model / Modelo | MSE | RMSE | MAE | R² |
|---|---|---|---|---|
| Linear Regression / Regresión Lineal | 258.40 | 16.07 | 13.72 | 0.9903 |
| KNN (k=3) | 1,265.41 | 35.57 | 27.03 | 0.9524 |
| **Decision Tree / Árbol de Decisión** | **52.37** | **7.24** | **2.08** | **0.9980** |

**EN** — All three models achieve strong performance (R² > 0.95), which suggests the engineered features (especially `profile_score` and `LTV_ratio`) are highly predictive of `Credit_Score`. The **Decision Tree** regressor obtained the best results across all metrics, followed by Linear Regression; KNN performed comparatively worse, likely due to its sensitivity to the high dimensionality after one-hot encoding.

**ES** — Los tres modelos logran un desempeño sólido (R² > 0.95), lo que sugiere que las variables construidas (especialmente `profile_score` y `LTV_ratio`) son altamente predictivas del `Credit_Score`. El **Árbol de Decisión** obtuvo los mejores resultados en todas las métricas, seguido de la Regresión Lineal; KNN tuvo un desempeño comparativamente menor, probablemente debido a su sensibilidad a la alta dimensionalidad tras el one-hot encoding.

> ⚠️ **EN** — Note: results may vary slightly between runs since `train_test_split` is not seeded with a fixed `random_state`.
> ⚠️ **ES** — Nota: los resultados pueden variar ligeramente entre ejecuciones ya que `train_test_split` no usa un `random_state` fijo.

---

