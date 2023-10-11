<p align='center'>
<img src ="https://d31uz8lwfmyn8g.cloudfront.net/Assets/logo-henry-white-lg.png">
<p>

<h1 align='center'>
 <b>PROYECTO INDIVIDUAL </b>
</h1>
 
# <h1 align="center">**`Accidentes Aereos`**</h1>


<p align='center'>
<img src="https://slack-imgs.com/?c=1&o1=ro&url=https%3A%2F%2Fcdn.pixabay.com%2Fphoto%2F2016%2F09%2F15%2F16%2F13%2Fairplane-1671967_1280.jpg"  height=300>
<p>

## **Descripción del problema -contexto y rol a desarrollar-**

### **Contexto**

Los accidentes aéreos son eventos inesperados e indeseados que involucran aeronaves y se producen daños físicos a personas o a la propia aeronave. Un accidente aéreo puede involucrar cualquier tipo de aeronave, incluyendo aviones comerciales, aviones privados, helicópteros, planeadores y globos aerostáticos.

Los accidentes aéreos pueden ser causados por diversos factores, como errores humanos, fallos de equipos, problemas meteorológicos, problemas de mantenimiento, fallas en la gestión del tráfico aéreo, problemas de diseño o problemas de fabricación. Y en cuanto a sus consecuencias, pueden ser tanto en términos de pérdidas humanas como económicas.

Es por eso que la industria de la aviación, las autoridades reguladoras y los investigadores trabajan incansablemente para mejorar la seguridad de la aviación y prevenir futuros accidentes. Por otro lado, para las organizaciones asociadas a la aviación, estudiar la causalidad de los accidentes y aprender a cómo prevenirlos en el futuro es clave para poder evitar pérdidas humanas y daños materiales significativos. 


### **Rol a desarrollar**

La **Organización de Aviación Civil Internacional (OACI)**, organismo de la Organización de las Naciones Unidas, quiere investigar en profundidad los accidentes producidos desde inicios del siglo XX. Para ello, el objetivo principal es poder obtener un análisis de datos relacionado a esto, junto a un dashboard que complemente los análisis con sus visualizaciones. 

La OACI únicamente cuenta con un dataset sobre datos de accidentes de aviones, pero insta a la consultora de datos -de la que forman parte- que intente cruzar esta información con otras fuentes de su interés. Esto con el objetivo de obtener mayor claridad y consistencia en los fundamentos del estudio.



**`EDA` (Exploratory Data Analysis)**

`Exploración Inicial`

- Analisando mí dataset ví que practicamente todas las columnas eran útiles, así que solo fue necesário excluír la columna "Unnamed: 0", que tenía función de índice.
- Agregué también columnas de dia, mes y año después de cambiar el formato de la columna Fecha para el patrón del pandas (yyy-mm-dd)
- No habían columnas dobles 
- Las columnas tenían el valor "?" adónde serían valores Desconocidos/Nulos, así que cambié para NAN, para facilitar mí analisis.
- Renombré todos los nombres de columna, solamente por un tema de mejor comprensión 
- Al final Guardé mí dataframe en formato parquet, para accelerar la lectura 

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
