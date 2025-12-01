# 🛍️ Olist Marketplace – Data Science Project  
**EDA • Feature Engineering • Machine Learning • Logística • NLP • Geoanálisis**

![Olist Data Science Project Cover](assets/images/cover_image.png)

# 🔎 TL;DR 
Este proyecto analiza el marketplace **Olist** para identificar los factores que explican la **satisfacción del cliente** y los **retrasos logísticos**, integrando:

- Machine Learning supervisado  
- Google Maps API para distancias entre estados  
- Análisis de sentimiento (NLP) con HuggingFace  
- Feature engineering avanzado  
- Interpretabilidad del modelo (SHAP)

El objetivo final es construir una **solución analítica completa** que conecte logística, experiencia del cliente y comportamiento de compra.

---

# 🎯 Objetivo del Proyecto

Comprender **qué variables influyen en la satisfacción del cliente** y cómo se relacionan los tiempos de entrega, la distancia geográfica y el contenido emocional de las reseñas.

También se evalúa si la incorporación de **variables externas** (distancias entre estados + sentimiento) **mejora el rendimiento del modelo**.

---

# 📊 Pipeline General

Datos Olist → Limpieza → EDA → Feature Engineering
               ↓
   Google Maps API (distancias) + NLP (sentimientos)
               ↓
    Dataset enriquecido → Modelos (LR / RF / XGB)
               ↓
     Interpretabilidad (SHAP) → Conclusiones

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
- 🗺️ **Enriquecimiento geográfico** con Google Maps API para cálculo de distancias estado-estado
- 💭 **Análisis de sentimiento (NLP)** utilizando modelos de HuggingFace para procesar reseñas en portugués
- 📈 **Re-entrenamiento de modelos** con variables enriquecidas (geográficas + sentimiento)

---

## 🧩 Estructura del Notebook
1. **Carga de datos** desde archivos CSV y creación de base SQLite.  
2. **Integración de tablas** (órdenes, clientes, productos, envíos, reseñas).  
3. **Data Wrangling y limpieza de valores nulos.**  
4. **EDA:** análisis univariado, bivariado y multivariado (PCA y MANOVA).  
5. **Modelado predictivo:** entrenamiento, optimización y evaluación comparativa de modelos.  
6. **Enriquecimiento geográfico con Google Maps API:** cálculo de distancias y tiempos estimados entre estados (seller-customer) para análisis logístico regional.  
7. **Análisis de sentimiento (NLP):** procesamiento de reseñas con modelos de HuggingFace, generación de variables de polaridad emocional y visualización mediante nubes de palabras.  
8. **Integración de variables enriquecidas:** merge de distancias geográficas y sentimientos al dataset principal (`df_vista_base`) y EDA multivariable del dataset enriquecido.  
9. **Re-entrenamiento del modelo:** evaluación comparativa del modelo mejorado con variables externas (Google Maps + sentimiento) vs. modelo original.  

---

🏆 Resultados Principales (Resumen)

| Modelo              | F1 Score         | Comentario                        |
| ------------------- | ---------------- | --------------------------------- |
| Logistic Regression | ~0.88            | Modelo lineal fuerte              |
| Random Forest       | ~0.88            | Similar a LR, diferencias mínimas |
| XGBoost             | **~0.89**        | Mejor desempeño global            |
| Modelo enriquecido  | **+3–5% mejora** | Incluye distancia + sentimiento   |

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
- 🗺️ **Google Maps API** – Cálculo de distancias y tiempos de viaje entre estados  
- 🤗 **HuggingFace Transformers** – Modelos de NLP para análisis de sentimiento multilingüe  
- ☁️ **WordCloud** – Visualización de términos más frecuentes en reseñas  

---

## 📈 Próximos Pasos
- 🚚 **Incorporar datos reales de transporte:** tiempos reales por transportista, velocidad media por ruta, capacidad de carga, e incidencias por clima o feriados.  
- 🤖 **Modelos adicionales:** experimentar con LightGBM, CatBoost (excelente para datos categóricos) y redes neuronales ligeras (MLP).  
- 🗺️ **Profundizar análisis geográfico:** mapas de calor de retrasos por municipio y feature engineering con "densidad de pedidos por zona".  
- 💭 **Análisis de sentimiento ampliado:** implementar topic modeling (LDA o BERTopic) y clasificación de emociones (enojo, frustración, satisfacción).  
- 🚀 **Optimización y despliegue:** implementar pipelines automatizados para actualización periódica de datos enriquecidos y despliegue en entorno reproducible.

---

## 📁 Estructura del Proyecto

```

├── assets/ # Recursos gráficos y archivos de soporte (mapas, imágenes, etc.)
│   └── images/ # Imágenes del proyecto (cover, visualizaciones, etc.)
├── inputs/ # Archivos CSV procesados para uso en las secciones 6-9
│   ├── distancias_estados_google.csv # Distancias y tiempos entre estados (Google Maps API)
│   └── sentiment_reviews_olist.csv # Reseñas con análisis de sentimiento (HuggingFace)
├── .gitignore # Exclusiones de archivos para Git
├── README.md # Descripción y documentación general del proyecto
├── olist_data_science_project.ipynb # Notebook principal con el análisis completo (EDA, PCA, ML, SHAP, enriquecimiento geográfico, NLP)
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

### Datasets Originales

> 💡 *Nota:* Los datasets originales no se incluyen en el repositorio por tamaño y políticas de privacidad.  
> Pueden descargarse desde el dataset público de [Olist Kaggle Dataset](https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce) disponible en Kaggle.

### Datasets Procesados (inputs/)

El proyecto incluye archivos CSV procesados en la carpeta `inputs/` que contienen datos enriquecidos utilizados en las secciones 6-9:

- **`distancias_estados_google.csv`** (43 KB): Contiene distancias y tiempos estimados entre estados calculados mediante Google Maps API. Incluye coordenadas de estados, distancias en kilómetros y tiempos estimados en minutos.

- **`sentiment_reviews_olist.csv`** (6.7 MB): Contiene las reseñas de clientes procesadas con análisis de sentimiento utilizando modelos de HuggingFace. Incluye variables como `sentiment_label_raw`, `sentiment_score_raw`, `sentiment_stars` y `sentiment_polarity`.

> ✅ **Estos archivos pueden subirse a GitHub** ya que son datos procesados/derivados del análisis y no contienen información sensible. Sus tamaños están dentro de los límites permitidos por GitHub (archivos < 100MB no requieren Git LFS).


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
- Enriquecimiento geográfico con Google Maps API
- Análisis de sentimiento mediante NLP (HuggingFace)
- Integración de variables enriquecidas al dataset principal
- Re-entrenamiento y mejora de modelos predictivos
- Visualizaciones y dashboards interactivos


## 📈 Resultados del Proyecto

- [Notebook interactivo en Kaggle – Olist Marketplace – EDA, Feature Engineering & ML](https://www.kaggle.com/code/vanesamizrahi/olist-marketplace-eda-feature-engineering-ml) 
- [Análisis de satisfacción y logística del Marketplace Olist (presentación)](https://docs.google.com/presentation/d/1mDuVNark3nnoYhvbLiFD52rtzURoOvEXpSQduoCVmCA/edit?usp=sharing)

## 🤝 Contribución

Este es un proyecto educativo desarrollado como parte del curso de Data Science II de la Diplomatura de Data Science en [Coder House](https://www.coderhouse.com/).

## 📄 Licencia

Este proyecto es de uso educativo.

## 👋 About Me

Soy Vanesa Mizrahi, desarrolladora móvil iOS y analista de datos.
Me especializo en:

- iOS Mobile Developer
- Ciencia de Datos aplicada a negocio
- Modelos interpretables
- Integración con APIs externas

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
- Enriquecimiento de datos con APIs externas (Google Maps API para análisis geográfico).  
- Procesamiento de lenguaje natural (NLP) para análisis de sentimiento en reseñas.  
- Integración de múltiples fuentes de datos (estructurados, geográficos y textuales).  
- Mejora iterativa de modelos mediante incorporación de nuevas features enriquecidas.  
- Interpretación de resultados y conclusiones orientadas al negocio.  

El objetivo principal fue desarrollar una **solución analítica completa** basada en datos reales del marketplace **Olist**,  
capaz de explicar los factores que influyen en la **satisfacción del cliente** y predecir comportamientos a partir de variables logísticas y de compra.

¡Gracias por revisar mi trabajo! 🚀

