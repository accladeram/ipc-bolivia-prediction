# Predicción del IPC en Bolivia usando Modelos Econométricos y de Machine Learning

### 📌 Descripción

Este proyecto corresponde a mi monografía final del diplomado en *Machine Learning aplicado a Econometría*, cuyo objetivo fue desarrollar un sistema de predicción del Índice de Precios al Consumidor (IPC) en Bolivia utilizando modelos tradicionales y de aprendizaje automático.

El enfoque se centra en comparar la precisión y estabilidad de diferentes enfoques univariados y multivariados, con especial énfasis en la implementación de métodos como Prophet, SVR, Random Forest y ARIMA, aplicados en esquemas de predicción multi-horizonte.

(El objetivo de esta investigación es comparar la precisión de distintos modelos para predecir el Índice de Precios al Consumidor (IPC) en Bolivia, utilizando tanto técnicas econométricas tradicionales (ARIMA/SARIMA) como modelos de Machine Learning (Random Forest, Prophet).)

---

### 🗃️ Dataset

* **Fuente:** Datos del INE Bolivia, Banco Central de Bolivia y simulaciones propias.
* **Cobertura temporal:** Enero 2007 – Febrero 2025
* **Frecuencia:** Mensual
* **Variables incluidas:**

  * IPC mensual e interanual
  * Tasas de interés activas y pasivas
  * Tipo de cambio
  * Importaciones, exportaciones
  * Variación de precios por sectores

> Nota: El dataset fue preprocesado y transformado con 12 rezagos para cada variable, generando un conjunto de entrenamiento para series temporales.

---

### 🛠️ Tecnologías utilizadas

| Herramienta             | Aplicación                              |
| ----------------------- | --------------------------------------- |
| **Python**              | Procesamiento de datos, modelos de ML   |
| `pandas`, `numpy`       | Manipulación de series temporales       |
| `scikit-learn`          | Modelos: SVR, Random Forest             |
| `statsmodels`           | Modelos: ARIMA, SARIMAX                 |
| `prophet`               | Predicción multihorizonte               |
| `matplotlib`, `seaborn` | Visualización de resultados             |
| `openpyxl` / `Excel`    | Exploración inicial y carga del dataset |
| `Jupyter Notebook`      | Desarrollo y explicación reproducible   |

---

### 📊 Modelos aplicados

| Modelo                                     | Enfoque                   | Comentario                                 |
| ------------------------------------------ | ------------------------- | ------------------------------------------ |
| **Prophet**                                | Univariado                | Modelo base para predicción multihorizonte |
| **ARIMA / SARIMAX**                        | Univariado y multivariado | Modelo econométrico de referencia          |
| **SVR (Regresión de Vectores de Soporte)** | ML supervisado            | Buen rendimiento en horizontes cortos      |
| **Random Forest Regressor**                | Ensamble ML               | Mayor estabilidad a largo plazo            |

Cada modelo fue entrenado y evaluado bajo un **esquema rolling-origin** para varios horizontes de predicción (1, 3, 6 y 12 meses).

---

### 📈 Métricas de evaluación

Se aplicaron múltiples indicadores para evaluar la precisión y robustez:

* **RMSE (Root Mean Squared Error)**
* **Coeficiente de Theil (U)**
* **% de dirección correctamente predicha**
* **Prueba de Diebold-Mariano modificada** (Harvey et al., 1997)

Los resultados se interpretan comparando el desempeño relativo entre modelos para cada horizonte temporal.

---

### 📁 Estructura del repositorio

```bash
📦 ipc-bolivia-prediction
├── 📂 data/                # Dataset consolidado (anonimizado o ejemplo)
│   └── ConsolidadoFinal.xlsx
├── 📂 notebooks/
│   ├── Prophet_model.ipynb
│   ├── ARIMA_model.ipynb
│   ├── RandomForest_model.ipynb
│   └── SVR_model.ipynb
├── 📂 figures/             # Gráficos generados por cada modelo
├── 📂 metrics/             # Resultados en Excel o CSV
├── 📄 README.md
```

---

### 📁 Estructura del repositorio (mejorado)

```bash
ipc-prediction-bolivia/
│
├── 📂 data/
│   ├── 📂 raw/              # Datos originales sin procesar
│   ├── 📂 processed/        # Datos transformados y listos para análisis
│   └── 📂 external/         # Fuentes externas relevantes (opcional)
│
├── 📂 notebooks/
│   ├── 01_exploracion.ipynb      # Análisis exploratorio
│   ├── 02_modelos_ARIMA.ipynb    # Modelos econométricos
│   ├── 03_modelos_ML.ipynb       # Modelos ML: RF, Prophet, etc.
│   └── 04_evaluacion_modelos.ipynb # Comparación y métricas
│
├── 📂 src/
│   ├── utils.py                  # Funciones auxiliares
│   ├── preprocessing.py         # Transformación de datos
│   └── 📂 models/                  # Scripts de entrenamiento y evaluación
│       ├── arima.py
│       ├── prophet_model.py
│       └── random_forest.py
│
├── 📂 outputs/
│   ├── 📂 figures/                  # Gráficos y visualizaciones finales
│   └── 📂 results/                  # Predicciones y métricas
│
├── 📂 report/
│   └── monografia.pdf            # Tu documento final en PDF
│
├── 📄README.md
├── 📄requirements.txt             # Librerías necesarias
└── 📄LICENSE                      # CC BY 4.0 o la que elijas
```

---

### 🚀 Cómo ejecutar

1. Clona este repositorio:

```bash
git clone https://github.com/accladeram/ipc-bolivia-prediction.git
```

2. Instala las dependencias:

```bash
pip install pandas numpy matplotlib seaborn prophet scikit-learn statsmodels openpyxl
```

3. Ejecuta los notebooks en orden desde la carpeta `/notebooks`.

4. Los resultados (predicciones + errores) se guardarán en `/metrics` y los gráficos en `/figures`.

---

### 🎯 Conclusiones generales

* Modelos como Random Forest y SVR mostraron una mejor capacidad de generalización frente a Prophet y ARIMA para horizontes mayores a 6 meses.
* Prophet mostró gran robustez para horizontes cortos en un contexto altamente estacional.
* El uso de rezagos y variables macroeconómicas mejora significativamente la precisión predictiva.
* Las pruebas estadísticas refuerzan la validez de los modelos seleccionados frente a benchmarks naïve.

---

## 📜 Licencia

Este trabajo está bajo la Licencia Creative Commons Attribution 4.0 International (CC BY 4.0). Puedes compartir, adaptar y usar este trabajo con atribución.

---

### 👩‍💻 Autor

**Ana Carolina Cladera Melgar**
Diplomado en Machine Learning aplicado a Econometría

📫 \accladeram@gmail.com

🔗 \[LinkedIn] 
 
🔗 \[Portafolio completo]

---

