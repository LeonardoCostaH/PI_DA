<p align='center'>
<img src="img/prevencion_accidentes_aereos.png"  height=300>
<p>

# <h1 align="center">**`Análisis de Datos para la prevención de Accidentes Aéreos`**</h1>
---


### 📘 Índice del Proyecto

- [Descripción del trabajo realizado](#descripción-del-trabajo-realizado)
- [EDA (Exploratory Data Analysis)](#eda-exploratory-data-analysis)
  - [Exploración inicial y limpieza de datos](#exploración-inicial-y-limpieza-de-datos)
- [Análisis de hallazgos clave 🔍](#análisis-de-hallazgos-clave-)
  - [Víctimas por categoría (pasajeros, tripulación, terceros) y eventos atípicos](#víctimas-por-categoría-pasajeros-tripulación-terceros-y-eventos-atípicos)
  - [Pasajeros a bordo vs. total de fatalidades](#pasajeros-a-bordo-vs-total-de-fatalidades)
  - [Tendencias temporales y contexto histórico](#tendencias-temporales-y-contexto-histórico)
  - [Accidentes por estación del año](#accidentes-por-estación-del-año)
  - [Día más desafortunado del año](#día-más-desafortunado-del-año)
  - [Horarios de mayor incidencia](#horarios-de-mayor-incidencia)
  - [Causas raíz: análisis de palabras clave](#causas-raíz-análisis-de-palabras-clave)
- [Modelos, Aerolíneas y Rutas con Mayor Número de Accidentes](#modelos-aerolíneas-y-rutas-con-mayor-número-de-accidentes)
  - [Modelos de aeronaves con mayor número de accidentes](#modelos-de-aeronaves-con-mayor-número-de-accidentes)
  - [Empresas de aviación con mayor cantidad de accidentes](#empresas-de-aviación-con-mayor-cantidad-de-accidentes)
  - [Rutas con mayor número de accidentes](#rutas-con-mayor-número-de-accidentes)
- [Uso de tecnologías y herramientas](#uso-de-tecnologías-y-herramientas-️)
- [Contacto](#contacto-)


---

## **Descripción del trabajo realizado**

En el marco de un proyecto impulsado por la **Organización de Aviación Civil Internacional (OACI)**, se llevó a cabo un análisis exhaustivo de datos relacionados con accidentes aéreos ocurridos desde inicios del siglo XX. El objetivo principal fue comprender las causas más frecuentes de estos incidentes, identificar patrones temporales y geográficos, y aportar información valiosa que contribuya a mejorar la **seguridad operacional** en la aviación global.

Para ello, se utilizó un *conjunto de datos* proporcionado por la OACI, el cual fue enriquecido mediante la integración de fuentes de datos externas estratégicamente seleccionadas, lo que permitió una **visión más completa y contextualizada** de los eventos. Además del análisis estadístico, se desarrolló un dashboard interactivo con visualizaciones dinámicas en Power BI que permiten explorar los resultados de manera clara y accesible.

A continuación, se presentan los principales hallazgos obtenidos a partir de este trabajo.

---

## **`EDA` (Exploratory Data Analysis)**

### `Exploración Inicial y Limpieza de Datos`

- **Estructura Inicial:** Se eliminó la columna `Unnamed: 0`, que cumplía una función de índice redundante.
- **Manejo de Valores Faltantes:** Los valores desconocidos o nulos, representados originalmente por el carácter `?`, fueron estandarizados a **NaN** para facilitar su tratamiento y análisis estadístico.
- **Ingeniería de Características:** La columna `Fecha` fue convertida al formato estándar YYYY-MM-DD de Pandas. A partir de esta, se crearon nuevas columnas (`Día`, `Mes`, `Año`) para un análisis temporal detallado.
- **Estandarización:** Se renombraron las columnas para una **mejor legibilidad y estandarización** de los datos.
- **Optimización:** Finalmente, el DataFrame procesado se guardó en formato **Parquet** para optimizar el rendimiento y acelerar la lectura de datos en análisis posteriores.

---

## `Análisis de Hallazgos Clave` 🔍

### Víctimas por categoría (pasajeros, tripulação, terceiros) y Eventos Atípicos

<img src="img/Distribución de Fatalidades en Accidentes de Avión por categoría.png">

El gráfico muestra la distribución de fatalidades entre pasajeros, tripulación y terceros (personas en tierra). Es fundamental notar el **dato atípico (outlier) de 2001** en la categoría de "Terceros/En Tierra". Tras la investigación, se concluyó que este pico corresponde a las **2750 fatalidades en tierra** resultantes de los ataques terroristas del 11 de septiembre, lo que demuestra la importancia del contexto histórico en el análisis de datos.

### Pasajeros a Bordo vs. Total de Fatalidades

<img src="img/Relación entre Pasajeros a Bordo y total de fatalidades.png">

Se observa una tendencia general **lineal** donde un mayor número de pasajeros a bordo se correlaciona con un mayor número de fatalidades en caso de accidente, lo que indica que muchos eventos son catastróficos. Sin embargo, una porción significativa de los puntos cae por debajo de esta línea, indicando que el número de fatalidades es considerablemente menor al de pasajeros a bordo, registrándose **cero fatalidades en numerosos incidentes**, lo cual subraya la efectividad de las medidas de seguridad y los avances en la capacidad de supervivencia.

### Tendencias Temporales y Contexto Histórico

<img src="img/Tendencias Temporales en Acidentes Aéreos (Conteo Mensual).png">
<img src="img/Tendencias Temporales en Accidentes Aéreos (Conteo Anual).png">
<img src="img/Tendencia Temporal de Accidentes Aéreos por Década.png">

Se observa un notable **aumento en la frecuencia** de accidentes a partir de **1920**, reflejando la expansión de la aviación comercial tras la Primera Guerra Mundial. Esta tendencia se estabiliza hasta **1990**, momento en el cual la curva comienza un **declive sostenido**, lo que se atribuye a la implementación global de regulaciones de la OACI, el desarrollo de la gestión de recursos de tripulación (**CRM**) y los avances tecnológicos en aeronaves y sistemas de control de tráfico aéreo.

### Accidentes por Estación del Año

<img src="img/Accidentes por Estación.png">

**Invierno y Otoño** presentan el mayor índice de accidentes. Esto está directamente asociado a las **condiciones meteorológicas adversas** (hielo, nieve, viento, baja visibilidad) características de estas estaciones, que son factores de riesgo conocidos.

### Día más Desafortunado del Año

<img src="img/Días con Mayor Número de Accidentes.png">
Se presenta el conteo agregado de accidentes aéreos por día del año (sin considerar el año), identificando los días con la mayor coincidencia histórica de incidentes.

### Horarios de Mayor Incidencia

<img src="img/Cantidad de Accidentes por Hora del Día.png">

El análisis por hora revela que el pico de accidentes ocurre en las horas de **mayor tráfico aéreo y operación**, específicamente entre las **7:00 AM y las 8:00 PM**.

### Causas Raíz: Análisis de Palabras Clave

El análisis de frecuencia de palabras y frases extraídas de los resúmenes de los informes de accidentes permite una clasificación clara de las causas primarias.

<img src="img/Word Cloud de Resúmenes de Accidentes de Avión.png">
<img src="img/Palabras Clave en Resúmenes de Accidentes de Avión.png">

**Palabras Clave (Ejemplos):** *Crashed* (Estrelló), *Aircraft* (Aeronave), *Crew* (Tripulación), *Engine* (Motor), *Failure* (Falla), *Approach* (Aproximación).

<img src="img/Frases Más Comunes en Resúmenes de Accidentes Aéreos.png">

**Frases Clave (Ejemplos):** *Pilot Error* (Error del Piloto), *Engine Failure* (Fallo del Motor), *Icing* (Formación de Hielo), *Controlled Flight Into Terrain* (Vuelo Controlado contra Terreno).

El análisis revela que las principales causas de accidentes se centran en tres grandes categorías:
1.  **Errores Humanos:** *Pilot Error* y *Crew Error*.
2.  **Fallos Técnicos:** *Engine Failure* y *problemas mecánicos*.
3.  **Factores Ambientales:** *Icing* y *Controlled Flight Into Terrain* (a menudo exacerbado por baja visibilidad).

## Modelos, Aerolíneas y Rutas con Mayor Número de Accidentes

Estos gráficos identifican los componentes que históricamente han estado más involucrados en incidentes, lo que ayuda a enfocar los esfuerzos de prevención y mantenimiento.

### Modelos de Aeronaves con más casos de accidentes
<img src="img/Modelos de Aeronave con Mayor Índice de Accidentes.png">

El gráfico de barras identifica los modelos de aeronaves con el mayor número absoluto de accidentes registrados.

**Insight Clave:** La posición de los modelos más antiguos en este ranking está fuertemente ligada a su **longevidad operacional** y su **herencia militar**. Muchos aviones de las primeras décadas (como el **Douglas DC-3**) fueron producidos en grandes volúmenes durante la Segunda Guerra Mundial (versión militar C-47) y luego adaptados para el transporte civil.

Estos modelos, aunque robustos, carecían de los sistemas de seguridad y navegación modernos (**TCAS, EGPWS**) exigidos por la OACI hoy en día. Por lo tanto, su alto conteo de accidentes refleja:
1.  **Alta Exposición Estadística:** Gran número de horas de vuelo acumuladas a lo largo de muchas décadas.
2.  **Tecnología de Transición:** Operación en una era donde la seguridad y la regulación aeronáutica aún estaban en desarrollo, utilizando diseños influenciados por la necesidad militar inmediata.

### Empresas de Aviación con Mayor cantidad de Accidentes
<img src="img/Empresas de Aviación con Mayor Cantidad de Accidentes.png">

Esta visualización enumera las empresas de aviación que han estado involucradas en la mayor cantidad de accidentes a lo largo de la historia analizada.

**Insight Clave:** La alta incidencia de accidentes en estas aerolíneas se explica, primariamente, por su **antigüedad y gran volumen de operación**. Las compañías de bandera o las grandes corporaciones aéreas que operaron desde el período de expansión posterior a las Guerras Mundiales han acumulado un vasto historial de vuelos, lo que aumenta su probabilidad estadística de incidentes.

Además de la alta exposición, es relevante considerar que muchas de estas empresas:
1.  **Surgieron en el *Boom* Post-Guerra:** Se expandieron rápidamente en un entorno regulatorio menos estricto (antes de la consolidación de la OACI).
2.  **Operaron Aeronaves Militares Adaptadas:** Utilizaron flotas que, en sus inicios, incluían modelos de origen militar excedente (como se mencionó en el análisis de modelos), que a menudo presentaban desafíos operacionales y de mantenimiento.

### Rutas con mayor número de Accidentes
<img src="img/Rutas con Mayor Frecuencia de Accidentes Aéreos.png">

El gráfico muestra las rutas específicas (definidas por pares de aeropuertos o regiones) donde se han concentrado más accidentes aéreos.

**Insight Clave:** La concentración de incidentes en ciertas rutas no solo está ligada al **alto volumen de tráfico comercial** (mayor exposición), sino que también puede reflejar herencias geopolíticas y desafíos operacionales persistentes:

1.  **Herencia de Rutas Pioneras:** Rutas transoceánicas o intercontinentales fueron frecuentemente **establecidas y perfeccionadas por la logística militar** durante las guerras. Las operaciones en estas rutas, en los inicios de la aviación comercial, presentaban mayores riesgos debido a la navegación imprecisa, la ausencia de opciones de desvío y las severas condiciones meteorológicas sobre grandes extensiones de agua o terrenos remotos.
2.  **Riesgo Geográfico y Congestión:** Las rutas más accidentadas generalmente incluyen aeropuertos con **condiciones geográficas desafiantes** o que operan con **alta saturación de tráfico** (aumentando el riesgo en las fases críticas de aterrizaje y despegue), reflejando un cúmulo de incidentes a lo largo del tiempo.

---

## Uso de Tecnologías y Herramientas 🛠️

Este análisis de prevención de accidentes aéreos se desarrolló utilizando un *stack* de tecnologías robustas que cubren todas las etapas del proceso de *Data Science*, desde la manipulación inicial hasta la visualización de resultados.

| Categoría | Herramienta | Rol Específico en el Proyecto |
| :--- | :--- | :--- |
| **Entorno de Desarrollo** | **Jupyter Notebooks** | Utilizado como entorno interactivo para la escritura, ejecución y documentación del código Python (EDA y Análisis). |
| **Manipulación y Limpieza** | **Pandas** | Esencial para la carga del *conjunto de datos*, la limpieza de datos (ej. manejo de `?` y rellenado de `NaN`), el filtrado, la agregación de información y la ingeniería de características (creación de columnas de fecha/tiempo). |
| **Cálculo Numérico** | **NumPy** | Empleado para realizar cálculos numéricos eficientes y operaciones vectorizadas necesarias en el análisis estadístico subyacente de los datos. |
| **Visualización Estática** | **Matplotlib** | Herramienta clave para generar las visualizaciones exploratorias (EDA), incluyendo gráficos de tendencias temporales, distribuciones y análisis de frecuencia, documentados en este `README.md`. |
| **Visualización Dinámica** | **Power BI** | Utilizado para diseñar y construir un **Dashboard Interactivo**. Permitió el seguimiento en tiempo real de los Indicadores Clave de Rendimiento (KPIs) y la exploración dinámica y *drill-down* de los resultados del análisis. |

---

## Contacto 📧

¡Me encantaría conectar y discutir este análisis, o cualquier otro proyecto de Data Science!

| Plataforma | Detalle |
| :--- | :--- |
| **Nombre** | Leonardo Augusto Costa Hermes |
| **Correo Electrónico** | [lcostahermes@gmail.com](mailto:lcostahermes@gmail.com) |
| **LinkedIn** | [![LinkedIn Badge](https://img.shields.io/badge/LinkedIn-Perfil-blue?style=flat&logo=linkedin)](https://www.linkedin.com/in/leonardo-c-hermes/) |
