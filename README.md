
<h1 align='center'>
 <b>PROYECTO INDIVIDUAL Nº2</b>
</h1>
 
# <h1 align="center">**`Accidentes Aereos Data Analytics`**</h1>

## Autor:
<h2 align='center'>
 <b>Néstor Fabio Cardona C.</b>
</h2>

¡Bienvenidos, les presento el proyecto de Análisis de Datos de Accidentes Aéreos del siglo XX! En esta ocasión, Se desarrolla el trabajo situándose en el rol de un ***Data Analyst***.
<p align='center'>
<img src = 'https://cnnespanol.cnn.com/wp-content/uploads/2018/05/accidentes-aviones-comerciales-mas-mortiferos-de-la-historia14.jpg' height = 200>
<p>

## **Descripción del problema - Contexto y rol a desarrollar-**

### **Contexto**

En los albores del siglo XX, la aviación era una novedad emocionante, pero también peligrosa. Los accidentes eran comunes, y cada uno de ellos servía como una lección dura pero necesaria para los pioneros de la aviación. A medida que avanzaba el siglo, los accidentes aéreos se volvieron más infrecuentes, pero también más mortíferos debido al aumento del tamaño y la velocidad de las aeronaves. La aviación se convirtió en un medio de transporte revolucionario y, al mismo tiempo, en un campo de desafíos y tragedias. 

El análisis y la exploración de datos desempeñan un papel crucial en la obtención de información valiosa dentro del vasto conjunto de datos disponibles sobre accidentes aereos. En este contexto, es clave el uso de una valiosa fuente de datos actualizados que proporcionen información relevante para el analisis.




### **Rol a desarrollar**

La Organización de Aviación Civil Internacional (OACI) , organismo de la Organización de las Naciones Unidas, quiere investigar en profundidad los accidentes producidos desde inicios del siglo XX. Para ello, el objetivo principal es poder obtener un análisis de datos relacionados a esto, junto a un tablero que complemente los análisis con sus visualizaciones.

La Organización de Aviación Civil Internacional (OACI) dispone exclusivamente de un conjunto de datos relacionados con accidentes de aeronaves. Sin embargo, el propósito de este esfuerzo es alcanzar una mayor transparencia y coherencia en los fundamentos del estudio en curso. 


## **Propuesta de trabajo**

`EDA` (Exploratory Data Analysis)

Se realiza un análisis exploratorio de los datos en el notebook EDA_DA.ipynb estan los pasos documentados con claridad, con las conclusiones correspondientes en cada gráfico empleado y análisis de lo observado, utilizando celdas Markdown para tal fin. 


Entre estos aspectos destacados se encuentran: *búsqueda de valores faltantes, valores atípicos/extremos u outliers y registros duplicados*. Asimismo, la utilización de gráficos coherentes según la tipología de variable que corresponda resulta esencial.

***Se acompañan los gráficos con análisis propios.***

Inicialmente se carga el archivo accidentesaviones.csv al DataFrame df_accid_aereos para hacer el análisis exploratorio de datos (EDA)

Luego Se grafica un mapa de calor para detectar visiblemente los valores NaN o vacíos

En el mapa de calor no se detectan, por tanto, se hacen conteos al DataFrame para validar la existencia de registros  NaN, vacios y nulos, y se aprecia un DataFrame bastante depurado para hacer los KPI propuestos.

Se detecta que existen muchos campos como string que deben convertirse a enteros. por tanto, se convierte a enteros la información numérica, que esta como string y se verifica que los cambios sean los correctos en los campos numéricos.

### DETECCION DE OUTLIERS EN TRIPULACIÓN FALLECIDA 'crew_fatalities'

Se usa un diagrama de caja para detectar los outliers en la columna 'crew_fatalities' que es el número de miembros de la tripulación fallecidos en el accidente, dato indispensable para el KPI No 1: 'Tasa de Fatalidad de la Tripulación'

Se visualiza un comportamiento normal en el diagrama de caja, de los datos en el campo 'crew_fatalities' excepto por dos registros outliers que pudieran considerarse errores.

Se ordena de mayor a menor la información en la columna 'crew_fatalities', para analizar los registros dudosos que pudieran ser error.

### OUTLIERS TRIPULACIÓN FALLECIDA
1er Registro
El dato que podría considerarse error, fue un accidente de avión militar
Fecha del siniestro: August 24, 1921	
Operador : Military - Royal Airship Works	
Ruta: River Humber, England
Tripulación fallecida: 43 miembros

Es una información que no debe considerarse errónea dado que fue
un avión militar y el accidente ocurrió hace mas de 100 años y es 
un accidente verdadero.

2do Registro
El dato que podria considerarse error fue un accidente de avión en la India
Fecha del siniestro: November 12, 1996		
Operador : Saudi Arabian Airlines / Kazakhstan Airlines	
Ruta: Near Charkhi Dadri, India
Personal a Bordo : 349
Tripulación fallecida: 33 miembros

Es una información no debe considerarse errónea dado que fue un avión de gran capacidad, en la India, lo cual es esperado el nivel de decesos.

Se Verifica la existencia de registros duplicados de ‘crew_fatalities’ en una grafica de barras. Se nota que no hay registros duplicados, pero se valida con un conteo minucioso, que efectivamente confirma la información en la grafica de barras.

### DETECCION DE OUTLIERS EN PASAJEROS FALLECIDOS 'passenger_fatalities'

Se usa un diagrama de caja para detectar los outliers en la columna 'passenger_fatalities' que es el número de Pasajeros Fallecidos en el accidente, dato indispensable para el KPI No 2: 'Tasa de Supervivencia de Pasajeros'

Se visualiza en el diagrama de caja un comportamiento normal en los datos del campo 'passenger_fatalities', excepto por dos registros outliers que pudieran considerarse erroneos.

Se ordena el DataFrame por la columna 'passenger_fatalities' de mayor a menor, para analizar los dos registros outliers.

### OUTLIERS EN PASAJEROS FALLECIDOS
1er Registro
El dato que podria considerarse outlier fue un accidente de avión comercial en Tenerife (Islas Canarias)
Considerado el accidente de aviacion mas grande del mundo, según los datos registrados hasta la fecha.
Fecha del siniestro: March 27, 1977	
Operador : Pan American World Airways / KLM	
Ruta: Tenerife, Canary Islands	
Pasajeros fallecidas: 560 

Es una información que no debe considerarse errónea dado que fue
un hecho comprobado y es considerado el mayor siniestro de aviación hasta la fecha

2do Registro
El dato que podría considerarse outlier fue un accidente de avión en Japón
Fecha del siniestro: August 12, 1985		
Operador: Japan Air Lines	
Ruta: Tokyo - Osaka	
Pasajeros fallecidos: 505 

Es una información que no debe considerarse errónea dado que fue el mayor 
accidente de un avión comercial en la historia en Japón cuando un Boeing 747 de Japan Airlines se estrelló contra el monte Ogura en Japón. 

Se Verifican los registros duplicados de ‘passenger_fatalities’ usando una grafica de barras. Se valida la información de la grafica de barras, haciendo un conteo minucioso, el cual nos confirma que efectivamente no se tienen registros duplicados.

Seguidamente se hace un resumen estadístico de las columnas numéricas en el DataFrame. Este resumen incluye varias estadísticas descriptivas para cada columna, como la cuenta de valores no nulos, la media, la desviación estándar, los valores mínimo y máximo, y los percentiles.

count: El número de valores no nulos en la columna.
mean: La media aritmética de la columna.
std: La desviación estándar de la columna.
min: El valor mínimo de la columna.
25%: El primer cuartil (percentil 25).
50%: La mediana (percentil 50), que es el valor que divide los datos en dos mitades iguales.
75%: El tercer cuartil (percentil 75).
max: El valor máximo de la columna.

Se detecta una información bastante depurada del DataFrame df_accid_aereos

Acto seguido se depura el campo fecha y se convierte de string a tipo fecha, a partir del campo fecha creamos una nueva columna llamada década, la cual es necesaria para la estrategia de la creación del KPI No. 1 'Tasa de Fatalidad de la Tripulación'

### Finalmente aquí creamos el archivo 'accidentesaereos2.csv' con el cual se trabaja en Power Bi

Por ultimo se hace una grafica de barras apiladas para dar un vistazo general con la información relevante para los dos KPIs propuestos en el proyecto.

`Dashboard`

Es funcional, incluye **filtros**, permitiendo explorar detalladamente los datos con la selección de cada uno de ellos. Es decir, es **interactivo**. Posee un diseño que facilita la interpretación de la información y su análisis, por tanto, la claridad en la presentación de los datos, la estetica, y los gráficos según las variables a visualizar, son representativos.

Inicialmente se carga el archivo AccidentesAereos2.csv que es la fuente de datos que se depuró después de hacer el EDA

### **KPI No.1 Tasa de Fatalidad de la Tripulaciónr**

Luego se crea la columna **TasaFatalidadTripulacion**, la cual hace con la formula propuesta para dicho KPI la cual es  AccidentesAereos2[crew_fatalities] / COUNTROWS(AccidentesAereos2)

A partir de la columna **decada**, creamos los campos correspondientes a cada decada, cada columna contiene la información de TasaFatalidadTripulacion de acuerdo a la decada descrita, asi la columna 1920 tiene todas las Tasas de Fatalidad de Tripulación de dicha decada, la columna 1930 posee las Tasas de Fatalidad de Tripulación de la decada 1930 y asi sucesivamente hasta la decada 2020 iniciando en la decada 1900.

Se usa un "segmentador de datos" configurado como deslizador para la columna "fecha" de la tabla, tambien se usa otro "segmentador de datos" pero configurado como lista de selección multiple, para la columna "decada" de modo que se pueda limitar la selección a una sola decada, con estos dos segmentadores se controla la información a visualizar en cuanto a tiempo se refiere.

Se usa el grafico de barras apiladas para visualizar cada decada con su Tasa de Fatalidad de Tripulación, adicional a ello se usa el grafico de lineas para detallasr año a año la tasa de Fatalidad de tripulación de las decadas a visualizar

Y finalmente se presentan tarjetas para detallar datos relevantes como Tasa de Fatalidad de tripulación y la tripulación fallecida en la selección escogida.

### **KPI No.2 Tasa de Supervicencia de los Pasajeros**

Se crea la columna TasaSupePasajeros la cual corresponde a la formula = AccidentesAereos2[PASAJEROS A BORDO] - AccidentesAereos2[passenger_fatalities]/ AccidentesAereos2[PASAJEROS A BORDO] 


Se usa un "segmentador de datos" configurado como deslizador para la columna "fecha" de la tabla, tambien se usa otro "segmentador de datos" pero configurado como lista de selección multiple, para la columna "decada" de modo que se pueda limitar la selección a una sola decada, con estos dos segmentadores se controla la información a visualizar en cuanto a tiempo se refiere.

Se usa el grafico de columnas apiladas para dar la información de supervivencia de pasajeros por decada, adicional a ello se apoya dicho grafico con el grafico de areas apiladas el cual muestra la Tasa de Supervivencia de Pasajeros Anual, pero también se tienen varias tarjetas Tasa de supervivencia, pasajeros a bordo y pasajeros fallecidos       

`KPIs`

El KPI propuesto a continuación, se representa adecuadamente en el dashboard.

Evaluar la disminución de un 10% la `Tasa de fatalidad de la tripulación` en los últimos 10 años, en comparación con la década anterior .

Se Define la tasa de fatalidad de la tripulación como el número total de tripulantes fallecidos en los accidentes registrados en la década a considerar, dividido en la cantidad total de accidentes aéreos ocurridos en este período de tiempo. Su fórmula es (Suma total de fallecidos en el período de tiempo / Suma total de accidentes en el período de tiempo).

El segundo KPI prouesto es:

`Tasa de Supervivencia de Pasajeros:`
    
    Fórmula: (Pasajeros a bordo - Passenger Fatalities) / Pasajeros a bordo
    
    Este KPI muestra la proporción de pasajeros que sobrevivieron en relación con el número total de pasajeros a bordo.

`Repositorio de GitHub`

https://github.com/NestorFCardona/PI_Data_Analysis

En este repositoria se encuentran los archivos del EDA y el archivo del dashboard en Power Bi 

EDA_PIDA.ipynb
PI_DA NFC.pbix


#   P I _ D a t a _ A n a l y s i s 
 
 
