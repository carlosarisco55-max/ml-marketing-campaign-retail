# 🛒 ML Marketing Campaign — Retail Customer Response Prediction

![Python](https://img.shields.io/badge/Python-3.10-blue?logo=python)
![Scikit-learn](https://img.shields.io/badge/Scikit--learn-ML-orange?logo=scikit-learn)
![Google Colab](https://img.shields.io/badge/Google%20Colab-Notebook-yellow?logo=googlecolab)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen)

## 📌 Descripción del proyecto

Proyecto de **Machine Learning supervisado** desarrollado como práctica del Máster en Marketing Digital e IA en **INESDI Business Tech School**.

El objetivo es predecir qué clientes de una cadena retail responderán a la próxima campaña de marketing, permitiendo al equipo comercial focalizar sus esfuerzos en los clientes con mayor probabilidad de conversión.

## 🎯 Problema de negocio

Una empresa retail lanza campañas de marketing a toda su base de clientes (2.240 clientes) sin saber de antemano quién va a responder. Esto genera:

- **Gasto innecesario** en clientes que no van a responder
- **Pérdida de oportunidades** al no priorizar los clientes con mayor probabilidad
- **Solo el 14.9% de los clientes** responde a las campañas (dataset desbalanceado)

**Solución:** Construir un modelo predictivo que, con datos históricos de Enero y Febrero, prediga la probabilidad de respuesta de cada cliente en Marzo.

## 📊 Dataset

| Fichero | Descripción | Filas | Etiquetado |
|---------|-------------|-------|------------|
| `Enero.xlsx` | Datos históricos de entrenamiento | 2.240 | ✅ Sí (`Response`) |
| `Febrero.xlsx` | Datos de validación | 2.240 | ✅ Sí (`Response`) |
| `Marzo.xlsx` | Datos de predicción final | 2.240 | ❌ No |

**Variable target:** `Response` (1 = respondió a la campaña, 0 = no respondió)

**Features principales:** Income, MntWines, MntMeatProducts, NumWebPurchases, NumStorePurchases, AcceptedCmp1-5, Recency, Education, Marital_Status, Kidhome, Teenhome...

## 🤖 Modelos entrenados y comparados

| Modelo | Descripción |
|--------|-------------|
| **Random Forest** | Conjunto de árboles de decisión — modelo principal |
| **Logistic Regression** | Modelo lineal para clasificación binaria |
| **Decision Tree** | Árbol de decisión interpretable |
| **KNN** | Clasificación por vecinos más cercanos |

## 🔄 Flujo del proyecto

ENERO   → Preprocesar → Entrenar 4 modelos → Evaluar → Guardar mejor modelo
FEBRERO → Preprocesar → Validar modelo → Comprobar que generaliza bien
MARZO   → Preprocesar → Predecir → Probabilidad de respuesta por cliente 🎯

## ⚙️ Preprocesado aplicado

1. Eliminación de columnas irrelevantes (`Client ID`, `Dt_Customer`)
2. Tratamiento de valores nulos en `Income` (imputación por media)
3. One-Hot Encoding de variables categóricas (`Education`, `Marital_Status`)
4. Escalado con `StandardScaler`
5. División Train/Test 70%/30%

## 📈 Output final

El modelo genera un fichero `Predicciones_Marzo.xlsx` con:

| Client ID | Prediccion | Probabilidad_Respuesta_% |
|-----------|------------|--------------------------|
| 5524 | 1 | 87.3% |
| 2174 | 0 | 12.1% |
| ... | ... | ... |

El equipo de marketing puede ordenar la tabla por probabilidad y contactar primero a los clientes con mayor score.

## 🛠️ Tecnologías utilizadas

- **Python 3.10**
- **Pandas** — manipulación de datos
- **Scikit-learn** — modelos de ML y métricas
- **Matplotlib** — visualización
- **Joblib** — serialización del modelo
- **Google Colab** — entorno de ejecución

## 🚀 Cómo ejecutar el proyecto

1. Abre el notebook en Google Colab:
   [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/carlosarisco55-max/ml-marketing-campaign-retail/blob/main/CopyColabRetailhecho.ipynb)

2. Sube los 3 ficheros Excel cuando el notebook lo solicite

3. Ejecuta las celdas en orden (0 → 12)

4. Al finalizar, descarga `Predicciones_Marzo.xlsx`

## 👤 Autor

**Carlos García-Arisco**
Máster en Marketing Digital e IA — INESDI Business Tech School (Grupo Planeta)
[LinkedIn](www.linkedin.com/in/carlos-garcia-arisco-vilchez-yourbestchoice) 
[GitHub](https://github.com/carlosarisco55-max)

## 📚 Contexto académico

Práctica desarrollada en el módulo de **Machine Learning aplicado al Marketing** del Máster en Marketing Digital e IA de INESDI, bajo la metodología de aprendizaje supervisado con datasets reales de campañas retail.
