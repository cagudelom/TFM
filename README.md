# Máster universitario en Ciencia de datos (Data science)
## Trabajo Final de Master

Se realiza la entrega de 2 notebook:

# 1. Análisis transaccional POS y dimensionamiento de capacidad self-checkout 

Este notebook **01-pos-transactions-rebuild-full-modeling** contiene el desarrollo analítico y predictivo de un conjunto de datos de transacciones POS, orientado a estudiar el comportamiento operativo y económico de las transacciones, segmentar su complejidad, analizar la adopción del canal self-checkout y estimar la capacidad necesaria de equipos de autoservicio bajo distintos escenarios de demanda.

A partir de un dataset original de transacciones, se llevó a cabo un proceso de limpieza, exploración y enriquecimiento de variables mediante *feature engineering*. Entre las variables adicionales construidas se incluyen atributos temporales, ratios operativos, banderas de outliers, segmentaciones por cuantiles y agregados históricos por operador y workstation. Este proceso permitió ampliar significativamente el espacio explicativo y construir una base más robusta para los modelos supervisados.

Sobre esta base se desarrollaron varios ejercicios de modelado. En primer lugar, se construyeron modelos de regresión para predecir el **monto transaccional (`amount`)** y la **duración de la transacción (`transaction_duration_sec`)**, utilizando enfoques de **Linear Regression** y **Random Forest Regressor**. Posteriormente, se creó una variable de clasificación denominada `transaction_class` para segmentar las transacciones en niveles de complejidad relativa (`LOW`, `MEDIUM`, `HIGH`), y se entrenaron modelos de **Logistic Regression** y **Random Forest Classifier** para evaluar la capacidad de clasificación de esta nueva variable.

Adicionalmente, se reinterpretó la variable `workstationgroupid` para diferenciar entre **caja asistida** y **self-checkout**, construyendo una nueva variable objetivo (`channel_target`) orientada a modelar afinidad de canal. Este análisis permitió identificar qué características transaccionales están asociadas con el uso del autoservicio. Finalmente, se construyó un modelo específico para predecir la **duración de atención en self-checkout**, comparando **Linear Regression**, **Random Forest Regressor** y **Gradient Boosting Regressor**, siendo este último el mejor modelo en capacidad de generalización.


# 2. Análisis transaccional POS y dimensionamiento de capacidad self-checkout 

Este notebook **prediccion-dimensionamiento-kioskos-starbucks-ml** desarrolla un modelo de predicción y dimensionamiento de kioskos a partir de un dataset de órdenes de clientes. El objetivo es estimar cuántos kioskos se requieren para atender distintos escenarios de demanda: órdenes actuales del canal Kiosk, órdenes combinadas de Kiosk + In-Store Cashier, y un escenario donde todos los canales son atendidos como Kiosk.

El proceso incluye limpieza de datos, EDA, creación de variables temporales y operativas, análisis de carga por hora y construcción de modelos predictivos. Se entrenaron modelos de regresión para estimar el tiempo de atención (fulfillment_time_min) y la demanda horaria (total_orders), comparando técnicas como Linear Regression, Poisson Regressor, Random Forest Regressor y Gradient Boosting Regressor.


## Archivos que se incluyen

01-pos-transactions-rebuild-full-modeling.ipynb
01-pos-transactions-rebuild-full-modeling.html

prediccion-dimensionamiento-kioskos-starbucks-ml.ipynb
prediccion-dimensionamiento-kioskos-starbucks-ml.html
