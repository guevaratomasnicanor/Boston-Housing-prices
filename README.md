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
- 🏡 Áreas con **más habitaciones (`rm`)** o **mayor proporción de zonas residenciales (`zn`)** → **valores más altos**.  
- 🌊 Viviendas que **bordean el río Charles (`chas = 1`)** son **significativamente más caras**.  
- 💡 Las variables con mayor impacto sobre el precio son: `lstat`, `rm`, `ptratio` y `nox`.

---

## 🤖 Modelado Predictivo

Se implementaron distintos modelos de regresión para estimar el valor medio de las viviendas (`medv`).

**Mejor modelo:** `XGBoost`

| Modelo | RMSE | MAE | R² |
|---------|------|-----|----|
| XGBoost | **2.93** | **2.07** | 0.88 |

Otros modelos probados: Linear Regression, Random Forest, LightGBM.

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

## 📈 Visualizaciones destacadas

- Heatmap de correlaciones  
- Distribución de `medv` (valor medio de vivienda)  
- Boxplots de `chas`, `rm`, `lstat` y `nox` vs `medv`  
- Gráfico de residuos del modelo  
- Feature importance de XGBoost  


  

