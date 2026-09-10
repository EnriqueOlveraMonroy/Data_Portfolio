# 💳 Credit Card Transaction Fraud Detection

*[Read this in English](#-english) · [Leer en Español](#-español)*

---

## EN English

### Overview
A machine learning project that classifies whether a credit card transaction is fraudulent or not, using **Python**, **pandas**, **scikit-learn**, and **imbalanced-learn**.

### 📺 Video walkthrough
A video explaining the full code, step by step, is available here: **[https://youtu.be/oZICPr8ULyk](#)**

### 🎯 Objective
Build a classification model that identifies fraudulent transactions as accurately as possible, in a dataset where fraud is a rare event compared to legitimate transactions.

### 🗂️ Dataset
[CreditCardData](https://www.kaggle.com/datasets/anurag629/credit-card-fraud-transaction-data) — **100,000 transactions**, 16 columns, including transaction amount, time, card type, entry mode, merchant category, transaction/shipping/residence country, gender, age, bank, and whether the transaction was fraudulent.

- **92,805** legitimate transactions
- **7,195** fraudulent transactions (**~7.2%** of the dataset — a clearly imbalanced problem)

### 🛠️ Tools & techniques
- **Data cleaning**: handling missing values, fixing a typo in bank names, currency symbol removal, data type casting
- **Exploratory Data Analysis (EDA)**: transaction patterns by day/hour, card type, entry mode, merchant category, country, gender and age
- **Feature engineering**: one-hot encoding, `MinMaxScaler` normalization
- **Class imbalance handling**: `RandomOverSampler` and `RandomUnderSampler` (imbalanced-learn)
- **Models**: Logistic Regression and Decision Tree Classifier, each evaluated on unbalanced, oversampled, and undersampled data
- **Evaluation**: accuracy, F1 score, precision, recall, confusion matrices, and K-Fold cross-validation

### 📈 Key findings
- The dataset is highly imbalanced (~7% fraud), so training directly on unbalanced data produces a model with good accuracy but poor recall — it misses many real fraud cases.
- After balancing the data (oversampling / undersampling), all four metrics (accuracy, F1, precision, recall) improved substantially, generally landing around or above 93%.
- The **oversampled Decision Tree** was the best-performing model overall — the highest accuracy, precision, and recall among all models tested, making it the most reliable at correctly catching fraud cases while minimizing false negatives.



## 🇪🇸 Español

### Descripción general
Proyecto de machine learning que clasifica si una transacción con tarjeta de crédito es fraudulenta o no, utilizando **Python**, **pandas**, **scikit-learn** e **imbalanced-learn**.

### 📺 Video explicativo
Aquí encontrarás un video donde explico el código completo, paso a paso: **[https://youtu.be/oZICPr8ULyk](#)**

### 🎯 Objetivo
Construir un modelo de clasificación que identifique transacciones fraudulentas de la mejor manera posible, en un dataset donde el fraude es un evento poco frecuente comparado con las transacciones legítimas.

### 🗂️ Dataset
[CreditCardData](https://www.kaggle.com/datasets/anurag629/credit-card-fraud-transaction-data) — **100,000 transacciones**, 16 columnas, incluyendo monto, hora, tipo de tarjeta, método de entrada, categoría del comercio, país de transacción/envío/residencia, género, edad, banco, e indicador de fraude.

- **92,805** transacciones legítimas
- **7,195** transacciones fraudulentas (**~7.2%** del dataset — un problema claramente desbalanceado)

### 🛠️ Herramientas y técnicas
- **Limpieza de datos**: manejo de valores nulos, corrección de un typo en nombres de bancos, eliminación de símbolo de moneda, conversión de tipos de datos
- **Análisis exploratorio (EDA)**: patrones de transacción por día/hora, tipo de tarjeta, método de entrada, categoría de comercio, país, género y edad
- **Ingeniería de variables**: codificación one-hot, normalización con `MinMaxScaler`
- **Manejo de desbalance de clases**: `RandomOverSampler` y `RandomUnderSampler` (imbalanced-learn)
- **Modelos**: Regresión Logística y Árbol de Decisión, cada uno evaluado con datos sin balancear, con oversampling y con undersampling
- **Evaluación**: exactitud, F1 score, precisión, recall, matrices de confusión y validación cruzada K-Fold

### 📈 Hallazgos principales
- El dataset está muy desbalanceado (~7% fraude), por lo que entrenar directamente con datos sin balancear produce un modelo con buena exactitud pero baja sensibilidad — se le escapan muchos casos reales de fraude.
- Después de balancear los datos (oversampling / undersampling), las cuatro métricas (exactitud, F1, precisión, recall) mejoraron sustancialmente, ubicándose en general alrededor o por encima del 93%.
- El **Árbol de Decisión con oversampling** fue el modelo con mejor desempeño en general: la exactitud, precisión y sensibilidad más altas entre todos los modelos evaluados, lo que lo hace el más confiable para detectar correctamente los casos de fraude minimizando los falsos negativos.

