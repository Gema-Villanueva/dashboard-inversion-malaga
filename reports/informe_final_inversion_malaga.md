# Informe final

## Dashboard de inversión en vivienda turística en Málaga ciudad

**Proyecto individual — Módulo 2**
**Autora:** Gema Villanueva Breña

---

## 1. Introducción

Este proyecto tiene como objetivo analizar el mercado visible de vivienda turística en Málaga ciudad a partir de datos procedentes de Airbnb. El análisis se ha planteado desde la perspectiva de una inversora privada interesada en identificar zonas y tipos de vivienda que puedan mostrar señales atractivas para una posible inversión.

El objetivo del proyecto no es recomendar una compra concreta ni calcular una rentabilidad neta real, sino construir una herramienta de primera criba que permita comparar distritos, niveles de actividad, ingresos estimados y características de los alojamientos.

Para ello se ha desarrollado un proceso completo de análisis de datos: limpieza del dataset, análisis exploratorio, creación de variables derivadas y construcción de un dashboard interactivo en Power BI.

---

## 2. Objetivo del análisis

La pregunta principal del proyecto es:

**¿Qué distritos de Málaga ciudad presentan mejores señales para estudiar una inversión en vivienda turística?**

Para responder a esta pregunta, el análisis se centra en varias señales de mercado:

* Volumen de alojamientos por distrito.
* Precio medio y precio mediano por noche.
* Ocupación media estimada.
* Ingresos brutos estimados.
* Ingresos medios por alojamiento.
* Nivel de competencia.
* Tipo de dormitorio y eficiencia por plaza.
* Limitaciones y sesgos del dato.

El enfoque utilizado es comparativo. No se busca elegir automáticamente “el mejor distrito”, sino detectar zonas y tipologías de vivienda que merecen un análisis posterior más detallado.

---

## 3. Datos utilizados y preparación

El dataset utilizado procede de Inside Airbnb y contiene información de alojamientos turísticos en Málaga. El archivo original incluía 9.714 registros y 79 columnas.

Durante la fase de preparación se realizaron los siguientes procesos:

* Selección de columnas relevantes para el análisis.
* Renombrado de variables para facilitar la interpretación.
* Filtrado de alojamientos completos, excluyendo habitaciones privadas u otros tipos de alojamiento.
* Conversión del precio a formato numérico.
* Tratamiento de valores nulos.
* Eliminación de valores extremos en precio.
* Creación de variables derivadas.
* Exportación de un dataset limpio para el análisis y el dashboard.

Tras la limpieza, el dataset principal quedó compuesto por **7.598 viviendas completas** en Málaga ciudad.

Entre las variables derivadas creadas destacan:

* `tipo_dormitorios`: clasificación del alojamiento según número de dormitorios.
* `ingresos_estimados_mensuales`: estimación mensual a partir del ingreso anual.
* `nivel_precio`: clasificación del alojamiento según su rango de precio.
* `nivel_competencia`: clasificación de distritos según volumen de oferta.
* `total_alojamientos_distrito`: número de alojamientos por distrito.

---

## 4. Principales indicadores del mercado

El análisis general del dataset limpio muestra los siguientes valores principales:

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

Estos indicadores ofrecen una primera visión del mercado, pero no son suficientes por sí solos para tomar decisiones. Por ese motivo, el dashboard se estructura en varias páginas que permiten profundizar en ingresos, competencia, actividad y tipo de producto.

---

## 5. Resultados principales del análisis

### 5.1. Ingresos por distrito

El distrito Centro concentra la mayor parte del ingreso estimado total. Esto se explica principalmente porque también concentra gran parte de la oferta visible en Airbnb.

Sin embargo, al analizar el ingreso medio por alojamiento, aparecen otros distritos con señales interesantes. Esto demuestra que no basta con analizar el volumen total de ingresos, ya que un distrito con muchos alojamientos puede acumular más ingresos simplemente por tamaño de mercado.

Por tanto, la comparación entre ingreso total e ingreso medio permite diferenciar entre:

* Distritos con gran volumen de mercado.
* Distritos con mejor rendimiento medio por alojamiento.
* Zonas que pueden requerir un análisis posterior más detallado.

---

### 5.2. Actividad y competencia

La página de actividad y competencia compara dos señales clave:

* Concentración de alojamientos por distrito.
* Ocupación media estimada por distrito.

Centro destaca claramente como el distrito con mayor concentración de alojamientos, lo que indica una fuerte presencia de oferta turística y, por tanto, mayor competencia.

Sin embargo, algunos distritos con menor volumen muestran niveles de ocupación estimada relativamente altos. Esto sugiere que la actividad turística no depende únicamente del número de alojamientos disponibles.

Esta comparación permite separar dos conceptos importantes:

* **Oferta o competencia:** cuántos alojamientos existen en una zona.
* **Actividad estimada:** qué nivel de ocupación presentan los alojamientos.

---

### 5.3. Segmentación del producto

La segmentación por tipo de dormitorio permite analizar qué tipo de vivienda presenta mejores señales económicas.

Los alojamientos de 3 o más dormitorios muestran mayores ingresos medios anuales. Esto es esperable, ya que suelen tener mayor capacidad, precios más altos y posibilidad de alojar a más personas.

Sin embargo, al normalizar los ingresos por capacidad, los alojamientos de 1 dormitorio muestran mayor eficiencia por plaza y mayor ocupación media estimada.

Esta diferencia es importante porque evita una conclusión simplista. No se puede afirmar que los alojamientos grandes sean siempre mejores únicamente porque generan más ingresos absolutos. Para interpretar correctamente la oportunidad, es necesario cruzar:

* Ingreso anual medio.
* Ingreso estimado por plaza.
* Ocupación media estimada.
* Precio noche.
* Volumen de alojamientos.

---

## 6. Dashboard desarrollado

El dashboard se ha desarrollado en Power BI Desktop y se encuentra en la carpeta:

`dashboard/dashboard_inversion_malaga.pbix`

Además, se ha exportado una versión en PDF para facilitar su revisión:

`reports/dashboard_inversion_malaga.pdf`

El dashboard contiene cinco páginas:

1. **Visión general**
   Resumen ejecutivo con indicadores principales del mercado.

2. **Ingresos por distrito**
   Comparación entre concentración del ingreso total e ingreso medio por alojamiento.

3. **Actividad y competencia**
   Análisis del volumen de oferta y la ocupación media estimada por distrito.

4. **Segmentación del producto**
   Comparativa por tipo de dormitorio, incluyendo ingresos, eficiencia por plaza, ocupación y precio noche.

5. **Sesgos y limitaciones**
   Advertencias necesarias para interpretar correctamente los resultados.

---

## 7. Sesgos y limitaciones

El análisis presenta varias limitaciones que deben tenerse en cuenta.

En primer lugar, los datos proceden de Airbnb, por lo que no representan todo el mercado turístico. Existen reservas que pueden realizarse a través de Booking, webs propias, agencias, canales directos u otras plataformas.

En segundo lugar, los ingresos utilizados son estimaciones brutas. No incluyen gastos de compra, impuestos, limpieza, comunidad, reformas, financiación, seguros, mantenimiento ni comisiones de plataformas.

Además, la ocupación estimada no equivale a reservas reales confirmadas. Debe interpretarse como una señal aproximada de actividad basada en la información disponible en el dataset.

Por último, el dashboard no sustituye un estudio financiero, legal o urbanístico. Tampoco calcula rentabilidad neta ni retorno de inversión. Su función es servir como herramienta de primera criba para orientar análisis posteriores.

---

## 8. Recomendación de priorización

A partir de las señales analizadas en el dashboard, no plantearía una única recomendación cerrada, sino una priorización en dos niveles: una opción principal más robusta y varias zonas exploratorias que merecen un análisis posterior.

Como opción principal, priorizaría una vivienda turística de **1 o 2 dormitorios en el distrito Centro**. Centro concentra la mayor parte de la oferta visible, del ingreso estimado total y de la actividad turística. Aunque esto implica una competencia elevada, también indica una zona con demanda contrastada y mayor volumen de datos, por lo que las señales son más estables que en distritos con pocos alojamientos.

En cuanto al tipo de vivienda, los alojamientos de **3 o más dormitorios** presentan mayores ingresos medios anuales, pero también menor ocupación estimada y menor eficiencia por plaza. Por ese motivo, no serían la primera opción si el objetivo es buscar equilibrio entre ingreso, actividad y eficiencia.

Los alojamientos de **1 dormitorio** muestran la mayor eficiencia por plaza y la mayor ocupación media estimada, lo que los convierte en una opción interesante si se prioriza eficiencia y rotación. Los alojamientos de **2 dormitorios** ofrecen una posición intermedia: mayor ingreso anual que los de 1 dormitorio, buena ocupación estimada y una capacidad más flexible.

Junto a esta opción principal, también revisaría como **zonas exploratorias** algunos distritos con menor volumen de alojamientos pero señales atractivas en ingresos medios u ocupación. En este grupo destacan especialmente **Palma-Palmilla**, **Puerto de la Torre** y **Ciudad Jardin**. Estos distritos muestran métricas interesantes, pero al tener una muestra más pequeña deben interpretarse con especial cautela.

Por tanto, la priorización quedaría así:

* **Opción principal:** Centro, por volumen de mercado, actividad turística y mayor solidez de la muestra.
* **Tipología preferente:** viviendas de 1 o 2 dormitorios.

  * **1 dormitorio:** si se busca mayor eficiencia por plaza y ocupación.
  * **2 dormitorios:** si se busca equilibrio entre ingresos anuales, capacidad y ocupación.
* **Zonas exploratorias:** Palma-Palmilla, Puerto de la Torre y Ciudad Jardin, por sus señales de ingresos u ocupación, aunque requieren validación adicional por menor volumen de datos.

Esta recomendación debe entenderse como una **priorización inicial basada en señales comparativas del mercado visible en Airbnb**, no como una decisión final de compra. Antes de invertir sería imprescindible analizar precio real de adquisición, gastos, fiscalidad, normativa turística, licencias, financiación, estado del inmueble, costes de reforma y rentabilidad neta esperada.

---

## 9. Conclusión

El análisis muestra que Málaga ciudad presenta un mercado de vivienda turística con una fuerte concentración en el distrito Centro, tanto en volumen de oferta como en ingresos estimados totales. Esta concentración convierte a Centro en la zona más sólida para iniciar un estudio de inversión, ya que ofrece mayor volumen de datos, demanda turística contrastada y una actividad visible más estable.

Sin embargo, el análisis también muestra que no conviene limitar la interpretación únicamente al volumen total. Algunos distritos con menor número de alojamientos presentan señales interesantes en ingresos medios u ocupación estimada. Este es el caso de zonas como Palma-Palmilla, Puerto de la Torre o Ciudad Jardin, que podrían representar oportunidades a estudiar en una segunda fase. La cautela aquí es importante: al tener menos alojamientos, sus métricas pueden estar más influidas por casos concretos y necesitan validación adicional.

Respecto al tipo de vivienda, los alojamientos de 3 o más dormitorios generan más ingresos absolutos, pero los alojamientos de 1 dormitorio muestran mayor eficiencia por plaza y mayor ocupación estimada. Los alojamientos de 2 dormitorios representan una opción intermedia interesante, al combinar mayor ingreso anual que los de 1 dormitorio con una ocupación estimada todavía alta.

Por tanto, la recomendación inicial sería estudiar con mayor profundidad viviendas turísticas de **1 o 2 dormitorios en el distrito Centro** como opción principal. Además, se recomienda analizar de forma exploratoria distritos con menor volumen pero buenas señales, especialmente **Palma-Palmilla, Puerto de la Torre y Ciudad Jardin**, antes de descartar oportunidades fuera del centro.

El dashboard desarrollado permite comparar distritos y tipos de vivienda de forma visual, clara y crítica. Su principal valor es facilitar una primera selección de zonas y productos que podrían estudiarse con mayor profundidad en una fase posterior.

La conclusión final es que los resultados deben interpretarse como señales comparativas del mercado visible, no como una recomendación directa de compra ni como una estimación de rentabilidad neta.


---

## 10. Archivos principales del proyecto

| Archivo                                        | Descripción                              |
| ---------------------------------------------- | ---------------------------------------- |
| `notebooks/01_data_preparation_cleaning.ipynb` | Limpieza y preparación del dataset       |
| `notebooks/02_exploratory_data_analysis.ipynb` | Análisis exploratorio de datos           |
| `data/processed/listings_malaga_processed.csv` | Dataset limpio utilizado en el dashboard |
| `data/processed/resumen_distritos_malaga.csv`  | Resumen agregado por distrito            |
| `dashboard/dashboard_inversion_malaga.pbix`    | Dashboard interactivo en Power BI        |
| `reports/dashboard_inversion_malaga.pdf`       | Exportación del dashboard en PDF         |
| `reports/informe_final_inversion_malaga.md`    | Informe final del proyecto               |

---

