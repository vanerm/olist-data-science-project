![Olist Data Science Project Cover](assets/images/cover_image.png)

🛍️ Análisis de Satisfacción de Clientes – Olist Marketplace

## 📄 Descripción del Proyecto
Este proyecto analiza el comportamiento de los clientes y las entregas en el marketplace **Olist**, con el objetivo de identificar los factores que más influyen en la **satisfacción del cliente** y el cumplimiento de entregas.  

El análisis incluye:  
- 📊 **Análisis Exploratorio de Datos (EDA)**  
- 🚚 **Evaluación de tiempos de entrega y retrasos**  
- 💬 **Análisis de satisfacción del cliente (reviews y puntuaciones)**  
- 🧠 **Modelos de Machine Learning supervisados**  
  - Regresión Logística  
  - Random Forest  
  - XGBoost  
- 🔍 **Interpretabilidad del modelo** con técnicas de *Feature Importance* y *SHAP Values*  
- 🌎 **Visualizaciones geográficas** con mapas interactivos (Folium / Plotly)

---

## 🧩 Estructura del Notebook
1. **Carga de datos** desde archivos CSV y creación de base SQLite.  
2. **Integración de tablas** (órdenes, clientes, productos, envíos, reseñas).  
3. **Data Wrangling y limpieza de valores nulos.**  
4. **EDA:** análisis univariado, bivariado y multivariado (PCA y MANOVA).  
5. **Modelado predictivo:** entrenamiento, optimización y evaluación comparativa de modelos.  
6. **Interpretabilidad:** análisis de impacto de variables con SHAP.  
7. *(Etapa futura)* **Enriquecimiento con APIs externas** (clima, tránsito, sentimiento en reviews).  

---

## 🛠️ Tecnologías Utilizadas
- 🐍 **Python 3.9+**  
- 📦 **Pandas / NumPy** – Manipulación y análisis de datos  
- 📊 **Matplotlib / Seaborn / Plotly** – Visualizaciones  
- 🤖 **Scikit-learn / XGBoost** – Modelos de Machine Learning  
- 🌍 **Folium / GeoPandas** – Mapas interactivos y análisis espacial  
- 📈 **Statsmodels / SciPy** – Análisis estadístico (ANOVA, MANOVA, correlaciones)  
- 🔎 **SHAP** – Interpretabilidad de modelos  
- 🗄️ **SQLite3** – Base de datos relacional local  

---

## 📈 Próximos Pasos
- 🌦️ Enriquecimiento del dataset con **APIs de clima y tránsito** para analizar su relación con las demoras.  
- 💬 **Análisis de sentimiento** en reseñas de clientes utilizando modelos de lenguaje (*Hugging Face*).  
- 🚀 Optimización y despliegue de modelos en entorno reproducible.

---

## 📁 Estructura del Proyecto

```
├── notebooks/           # Jupyter notebooks
├── data/               # Datasets (no incluidos en repo)
├── src/                # Código fuente Python
├── results/            # Resultados y visualizaciones
└── README.md           # Este archivo
```

## 🚀 Instalación

```bash
# Clonar el repositorio
git clone https://github.com/vanerm/olist-data-science-project.git
cd olist-data-science-project

# Instalar dependencias
pip install -r requirements.txt
```

## 📊 Dataset

El proyecto utiliza el dataset público de [Olist Brazilian E-commerce](https://www.kaggle.com/olistbr/brazilian-ecommerce) disponible en Kaggle.

## 🔗 Conexión con Google Colab

Este repositorio está configurado para trabajar directamente con Google Colab.

**[🚀 Abrir en Google Colab](https://colab.research.google.com/drive/1sBmDUGT13lOsoGc8JseWFglr7zCNDdNk?usp=sharing)**

También puedes abrir el notebook directamente desde GitHub haciendo clic en el archivo `olist_data_science_project.ipynb` y seleccionando "Open in Colab".

## 📈 Resultados Principales

- [Los resultados del análisis se mostrarán aquí]

## 🤝 Contribución

Este es un proyecto educativo desarrollado como parte del curso de Data Science II en Coder House.

## 📄 Licencia

Este proyecto es de uso educativo.

## 👨‍💻 Autor

Desarrollado como parte de la materia de Data Science II de la Diplomatura de Data Science en [Coder House](https://www.coderhouse.com/).

## 👋 About Me

¡Hola! Soy **Vanesa Mizrahi**, desarrolladora mobile iOS y apasionada por los datos y el aprendizaje continuo.

### 🔗 Conecta conmigo
- **LinkedIn:** [Vanesa Mizrahi](https://www.linkedin.com/in/vanesamizrahi)

### 💡 Sobre este proyecto
Este proyecto fue desarrollado como parte de mi formación en **Data Science** en Coder House, donde aprendí a crear aplicaciones web completas con Django, desde la concepción hasta el despliegue.

¡Gracias por revisar mi trabajo! 🚀

