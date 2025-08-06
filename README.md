# 🏡 Predicción de Precios de Viviendas en Melbourne (Ejemplo del Libro "ML for Absolute Beginners")

Este proyecto es un script de Machine Learning en Python que implementa un modelo de regresión para predecir los precios de las viviendas en Melbourne, Australia. Este código es un ejemplo práctico extraído de la sección de Python del libro **"Machine Learning for Absolute Beginners"**, diseñado para ilustrar un pipeline completo de ML desde la preparación de datos hasta el entrenamiento y evaluación de un modelo.

## 📊 Dataset

El modelo se entrena y evalúa utilizando el archivo `Melbourne_housing_FULL.csv`. Este dataset contiene diversas características de propiedades residenciales, como el número de habitaciones, tipo de propiedad, tamaño del terreno, y, por supuesto, el precio.

## 🚀 Proceso del Modelo

El script sigue los pasos estándar de un pipeline de Machine Learning:

1.  **Carga de Datos**: El dataset `Melbourne_housing_FULL.csv` es cargado en un DataFrame de Pandas.
2.  **Preprocesamiento de Datos**:
    * Se eliminan columnas consideradas irrelevantes para la predicción (`Address`, `Method`, `Date`, `Postcode`, `Lattitude`, `Longtitude`, `Regionname`, `Propertycount`).
    * Se eliminan las filas que contienen valores nulos (`NaN`) en cualquier columna.
    * Se aplica *One-Hot Encoding* a las columnas categóricas (`Suburb`, `CouncilArea`, `Type`, `SellerG`) para convertirlas en un formato numérico adecuado para el modelo.
3.  **División de Datos**: El dataset se divide en conjuntos de entrenamiento (70%) y prueba (30%) para evaluar el rendimiento del modelo en datos no vistos.
4.  **Selección y Entrenamiento del Modelo**:
    * Se utiliza un modelo `GradientBoostingRegressor` de `scikit-learn`.
    * El modelo se configura con parámetros específicos (`n_estimators`, `learning_rate`, `max_depth`, `min_samples_split`, `min_samples_leaf`, `max_features`, `loss`) para optimizar su rendimiento.
    * El modelo se entrena con el conjunto de datos de entrenamiento.
5.  **Evaluación del Modelo**:
    * Se calcula el Error Absoluto Medio (MAE) tanto para el conjunto de entrenamiento como para el conjunto de prueba. Esto permite entender qué tan bien predice el modelo y si existe *overfitting*.

## 🐍 Librerías Utilizadas

* **pandas**: Para manipulación y análisis de datos.
* **scikit-learn**: Para preprocesamiento de datos, división de conjuntos y el algoritmo de Machine Learning (`ensemble.GradientBoostingRegressor`).

## ⚙️ Cómo Ejecutar el Script

1.  Asegúrate de tener Python instalado en tu sistema.
2.  Instala las librerías necesarias si aún no las tienes:
    ```bash
    pip install pandas scikit-learn
    ```
3.  Descarga el archivo `Melbourne_housing_FULL.csv` y asegúrate de que esté en el mismo directorio que el script de Python.
4.  Guarda el código proporcionado en un archivo llamado, por ejemplo, `predict_housing_prices.py`.
5.  Ejecuta el script desde tu terminal:
    ```bash
    python predict_housing_prices.py
    ```

## 📊 Salida del Script

El script imprimirá en la consola el Error Absoluto Medio (MAE) para el conjunto de entrenamiento y para el conjunto de prueba, así como la diferencia entre ambos, lo cual es un indicador clave del rendimiento del modelo.

## 🧑‍💻 Autor

[Christian Vizcardo]
[www.linkedin.com/in/christian-vizcardo]