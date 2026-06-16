<div align="center">

# 🏡 Inversión VT Málaga

## Dashboard para análisis de vivienda turística en Málaga ciudad

---

**Proyecto de análisis de datos y visualización interactiva para identificar señales de oportunidad en el mercado de vivienda turística de Málaga ciudad.**

![Python](https://img.shields.io/badge/Python-3.12-blue?style=for-the-badge\&logo=python)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-150458?style=for-the-badge\&logo=pandas)
![Power BI](https://img.shields.io/badge/Power%20BI-Dashboard-F2C811?style=for-the-badge\&logo=powerbi)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebooks-F37626?style=for-the-badge\&logo=jupyter)
![Git](https://img.shields.io/badge/Git-Version%20Control-F05032?style=for-the-badge\&logo=git)

</div>

---

## ✨ Introducción

**Inversión VT Málaga** es un proyecto de análisis de datos orientado a una inversora privada interesada en estudiar posibles zonas de Málaga ciudad para invertir en vivienda turística.

El objetivo principal no es recomendar una compra concreta, sino construir una **herramienta de primera criba** que permita comparar distritos y tipos de vivienda a partir de señales visibles del mercado turístico en Airbnb.

El análisis se centra en variables como precio, ocupación estimada, ingresos brutos estimados, volumen de oferta, tipo de dormitorio, nivel de competencia y limitaciones del dato.

---

## 🎯 Objetivo del proyecto

El objetivo principal del proyecto es responder a la siguiente pregunta:

> **¿Qué distritos de Málaga ciudad presentan mejores señales para estudiar una inversión en vivienda turística?**

Para ello se ha construido un flujo completo de trabajo que incluye:

* Limpieza y preparación de datos.
* Análisis exploratorio.
* Creación de variables derivadas.
* Evaluación de ingresos, ocupación y competencia.
* Desarrollo de un dashboard interactivo en Power BI.
* Inclusión explícita de sesgos y limitaciones del análisis.
* Recomendación de priorización para una segunda fase de estudio.

---

## 🧭 Enfoque del análisis

El proyecto analiza la vivienda turística desde una perspectiva comparativa, utilizando señales de mercado visibles en el dataset.

Las principales dimensiones analizadas son:

* **Visión general del mercado**: número de alojamientos, precios medios, ocupación estimada e ingresos medios.
* **Ingresos por distrito**: comparación entre ingreso total estimado e ingreso medio por alojamiento.
* **Actividad y competencia**: relación entre volumen de oferta y ocupación media estimada.
* **Segmentación del producto**: análisis por tipo de dormitorio, eficiencia por plaza y precio noche.
* **Sesgos y limitaciones**: advertencias necesarias para interpretar los resultados correctamente.
* **Priorización de inversión**: identificación de una opción principal y varias zonas exploratorias.

---

## 📊 Dashboard interactivo

El proyecto incluye un dashboard desarrollado en **Power BI Desktop**.

Archivo principal:

```text
dashboard/dashboard_inversion_malaga.pbix
```

También se incluye una versión exportada en PDF:

```text
reports/dashboard_inversion_malaga.pdf
```

El dashboard está dividido en cinco páginas:

### 1. Visión general

Resumen ejecutivo del mercado turístico en Málaga ciudad.

Incluye indicadores principales como:

* Total de alojamientos analizados.
* Número de distritos.
* Precio medio por noche.
* Precio mediano por noche.
* Ocupación media estimada.
* Ingresos medios anuales.
* Ingresos medios mensuales.
* Reviews del último año.

---

### 2. Ingresos por distrito

Comparativa entre:

* Distribución de ingresos estimados totales por distrito.
* Ingresos medios anuales por alojamiento y distrito.

Esta página permite distinguir entre distritos con mucho volumen total y distritos con mayor ingreso medio por alojamiento.

---

### 3. Actividad y competencia

Análisis de dos señales clave:

* Concentración de alojamientos por distrito.
* Ocupación media estimada por distrito.

Esta página ayuda a diferenciar entre zonas con mucha oferta turística y zonas con mayor actividad estimada.

---

### 4. Segmentación del producto

Comparativa por tipo de dormitorio.

Incluye:

* Ingresos medios anuales por alojamiento.
* Ingresos anuales estimados por plaza.
* Ocupación media.
* Precio noche.
* Número de alojamientos por tipo de dormitorio.

Esta página permite ver que los alojamientos más grandes pueden generar más ingresos absolutos, mientras que los alojamientos de menor tamaño pueden mostrar mayor eficiencia por plaza.

---

### 5. Sesgos y limitaciones

Página dedicada a advertencias de interpretación.

Incluye limitaciones relacionadas con:

* Fuente de datos.
* Ingresos estimados.
* Ocupación estimada.
* Decisión de inversión.

El dashboard debe interpretarse como una herramienta de análisis comparativo, no como una recomendación directa de compra.

---

## 🗂️ Estructura del proyecto

```text
dashboard-inversion-malaga/
│
├── dashboard/
│   └── dashboard_inversion_malaga.pbix
│
├── data/
│   ├── raw/
│   │   └── listings.csv
│   │
│   └── processed/
│       ├── listings_malaga_processed.csv
│       └── resumen_distritos_malaga.csv
│
├── docs/
│   └── PDF Briefing.pdf
│
├── notebooks/
│   ├── 01_data_preparation_cleaning.ipynb
│   └── 02_exploratory_data_analysis.ipynb
│
├── reports/
│   ├── dashboard_inversion_malaga.pdf
│   └── informe_final_inversion_malaga.md
│
├── README.md
├── requirements.txt
└── .gitignore
```

---

## 🧹 Preparación de datos

El dataset original contenía información de alojamientos turísticos de Málaga procedente de Inside Airbnb.

Durante la preparación de datos se realizaron los siguientes procesos:

* Selección de columnas relevantes para el análisis.
* Renombrado de variables.
* Filtrado de viviendas completas.
* Conversión del precio a formato numérico.
* Tratamiento de valores nulos.
* Eliminación de valores extremos en precio.
* Creación de variables derivadas.
* Exportación de datasets limpios para análisis y dashboard.

El dataset original contenía **9.714 registros y 79 columnas**.
Tras la limpieza, el análisis se realizó sobre **7.598 viviendas completas**.

---

## 🧪 Variables derivadas principales

Durante el proceso de limpieza y análisis se generaron variables adicionales para enriquecer el estudio:

| Variable                       | Descripción                                            |
| ------------------------------ | ------------------------------------------------------ |
| `tipo_dormitorios`             | Agrupación de alojamientos según número de dormitorios |
| `ingresos_estimados_mensuales` | Estimación mensual a partir del ingreso anual          |
| `nivel_precio`                 | Clasificación del alojamiento según nivel de precio    |
| `nivel_competencia`            | Clasificación del distrito según volumen de oferta     |
| `total_alojamientos_distrito`  | Número de alojamientos por distrito                    |

---

## 📈 Principales indicadores

| Indicador                           |   Valor |
| ----------------------------------- | ------: |
| Alojamientos analizados             |   7.598 |
| Distritos analizados                |      11 |
| Precio medio por noche              |   135 € |
| Precio mediano por noche            |   106 € |
| Ocupación media estimada            |  21,5 % |
| Ingresos medios anuales estimados   | 9.143 € |
| Ingresos medios mensuales estimados |   762 € |
| Reviews último año                  | 101.142 |

---

## 🔎 Principales hallazgos

Algunas conclusiones destacadas del análisis son:

* **Centro** concentra la mayor parte de la oferta visible en Airbnb y también gran parte del ingreso estimado total.
* El peso del distrito Centro indica una zona con fuerte actividad turística, pero también con alta competencia.
* Algunos distritos con menor volumen de alojamientos muestran señales interesantes en ingresos medios u ocupación estimada.
* **Palma-Palmilla**, **Puerto de la Torre** y **Ciudad Jardin** aparecen como zonas exploratorias que merecen revisión adicional.
* Los alojamientos de **3 o más dormitorios** presentan mayores ingresos medios anuales.
* Los alojamientos de **1 dormitorio** muestran mayor eficiencia por plaza y mayor ocupación media estimada.
* Los alojamientos de **2 dormitorios** ofrecen una opción intermedia entre capacidad, ingresos y ocupación.
* La ocupación estimada y los ingresos deben interpretarse como señales aproximadas, no como reservas reales ni rentabilidad neta.

---

## 🧭 Recomendación de priorización

A partir de las señales analizadas, la recomendación no se plantea como una decisión directa de compra, sino como una **priorización para una segunda fase de estudio**.

### Opción principal

La opción principal sería estudiar viviendas turísticas de **1 o 2 dormitorios en el distrito Centro**.

Centro destaca por:

* Mayor volumen de oferta visible.
* Mayor concentración de ingresos estimados totales.
* Alta actividad turística.
* Mayor robustez de los datos al tener una muestra más amplia.

Sin embargo, también presenta una competencia elevada, por lo que no debe interpretarse como una decisión automática de inversión.

### Tipología recomendada

La tipología preferente sería:

* **1 dormitorio**, si se busca mayor eficiencia por plaza y ocupación.
* **2 dormitorios**, si se busca un equilibrio entre ingresos anuales, capacidad y ocupación.

Los alojamientos de **3 o más dormitorios** generan más ingresos absolutos, pero muestran menor eficiencia por plaza y menor ocupación estimada, por lo que no serían la primera opción dentro de este análisis.

### Zonas exploratorias

Además de Centro, se recomienda revisar en una segunda fase distritos con menor volumen de alojamientos pero señales interesantes:

* **Palma-Palmilla**
* **Puerto de la Torre**
* **Ciudad Jardin**

Estas zonas pueden presentar ingresos medios u ocupaciones atractivas, pero deben analizarse con cautela porque el número de alojamientos es menor y los resultados pueden estar más influidos por casos concretos.

---

## ⚠️ Sesgos y limitaciones

Este proyecto incluye una sección específica de advertencias porque el análisis tiene limitaciones importantes:

* El dataset procede de Airbnb y no representa todo el mercado turístico.
* Puede haber reservas realizadas por Booking, webs propias, agencias u otros canales.
* Los ingresos son brutos y estimados.
* No se incluyen gastos de compra, impuestos, financiación, limpieza, reformas ni comisiones.
* La ocupación estimada no equivale a reservas reales confirmadas.
* El dashboard no sustituye un estudio financiero, legal, urbanístico ni de rentabilidad neta.

Por tanto, los resultados deben interpretarse como **señales comparativas del mercado visible**, no como una recomendación definitiva de compra.

---

## 🛠️ Tecnologías utilizadas

* **Python**
* **Pandas**
* **NumPy**
* **Matplotlib**
* **Seaborn**
* **Jupyter Notebook**
* **Power BI Desktop**
* **Git**
* **GitHub**

---

## ▶️ Cómo reproducir el análisis

### 1. Clonar el repositorio

```bash
git clone https://github.com/Gema-Villanueva/dashboard-inversion-malaga.git
cd dashboard-inversion-malaga
```

### 2. Crear y activar entorno virtual

```bash
python -m venv .venv
```

En Windows:

```bash
.venv\Scripts\activate
```

En Linux/Mac:

```bash
source .venv/bin/activate
```

### 3. Instalar dependencias

```bash
pip install -r requirements.txt
```

### 4. Ejecutar notebooks

Ejecutar en orden:

```text
notebooks/01_data_preparation_cleaning.ipynb
notebooks/02_exploratory_data_analysis.ipynb
```

### 5. Abrir dashboard

Abrir el archivo en Power BI Desktop:

```text
dashboard/dashboard_inversion_malaga.pbix
```

---

## 📄 Informes y entregables

El proyecto incluye los siguientes entregables finales:

| Archivo                                        | Descripción                              |
| ---------------------------------------------- | ---------------------------------------- |
| `dashboard/dashboard_inversion_malaga.pbix`    | Dashboard interactivo en Power BI        |
| `reports/dashboard_inversion_malaga.pdf`       | Exportación del dashboard en PDF         |
| `reports/informe_final_inversion_malaga.md`    | Informe final del proyecto               |
| `notebooks/01_data_preparation_cleaning.ipynb` | Limpieza y preparación del dataset       |
| `notebooks/02_exploratory_data_analysis.ipynb` | Análisis exploratorio de datos           |
| `data/processed/listings_malaga_processed.csv` | Dataset limpio utilizado en el dashboard |
| `data/processed/resumen_distritos_malaga.csv`  | Resumen agregado por distrito            |

---

## 📌 Interpretación del dashboard

El dashboard está diseñado para apoyar una primera fase de análisis. Su objetivo es ayudar a comparar zonas y tipos de vivienda turística a partir de señales disponibles en los datos.

No debe interpretarse como:

* Una recomendación directa de compra.
* Una estimación de rentabilidad neta.
* Un estudio legal o urbanístico.
* Una predicción financiera definitiva.

---

## 👩‍💻 Autora

**Gema Villanueva Breña**

Proyecto individual desarrollado dentro del Módulo 2, centrado en análisis de datos, visualización interactiva y comunicación de insights para público no técnico.

---

<div align="center">

## 🏁 Conclusión

Este proyecto convierte datos turísticos abiertos en una herramienta visual de apoyo a la decisión.

La recomendación inicial es estudiar con mayor profundidad viviendas turísticas de **1 o 2 dormitorios en el distrito Centro** como opción principal, sin descartar una segunda fase de análisis sobre zonas con menor oferta pero buenas señales, como **Palma-Palmilla**, **Puerto de la Torre** y **Ciudad Jardin**.

Los resultados deben interpretarse como una primera criba basada en señales comparativas del mercado visible, no como una decisión final de compra ni como una estimación de rentabilidad neta.

</div>
