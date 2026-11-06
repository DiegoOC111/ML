Inteligencia Musical y Predicción de Popularidad (Spotify Tracks)

Descripción del Problema de Negocio

En la industria musical actual, el éxito de una canción depende de múltiples factores acústicos, de contexto y de género. Para las discográficas, productores y artistas independientes, comprender qué características hacen que un track se vuelva "popular" es fundamental para optimizar la producción, dirigir las campañas de marketing y maximizar el retorno de inversión (ROI).

Este proyecto busca resolver la incertidumbre en el lanzamiento de nuevos sencillos mediante la aplicación de Machine Learning, identificando los atributos clave del éxito y prediciendo el nivel de popularidad de las canciones en Spotify.

Objetivos del Proyecto

Objetivo Principal: Desarrollar una solución analítica integral que permita predecir la popularidad de una canción y descubrir patrones subyacentes en el ecosistema musical.

Objetivos Específicos:

Implementar modelos de aprendizaje no supervisado para segmentar canciones con características acústicas similares.

Desarrollar modelos de regresión para estimar el score exacto de popularidad (0-100).

Desarrollar modelos de clasificación para predecir si una canción será un "Hit" (alta popularidad) o no.

Aplicar técnicas de ensamble y optimización de hiperparámetros para asegurar la robustez de las predicciones.

Definición de KPIs

Precisión de Clasificación (Hit / No Hit): Alcanzar un F1-Score general superior al 80% para balancear correctamente Precision y Recall.

Error de Estimación (Regresión): Minimizar el Error Absoluto Medio (MAE) y maximizar la varianza explicada (R^2) en la predicción del score de popularidad.

Identificación de Nichos: Agrupar el 100% del catálogo en clusters interpretables comercialmente (ej. "Música de fiesta", "Música relajante").

Fuentes de Datos

El proyecto utiliza el dataset Spotify_Tracks_Dataset.csv, el cual contiene información detallada sobre miles de canciones, incluyendo:

Metadatos: Nombre del track, artistas, álbum, género.

Atributos Acústicos: Danceability, Energy, Key, Loudness, Mode, Speechiness, Acousticness, Instrumentalness, Liveness, Valence, Tempo.

Target: Popularity (Variable objetivo principal).

Fases del Proyecto (Metodología CRISP-DM)

Fase 1: Comprensión y Análisis Exploratorio de los Datos (EDA)

Limpieza de datos nulos y tratamiento de valores atípicos (outliers).

Análisis de distribución de variables acústicas y de la variable objetivo (Popularity).

Análisis de correlación para identificar multicolinealidad.

Insights: Identificación de las primeras tendencias que relacionan la "energía" y "bailabilidad" con la popularidad.

Fase 2: Preparación y Transformación de Datos

Codificación de variables categóricas (One-Hot Encoding para géneros, Label Encoding).

Escalado y normalización de variables numéricas para algoritmos sensibles a distancias.

Reducción de dimensionalidad utilizando Análisis de Componentes Principales (PCA) para optimizar el rendimiento del clustering.

Fase 3: Modelamiento No Supervisado (Descubrimiento de Patrones)

Algoritmos utilizados: K-Means y DBSCAN.

Evaluación: Uso de métricas avanzadas como el Índice de Silueta, Davies-Bouldin y Calinski-Harabasz.

Resultado: Creación de "perfiles musicales" que agrupan canciones con comportamientos similares, útiles para sistemas de recomendación.

Fase 4: Modelamiento Supervisado (Regresión y Clasificación)

Regresión (Predicción de Score): Estimación continua del índice de popularidad.

Clasificación (Predicción de "Hit"): Transformación de la popularidad en una variable binaria/multiclase.

Modelos de Ensamble Aplicados: Se implementan 3 algoritmos de última generación para combatir el sobreajuste y mejorar la generalización:

Random Forest (Bagging)

XGBoost (Boosting)

LightGBM (Boosting)

Fase 5: Optimización y Validación Cruzada

Validación Cruzada (Cross-Validation): Implementación de K-Fold y Stratified K-Fold para garantizar que los modelos sean estables y no dependan de una sola partición de datos.

Tuning de Hiperparámetros: Búsqueda exhaustiva e inteligente utilizando GridSearchCV y RandomizedSearchCV de Scikit-Learn.

Interpretación: Estudios de ablación e importancia por permutación (Permutation Importance) para identificar las variables más determinantes.

Fase 6: Evaluación, Ética y Conclusiones

Análisis de Sesgos y Ética: Evaluación de posibles sesgos en los datos (ej. sobrerrepresentación de ciertos géneros comerciales como el Pop frente a géneros de nicho) y el impacto ético de utilizar estas predicciones para limitar la exposición de artistas emergentes.

Conclusiones de Negocio: Recomendaciones finales basadas en datos para que los productores musicales enfoquen sus recursos en atributos acústicos específicos que estadísticamente impulsan la popularidad.

Estructura del Repositorio

spotify_popularity_prediction/
|-- data/               # Datasets crudos y procesados
|-- notebooks/          # Jupyter Notebooks documentados con el código
|-- models/             # Modelos serializados (archivos .pkl)
|-- images/             # Gráficos generados en el EDA y métricas
|-- README.md           # Documentación principal del proyecto
|-- requirements.txt    # Dependencias de Python necesarias

Cómo Ejecutar este Proyecto

Clona este repositorio: git clone [url_del_repo]

Instala las dependencias: pip install -r requirements.txt

Ejecuta el notebook principal ubicado en la carpeta notebooks/ asegurándote de que el archivo Spotify_Tracks_Dataset.csv se encuentre en la carpeta data/.
