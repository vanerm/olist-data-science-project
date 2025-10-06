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

├── assets/ # Recursos gráficos y archivos de soporte (mapas, imágenes, etc.)
├── .gitignore # Exclusiones de archivos para Git
├── README.md # Descripción y documentación general del proyecto
├── olist_data_science_project.ipynb # Notebook principal con el análisis completo (EDA, PCA, ML, SHAP)
└── olist_data_science_project.py # Script en Python con las funciones principales y ejecución modular

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


> 💡 *Nota:* Los datasets originales no se incluyen en el repositorio por tamaño y políticas de privacidad.  
> Pueden descargarse desde el dataset público de [Olist Kaggle Dataset](https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce) disponible en Kaggle.


## 🔗 Conexión con Google Colab

Este repositorio está configurado para trabajar directamente con Google Colab.

**[🚀 Abrir en Google Colab](https://colab.research.google.com/drive/1sBmDUGT13lOsoGc8JseWFglr7zCNDdNk?usp=sharing)**

## 📦 Obtención de los datos desde Kaggle

Para ejecutar este proyecto es necesario descargar el dataset público de **Olist Brazilian E-Commerce** desde Kaggle.  
A continuación se detallan los pasos para generar la **API key**, configurarla en **Google Colab** y descargar los archivos de forma automática.

---

### 🔑 Paso 1. Generar la API Key en Kaggle

1. Iniciá sesión en tu cuenta de [Kaggle](https://www.kaggle.com/).  
2. Hacé clic en tu foto de perfil (esquina superior derecha) → **Account**.  
3. Desplazate hasta la sección **API**.  
4. Hacé clic en **Create New API Token**.  
5. Se descargará un archivo llamado **`kaggle.json`**, que contiene tus credenciales personales.

> ⚠️ **Importante:** No compartas este archivo ni lo subas a repositorios públicos. Contiene tu clave privada de acceso a la API de Kaggle.

---

### 💾 Paso 2. Subir la API Key a Google Colab

Ejecutá el siguiente bloque en tu notebook y seleccioná el archivo `kaggle.json` descargado:

```python
from google.colab import files
files.upload()  # seleccionar el archivo kaggle.json desde tu computadora
```

### 📁 Paso 3. Configurar la ruta para la CLI de Kaggle

Los siguientes comandos crean la carpeta correcta, mueven el archivo kaggle.json y le asignan permisos de lectura seguros:

```bash
!mkdir -p ~/.kaggle
!cp kaggle.json ~/.kaggle/
!chmod 600 ~/.kaggle/kaggle.json
```

### 📥 Paso 4. Descargar y descomprimir el dataset de Olist

Una vez configurado el acceso, descargá el dataset con los siguientes comandos:

```bash
!kaggle datasets download -d olistbr/brazilian-ecommerce -p /content
!unzip -o /content/brazilian-ecommerce.zip -d /content/olist_dataset
```

### 🔍 Paso 5. Verificar los archivos descargados

Para confirmar que los CSV fueron descargados correctamente, listá los primeros archivos del dataset:

```bash
!ls /content/olist_dataset | sed -n '1,20p'
```

Verás archivos como:

- olist_orders_dataset.csv
- olist_customers_dataset.csv
- olist_order_items_dataset.csv
- olist_products_dataset.csv
- olist_sellers_dataset.csv, entre otros.

### ✅ Resultado esperado

Al finalizar estos pasos, tendrás todos los archivos del dataset Olist Brazilian E-Commerce disponibles en tu entorno de trabajo (/content/olist_dataset), listos para ser utilizados en las siguientes etapas del análisis:

- Exploración y limpieza de datos (EDA)
- Análisis de comportamiento de clientes
- Modelado predictivo y evaluación de satisfacción
- Visualizaciones y dashboards


## 📈 Resultados Principales

- [Los resultados del análisis se mostrarán aquí]

## 🤝 Contribución

Este es un proyecto educativo desarrollado como parte del curso de Data Science II de la Diplomatura de Data Science en [Coder House](https://www.coderhouse.com/).

## 📄 Licencia

Este proyecto es de uso educativo.

## 👋 About Me

¡Hola! Soy **Vanesa Mizrahi**, desarrolladora mobile iOS y apasionada por los datos y el aprendizaje continuo.

### 🔗 Conecta conmigo
- **LinkedIn:** [Vanesa Mizrahi](https://www.linkedin.com/in/vanesamizrahi)

### 💡 Sobre este proyecto

Este proyecto fue desarrollado como parte del curso **Data Science II** de la carrera de **Data Science** en **CoderHouse**,  
donde se aplicaron técnicas avanzadas de análisis de datos, estadística multivariada y machine learning.  

El trabajo integra todas las etapas del proceso de ciencia de datos:
- Extracción y limpieza de datos desde fuentes públicas.  
- Análisis exploratorio (EDA) y visualización interactiva.  
- Formulación y validación de hipótesis estadísticas.  
- Construcción y evaluación de modelos supervisados.  
- Interpretación de resultados y conclusiones orientadas al negocio.  

El objetivo principal fue desarrollar una **solución analítica completa** basada en datos reales del marketplace **Olist**,  
capaz de explicar los factores que influyen en la **satisfacción del cliente** y predecir comportamientos a partir de variables logísticas y de compra.

¡Gracias por revisar mi trabajo! 🚀

