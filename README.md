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

| Modelo              | RMSE | MAE | R² | MAPE |
|---------------------|------|-----|----|------|
| XGBoost             | 2.97 | 2.08 | 0.895 | 10.54% |
| Random Forest       | 3.23 | 2.21 | 0.873 | 11.20% |
| LightGBM            | 3.14 | 2.15 | 0.880 | 10.84% |
| Regresión Múltiple  | 4.79 | 3.35 | 0.723 | 16.82% |


 
El modelo xgboost es el mejor ya que sus métricas de error son las menores. Su error de predicción promedio es de 10% y el modelo es capaz de explicar 89,5% de la variabilidad.
---
---

## 💼 Caso de Negocio

Pensemos en una inmobiliaria o fondo de inversión que tasa **500 propiedades al año** (valor promedio: **$350,000 USD**) usando un método tradicional como la regresión lineal, cuyo error promedio (MAPE) es del **16.82%** → un margen de equivocación de **$58,870 USD por propiedad**, o **$29.4 millones de dólares** de exposición al riesgo en el portafolio anual.

Al reemplazar ese enfoque por **XGBoost**, el error cae a **10.54%**, reduciendo el margen de equivocación a **$36,890 USD por propiedad**. Escalado al portafolio completo, esto representa una **reducción del 37.3% en la exposición al riesgo de tasación**, equivalente a casi **$11 millones de dólares al año** en decisiones de compra, venta y crédito mejor fundamentadas.

| Métrica | Regresión Múltiple | XGBoost | Mejora |
|---|---|---|---|
| MAPE | 16.82% | 10.54% | -37.3% |
| Error por propiedad (USD) | $58,870 | $36,890 | -$21,980 |
| Exposición anual (500 propiedades) | $29.4M | $18.4M | **-$11.0M** |

Además, el modelo explica el **89.5% de la variabilidad** del precio (R²), confirmando que factores como `lstat`, `rm`, `ptratio` y `nox` —ya identificados en el análisis exploratorio— son los verdaderos motores del valor de una vivienda. No se trata de reemplazar el criterio humano, sino de darle una base cuantitativa sólida para tomar decisiones donde antes solo había estimaciones aproximadas.

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





  

