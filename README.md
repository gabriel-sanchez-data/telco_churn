# Customer Churn Prediction: Retención de Clientes con Machine Learning

El objetivo de este proyecto es predecir la fuga de clientes (Churn) en una empresa de telecomunicaciones para optimizar las campañas de retención. 

En lugar de utilizar métricas estándar de clasificación, el proyecto se centra en minimizar los falsos negativos, maximizando la detección de clientes en riesgo de abandono mediante la optimización de pesos en clases desbalanceadas.

**Metodología y Herramientas**
* **Limpieza y Preprocesamiento:** Pipelines de Scikit-Learn para imputación de nulos y codificación de variables (`OneHotEncoder`, `StandardScaler`), evitando el data leakage.
* **Modelado:** Entrenamiento y evaluación de Regresión Logística, SVM, Random Forest y XGBoost. 
* **Optimización:** Ajuste de hiperparámetros con `GridSearchCV` y compensación de desbalanceo (`scale_pos_weight`). El modelo ganador (XGBoost) logró incrementar la tasa de detección del churn del 52% al 80%.
* **Explicabilidad:** Uso de SHAP values para interpretar las decisiones del modelo y extraer *insights* de negocio.

**Insights de Negocio Destacados**
1. **Riesgo inicial:** Los clientes con menor antigüedad (*tenure*) presentan el mayor riesgo de fuga.
2. **Impacto del contrato:** Los contratos anuales y bianuales reducen drásticamente la probabilidad de abandono.
3. **Sorpresas en el servicio:** Curiosamente, los usuarios con servicio de fibra óptica y facturas mensuales altas muestran una mayor propensión al churn, lo que sugiere la necesidad de revisar la calidad o el precio de este servicio.

**Cómo reproducir este proyecto**
1. Clona este repositorio.
2. Instala las dependencias ejecutando `pip install -r requirements.txt`.
3. Ejecuta el notebook. La primera celda descargará automáticamente el dataset de Kaggle en una carpeta local `/data`.
