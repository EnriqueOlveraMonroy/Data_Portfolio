# Ejercicio: Predicción de Riesgo Crediticio con Árbol de Decisión

## ES

### Descripción
Este repositorio contiene un ejercicio de **credit-default-decision-tree** (impago) de clientes, usando un árbol de decisión (`DecisionTreeClassifier` de scikit-learn).

El objetivo del modelo es predecir, para cada solicitante, si va a caer en default:

- **1** = el cliente hará default (no pagará o se atrasará más de 28 días en sus pagos)
- **0** = el cliente NO hará default (pagará a tiempo)

> **Nota:** el notebook ahora carga los CSV desde la carpeta `data/` (`data/Train_Data.csv` y `data/Test_Data.csv`). Si mueves los archivos, actualiza las rutas en las celdas de carga de datos.

### Flujo del notebook
1. **Carga de datos**: se leen `Train_Data.csv` y `Test_Data.csv`.
2. **Análisis exploratorio**: `describe()`, `info()` y conteo de nulos por columna.
3. **Limpieza de datos**: los valores nulos en `edad`, `emailScore` y `NUMTDC_AV` se imputan con la **moda** de cada columna. La columna `browser` se elimina por no considerarse relevante y por tener muchos valores nulos.
4. **Preparación para el modelo**: se elimina la columna `ID` (y `label` en train, guardándola como variable objetivo `y`), y se codifican las columnas categóricas (`genero`, `nivelEstudio`) con `LabelEncoder`.
5. **Entrenamiento**: se entrena un `DecisionTreeClassifier` con los datos de entrenamiento.
6. **Predicción**: se generan predicciones sobre el set de prueba y se prueba el modelo con una muestra aleatoria.
7. **Interpretación**: se grafica el árbol de decisión y se calcula la importancia de cada variable (`feature_importances_`).
8. **Exportación**: se arma un DataFrame con `ID` y `resultado` (predicción) listo para exportarse a CSV (la línea de exportación está comentada en el notebook).

### Resultados principales
Según `feature_importances_` del árbol entrenado, las variables más influyentes en la predicción son:

| Variable | Importancia |
|---|---|
| score | ~18.8% |
| montoOtorgado | ~16.3% |
| gastosMensuales | ~12.2% |
| edad | ~11.6% |
| ingresosMensuales | ~11.6% |
| montoSolicitado | ~11.3% |
| nivelEstudio | ~5.5% |
| emailScore | ~4.5% |
| dependientesEconomicos | ~2.5% |
| quincenal | ~2.0% |
| genero | ~0.3% |

`score`, `montoOtorgado` y `gastosMensuales` concentran la mayor parte del peso del modelo, por lo que serían las variables clave a monitorear/priorizar si el modelo se pusiera en producción.

### Limitaciones / próximos pasos (sugeridos)
- El notebook no calcula métricas de evaluación (accuracy, precisión, recall, matriz de confusión) porque el set de prueba (`Test_Data.csv`) no incluye la etiqueta real (`label`). Para validar el modelo de forma más rigurosa se recomienda hacer una separación train/validation dentro del propio `Train_Data.csv` (`train_test_split`).
- No hay control de sobreajuste (poda del árbol, `max_depth`, validación cruzada).
- Los valores nulos se imputan con la moda; podría explorarse otras estrategias (mediana, imputación por grupo, modelos más robustos a NaN).

---

## EN

### Description
This repository contains a **credit-default-decision-tree** for loan/credit applicants, using a decision tree (`DecisionTreeClassifier` from scikit-learn).

The goal is to predict, for each applicant, whether they will default:

- **1** = the client will default (will not pay, or will be more than 28 days late on payments)
- **0** = the client will NOT default (will always pay on time)


### Notebook flow
1. **Data loading**: reads `Train_Data.csv` and `Test_Data.csv`.
2. **Exploratory analysis**: `describe()`, `info()`, and null-value counts per column.
3. **Data cleaning**: missing values in `edad` (age), `emailScore`, and `NUMTDC_AV` are imputed with each column's **mode**. The `browser` column is dropped as not relevant and having many nulls.
4. **Model preparation**: drops `ID` (and `label` in the training set, saved as the target `y`), and encodes categorical columns (`genero`, `nivelEstudio`) with `LabelEncoder`.
5. **Training**: fits a `DecisionTreeClassifier` on the training data.
6. **Prediction**: generates predictions on the test set and sanity-checks the model on a random sample.
7. **Interpretation**: plots the decision tree and computes each feature's importance (`feature_importances_`).
8. **Export**: builds a DataFrame with `ID` and `resultado` (prediction) ready to export to CSV (the export line is commented out in the notebook).

### Key results
Based on the trained tree's `feature_importances_`, the most influential variables are:

| Feature | Importance |
|---|---|
| score | ~18.8% |
| montoOtorgado (amount granted) | ~16.3% |
| gastosMensuales (monthly expenses) | ~12.2% |
| edad (age) | ~11.6% |
| ingresosMensuales (monthly income) | ~11.6% |
| montoSolicitado (amount requested) | ~11.3% |
| nivelEstudio (education level) | ~5.5% |
| emailScore | ~4.5% |
| dependientesEconomicos (dependents) | ~2.5% |
| quincenal (biweekly pay) | ~2.0% |
| genero (gender) | ~0.3% |

`score`, `montoOtorgado`, and `gastosMensuales` account for most of the model's decision weight, making them the key variables to monitor/prioritize if the model were put into production.

### Limitations / suggested next steps
- The notebook does not compute evaluation metrics (accuracy, precision, recall, confusion matrix) because the test set (`Test_Data.csv`) has no ground-truth `label`. For a more rigorous validation, consider splitting `Train_Data.csv` itself into train/validation sets (`train_test_split`).
- No overfitting controls are applied (tree pruning, `max_depth`, cross-validation).
- Missing values are imputed with the mode; other strategies (median, group-wise imputation, or models more robust to NaNs) could be explored.
