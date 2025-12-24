# 🏙️ Boston Housing Prices

El objetivo del proyecto es **predecir el valor medio de las viviendas en Boston**, en función de características socioeconómicas, ambientales y estructurales de los barrios.

---

## 📊 Dataset

📦 Fuente: [Boston Housing Dataset – UCI Machine Learning Repository / scikit-learn]  
El dataset contiene información de **506 observaciones** y **14 variables**, ampliamente utilizado en problemas de regresión.

**Variables principales:**
- `crim` → Tasa de criminalidad por distrito  
- `zn` → Porcentaje de zonas residenciales  
- `indus` → Porcentaje de áreas industriales  
- `chas` → 1 si el distrito bordea el río Charles  
- `nox` → Concentración de óxidos nítricos (contaminación)  
- `rm` → Promedio de habitaciones por vivienda  
- `age` → Porcentaje de viviendas construidas antes de 1940  
- `dis` → Distancia media a los centros de empleo  
- `rad` → Accesibilidad a autopistas radiales  
- `tax` → Tasa de impuesto a la propiedad  
- `ptratio` → Ratio de alumnos por profesor  
- `black` → Proporción de población afroamericana  
- `lstat` → Porcentaje de población con bajo estatus socioeconómico  
- `medv` → Valor medio de la vivienda (variable objetivo)

---

## 🧹 Limpieza de datos

- ✅ **Sin valores faltantes (NAs)**  
- ⚠️ **Algunos outliers** detectados en `crim`, `rm` y `lstat`, tratados mediante winsorización.  
- Se normalizaron variables numéricas y se eliminaron correlaciones redundantes antes del modelado.

---

## 🔍 Insights Principales

- 🏭 **Zonas industriales**, alta **tasa de criminalidad**, mayor **contaminación (nox)**, alto porcentaje de **población de bajo estatus (`lstat`)** o mayor **ratio estudiante/profesor (`ptratio`)** → **menores precios** de vivienda.
<img width="1347" height="693" alt="Captura de pantalla 2025-11-12 162917" src="https://github.com/user-attachments/assets/201b12ff-c2f5-4edc-827d-ce12dd7a97c4" />
- 🏡 Áreas con **más habitaciones (`rm`)** o **mayor proporción de zonas residenciales (`zn`)** → **valores más altos**.
<img width="1355" height="693" alt="Captura de pantalla 2025-11-12 163504" src="https://github.com/user-attachments/assets/43a2d205-4849-42f0-a551-89a3f0976be0" />

- 🌊 Viviendas que **bordean el río Charles (`chas = 1`)** son **significativamente más caras**.
<img width="1347" height="656" alt="Captura de pantalla 2025-11-12 160847" src="https://github.com/user-attachments/assets/bd926b92-6bd3-4b10-9c62-b3f4cc5b5da9" />

- 💡 Las variables con mayor impacto sobre el precio son: `lstat`, `rm`, `ptratio` y `nox`.

---

## 🤖 Modelado Predictivo

Se implementaron distintos modelos de regresión y data mining para estimar el valor medio de las viviendas (`medv`).
                      RMSE       MAE        R2     MAPE

             XGBoost 2.966036 2.078375 0.8947201 10.53740
       Random Forest 3.231569 2.208940 0.8729431 11.19965
            LightGBM 3.144446 2.148696 0.8799075 10.83539
  Regresión Múltiple 4.792320 3.348142 0.7225754 16.82101
 


 
El modelo xgboost es el mejor ya que sus métricas de error son las menores. Su error de predicción es de 10,% y el modelo es capaz de explicar 89,5% de la variabilidad.
---

## 🧰 Tecnologías utilizadas

- **Lenguaje:** Python  
- **Bibliotecas:** `pandas`, `numpy`, `matplotlib`, `seaborn`, `scikit-learn`, `xgboost`  
- **Técnicas:**  
  - Análisis de correlaciones  
  - Feature scaling y selección de variables  
  - Evaluación mediante RMSE, MAE y R²  
  - Optimización de hiperparámetros  
  - Validación cruzada  

---





  

