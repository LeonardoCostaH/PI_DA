<p align='center'>
<img src="img/prevencion_accidentes_aereos.png"  height=300>
<p>

# <h1 align="center">**`Análisis para prevención de Accidentes Aéreos`**</h1>
---

### Índice del Proyecto

- [Descripción del trabajo realizado](#descripción-del-trabajo-realizado)
- [EDA (Exploratory Data Analysis)](#eda-exploratory-data-analysis)
  - [Exploración Inicial](#exploración-inicial)
  - [Análisis](#análisis)
    - [Víctimas por Categoría](#víctimas-por-categoría)
    - [Pasajeros a Bordo vs. Fatalidades](#pasajeros-a-bordo-vs-fatalidades)
    - [Tendencias Temporales](#tendencias-temporales)
    - [Accidentes por Estación del Año](#accidentes-por-estación-del-año)
    - [Día más Desafortunado del Año](#día-más-desafortunado-del-año)
    - [Accidentes por Horario](#accidentes-por-horario)
    - [Análisis de Palabras en los Reportes](#análisis-de-palabras-en-los-reportes)
    - [Modelos de Aeronaves con Mayor Número de Accidentes](#modelos-de-aeronaves-con-mayor-número-de-accidentes)
    - [Empresas de Aviación con Mayor Cantidad de Accidentes](#empresas-de-aviación-con-mayor-cantidad-de-accidentes)
    - [Rutas con Mayor Número de Accidentes](#rutas-con-mayor-número-de-accidentes)
- [Uso de Tecnologías](#uso-de-tecnologías)
- [Contacto](#contacto)

---

## **Descripción del trabajo realizado**

En el marco de un proyecto impulsado por la Organización de Aviación Civil Internacional (OACI), se llevó a cabo un análisis exhaustivo de datos relacionados con accidentes aéreos ocurridos desde inicios del siglo XX. El objetivo principal fue comprender las causas más frecuentes de estos accidentes, identificar patrones temporales y geográficos, y aportar información valiosa que contribuya a mejorar la seguridad en la aviación.

Para ello, se utilizó un dataset proporcionado por la OACI, el cual fue enriquecido mediante el cruce con fuentes de datos externas seleccionadas estratégicamente. Además del análisis estadístico, se desarrolló un dashboard interactivo con visualizaciones dinámicas que permiten explorar los resultados de manera clara y accesible.

A continuación, se presentan los principales hallazgos obtenidos a partir de este trabajo.

---

**`EDA` (Exploratory Data Analysis)**

`Exploración Inicial`

- Analisando mí dataset ví que practicamente todas las columnas eran útiles, así que solo fue necesário excluír la columna "Unnamed: 0", que tenía función de índice.
- Agregué también columnas de dia, mes y año después de cambiar el formato de la columna Fecha para el patrón del pandas (yyy-mm-dd)
- No habían columnas dobles 
- Las columnas tenían el valor "?" adónde serían valores Desconocidos/Nulos, así que cambié para NAN, para facilitar mí analisis.
- Renombré todos los nombres de columna, solamente por un tema de mejor comprensión 
- Al final Guardé mí dataframe en formato parquet, para accelerar la lectura 

---

`Análisis` 
- Víctimas por categoría (passageiros, tripulação, terceiros)
<img src="img/Distribución de Fatalidades en Accidentes de Avión por categoría.png">
  - me llamó la atención el outlier que se puede ver en 2001 de las fatalidades en solo, así que buscando la fecha exacta, llegué a la conclusión de que se trata del atentado de 11 de septiembre con un total de 2750 fatalidades en solo.

- Comparativo de Pasajeros a Bordo y Total de Fatalidades
<img src="img/Relación entre Pasajeros a Bordo y total de fatalidades.png">
  - Lo que vi es que la mayoría del gráfico es bastante lineal(la cantidad de pasajeros coincide con la cantidad de Fatalidades), en general no cambian mucho para arriba, pero hay muchos casos que hay más sobrevivientes que pasajeros a bordo.

- tendencias temporales
<img src="img/Tendencias Temporales en Acidentes Aéreos (Conteo Mensual).png">
<img src="img/Tendencias Temporales en Accidentes Aéreos (Conteo Anual).png">
<img src="img/Tendencia Temporal de Accidentes Aéreos por Década.png">
  - En 1930 hay un aumento de accidentes aereos, que se mantiene de esa manera hasta el año 1990 que empiezan a bajar los números

- Accidentes por Estación del Año
<img src="img/Accidentes por Estación.png">
  - Invierno y Otoño son las estaciones con mayor índice de accidentes Aereos

- Día más Desafortunado del Año
<img src="img/Días con Mayor Número de Accidentes.png">
  - esa lista tiene los días que coincidieron más accidentes aereos sin considerar el año

- Accidentes por horario
<img src="img/Cantidad de Accidentes por Hora del Día.png">
  - esa lista tiene los horarios con mayor número de accidentes, asi que el pico de accidentes está de las 7AM a las 8PM

- Palabras más usadas en los Relatórios de accidentes
<img src="img/Word Cloud de Resúmenes de Accidentes de Avión.png">
<img src="img/Palabras Clave en Resúmenes de Accidentes de Avión.png">
  - Crashed: Se estrelló
  - Aircraft: Aeronave
  - Plane: Avión
  - Crew: Tripulación
  - Flight: Vuelo
  - Pilot: Piloto
  - Runway: Pista de aterrizaje
  - Engine: Motor
  - Approach: Aproximación
  - Failure: Falla

<img src="img/Frases Más Comunes en Resúmenes de Accidentes Aéreos.png">

  - pilot Error: Error del Piloto
  - Crew Error: Error de la Tripulación
  - Cause Unknown: Causa Desconocida
  - Icing: Formación de Hielo
  - The No: Sin traducción específica 
  - Controlled Flight Into Terrain: Vuelo Controlado contra Terreno
  - Crashed Into Mt: Choque Contra Montaña
  - Cause Undetermined: Causa Indeterminada
  - Engine Failure: Fallo del Motor
  - Midair Collision: Colisión en el Aire

Con esas palabras sacadas de los relatórios, puedo ver que las mayores causas de accidentes de avión son los errores humanos, ambientes naturales y errores técnicos.

- Modelos de Aeronaves con más casos de accidentes
<img src="img/Modelos de Aeronave con Mayor Índice de Accidentes.png">

- Empresas de Aviación con Mayor cantidad de Accidentes
<img src="img/Empresas de Aviación con Mayor Cantidad de Accidentes.png">

- Rutas con mayor numero de Accidentes
<img src="img/Rutas con Mayor Frecuencia de Accidentes Aéreos.png">

---

## Uso de Tecnologías

Este análisis se llevó a cabo utilizando una variedad de tecnologías, incluyendo:

- **Jupyter:** Se utilizó Jupyter Notebook para escribir y ejecutar código Python de manera interactiva, lo que permitió un análisis eficiente de los datos.

- **Pandas:** La biblioteca Pandas se utilizó para la manipulación y análisis de datos. Facilitó la limpieza, filtrado y agregación de datos para su posterior visualización.

- **NumPy:** NumPy se empleó para realizar cálculos numéricos y operaciones en matrices, lo que resultó útil en diversas partes del análisis.

- **Matplotlib:** Matplotlib fue la herramienta de elección para la creación de visualizaciones, incluyendo gráficos de barras, gráficos de líneas y gráficos de distribución.

- **Power BI:** Para llevar a cabo el seguimiento y presentación de los indicadores clave de rendimiento (KPIs) propuestos, se utilizó Power BI, lo que permitió una visualización efectiva y dinámica de los datos.

---

## Contacto

- Nombre: Leonardo Augusto Costa Hermes
- Correo Electrónico: lcostahermes@gmail.com
- LinkedIn: [/in/leonardo-c-hermes/](https://www.linkedin.com/in/leonardo-c-hermes)
