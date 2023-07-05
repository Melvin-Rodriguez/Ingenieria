# Power BI Desktop 

# Objetivos

1. Conocimiento principales funciones Power BI Desktop
2. Crear Dashboard
3. Con DAX generar métricas y columnas calculadas


# Descripción general

Power BI es una herramientas de anális de datos y creación de ifnormes de instalación local muy utilizada en Business Intelligence, dentro de las muchas ventajas que ofrece, es que permite conectar, transformar y analizar grandes volúmenes de datos y a partir de estos datos poder construir modelos que se relacionen (relacionales) de forma fácil y automatizada, a su vez poder realizar cálculos complejos de forma rápida y sencilla utilizando DAX, como presentación de resultados permite crear informes de manera personaliza e interactivos, permitiendo realizar analítica avanzada. 

# Recursos
Ruta de aprendizaje [Donde iniciar](https://learn.microsoft.com/en-us/training/powerplatform/power-bi?WT.mc_id=powerbi_landingpage-docs-link)

Comunidad PowerBI [Forums](https://community.powerbi.com/t5/Forums/ct-p/PBI_Comm_Forums)

Galería [Dashboards](https://community.powerbi.com/t5/Data-Stories-Gallery/bd-p/DataStoriesGallery)

Cheat Sheet [DAX](https://community.powerbi.com/t5/Data-Stories-Gallery/DAX-Cheat-Sheet-Success-of-CSS-Selector/td-p/559474)

# Fundamentos de Power BI

## Extracción y Transformación

Como se mencionó anteriormente para la **extracción y transformación** de datos Power BI permite conectarse e importa datos de múltiples orígenes tales como: 

* Archivos planos y carpetas: csv, text, xls, etc.

* Bases de datos: SQL, Access, Oracle, IBM, Azure, etc.

* Servicios en línea: Sharepoint, GitHub, Dynamics 365, Google Analytics, Salesforce, servicio Power BI, etc.

* Otros: Web feeds, scripts R, Spark, Hadoop, etc.

Al completarse la extracción (importación) de datos existen funciones importantes para la **transformación de los datos** que se encuentran distribuidas en las pestañas siguientes:

* Inicio: La pestaña incluye configuraciones generales y operaciones comunes de transformación de datos.

* Transformación: La pestaña incluye herramientas para modificar columnas existentes.

* Agregar columna: ofrece operaciones para crear nuevas columnas como reglas condicionales, operaciones de texto, cálculos, etc.

## Modelo de Datos

Una vez realizados los pasos anteriores podemos iniciar a crear **modelos de datos** entiendace como modelado a preparar los datos par aque estén concectados y puedan usarse de forma conjunta, es decir establecer **relaciones** entre las tablas a utilizar.

Podemos dividir los modelos o esquemas en dos tipos: 

* Modelo en estrella: Hay una tabla central (tabla de hechos) rodeada de otras tablas (tablas de dimensiones)

### ![image](https://user-images.githubusercontent.com/111929312/210885604-bf245365-c437-47ba-ba18-976b9db687dc.png)


* Modelo en copo de nieve: deriva del modelo en estrella donde las tablas de dimensiones se separan en múltiples tablas.

### ![image](https://user-images.githubusercontent.com/111929312/210886144-e678e7c8-c792-4bc5-8eb8-9007db7a3ba5.png)


## Métricas con DAX

DAX es catalogado como un lenguaje de programación utilizado en Power BI con el cual se pueden crear métricas o columnas calculadas y esto poderlo agregar al modelo. La sintaxis es intuitiva y ayuda a generar métricas avanzadas variables, así como cálculos complejos. 

Las columnas calculadas son utilizadas para obtener un valor para cada registro (fila), y las métricas son utilizadas para agregar un valor.

## Visualización de informes

Al momento de visualizar los resultados con gráficas podemos realizarlos desde la **vista de inicio** las herramientas de Power BI nos permitirán añadir gráficas e introducir diferentes datos hasta modificar las gráficas.

* **Páginas del informe:** muestran las diferentes hojas de las que se compone el dashboard.

* **Opciones de visualización:** es el panel principal donde seleccionamos el tipo de grafica que queremos crear.

* **Panel de filtros:** permite configurar los filtros.

* **Campo/Formato/Analytics:** permiten introducir los datos, modificar los campos o añadir análisis, como líneas de tendencia, etc.

* **Panel de datos:** contiene las diferentes tablas, columnas, métricas y columnas calculadas que contiene el informe.

![image](https://user-images.githubusercontent.com/111929312/210890633-8e4be906-051d-42a7-ae36-163564663267.png)


# Proyecto práctico

### 1. Extracción y transformación de datos

Par obtener los datos nos vamos a Inicio > Obtener datos > seleccionamos de las opciones el tipo de archivo a conectar/cargar, en este caso utilizaremos CSV > damos doble click o bien seleccionamos Conectar, nos mostrara el navegador de documentos y seleccionamos nuestro archivo > por ultimo seleccionamos Cargar.

![image](https://user-images.githubusercontent.com/111929312/210902743-fea55a3d-bba0-451f-b224-a6fd104192a4.png)
                                 **--------------------------------------------------**
![image](https://user-images.githubusercontent.com/111929312/210902823-ccc75fb2-4604-41ee-8c7c-39d92b0cb445.png)

En la pestaña de **Transformación de Datos** se abrirá una nueva ventana en la cual tendremos múltiples opciones de transformación dentro de las que podemos mencionar la pestaña **Vista** y las opciones Calidad de columnas, Distribución de columnas y Perfil de columna, estas opciones permitirán claridad de la calidad de los datos por columna y poder decidir qué acciones tomar.  

![image](https://user-images.githubusercontent.com/111929312/210907060-e8025510-87cf-4e84-90c6-df207604c9fb.png)

También es importante conocer el tipo de datos que contiene cada columna, esto lo podemos realizada en la pestaña Inicio > Tipo de Datos

![image](https://user-images.githubusercontent.com/111929312/210907146-938205ee-775d-4d15-978f-e6a037382223.png)

### 2. Modelado de datos

El concento basico del modelado de datos es: Tablas conectadas por relaciones usando un identificador único en ambas tablas.(Ver Imagen Modelo)

**Tipos de Tablas**
* Existen tablas de **hechos** que contienen valores y números.
* Tablas de **dimensiones** que contienen información descriptiva basada en texto y explicativos

Las tablas de hechos se encuentran en la parte central del modelo y las tablas de dimensiones alrededor de esta. (Ver Imagen Modelo) 

**Las relaciones (cardinalidad) pueden se:**
* Uno a Uno
* Uno a Varios
* Varios a Uno
* Varios a Varios (debe existir una tabla intermedia con valores únicos para crear una relación de varios a uno y de uno a varios)


**Se debe considerar:**
* Cada tabla debe tener un objetivo distinto y especifico
* Una tabla que contenga información de dos temas diferentes es necesario dividirla en dos tablas
* Tipo de modelos de datos (Estrella, Copo de Nieve)
* Llaves foráneas y primarias
* Normalización de datos: objetivos principales 
  * Eliminar datos redundantes
  * Minimizar los errores y anomalías
  * Simplificar consultas y estructuras del modelo

**Imagen Modelo**

![image](https://user-images.githubusercontent.com/111929312/211933760-28820691-58bf-4f33-af8c-0fae11b30be5.png)


**Crear una Relacion**

Para crear una relación únicamente arrastramos el campo llave de la tabla A hacia el campo llave de la tabla B, se valida la relación, cardinaliad y si todo esta como lo deseamos click en aceptar.

![image](https://user-images.githubusercontent.com/111929312/211935677-c93b0e0e-7d95-47ff-af9f-9eea34bd3ca6.png)


**Modificar la relación: click derecho en la relación**

![image](https://user-images.githubusercontent.com/111929312/211934956-7141132b-1b9d-4428-ac2d-15c35c6b6417.png)

Pueden tenerse relaciones activas y relaciones secundarias (al utilizar relaciones secundarias no se filtrarían las gráficas por esta relación, por lo que, según el caso es recomendable mantenerlas activas)

**Modificar Dirección de filtro: click derecho en la relación**

![image](https://user-images.githubusercontent.com/111929312/211935351-63e99e4e-1190-4e71-a998-d24efe7f32b0.png)

Por defecto la relación del filtro apuntara del lado uno a varios, cuando se filtra una tabla en esta condición el filtro va con dirección a la flecha.

**Nota:** Al principio se utiliza la dirección en ambos sentidos pero es importante no abusar de esta condición, para evitar problemas de circularidad en las relaciones.

Power BI genera relaciones automáticamente, sin embargo, es necesario revisar estas relaciones. 

**Agregar tabla calendario al modelo por medio de una funcion de DAX**

Modelado > Nueva Tabla > Renombrar a “Calendario” 

![image](https://user-images.githubusercontent.com/111929312/211935836-bbce53a4-f7da-456b-9e3f-cce1e7ae1782.png)

Al crease la tabla debemos realizar la relación con la tabla y campo deseado (día, semana, mes, año, etc.) es importante que el formato de fecha coincida en ambas tablas.

![image](https://user-images.githubusercontent.com/111929312/211936009-4c98951c-1b4e-4700-87a5-784f990949fd.png)


### 3. Generar métricas y columnas calculadas con DAX

**Columna calculada**: Tiene una representación física en la tabla y con un valor fijo para cada registro

![image](https://user-images.githubusercontent.com/111929312/211943404-59816d52-624a-4324-b07c-cf6cba1be9ce.png)

**Métricas**: No tienen representación física en la tabla, son un valor agregado y también pueden se filtradas, las métricas utilizan las funciones que se dividen en:

* Fecha y Tiempo 
* Filtro 
* Información 
* Lógica 
* Matemáticas y trigonometría
* Estadísticas
* Texto 
* Inteligencia del Tiempo 
* Padres e Hijos 
* Otras funciones 

![image](https://user-images.githubusercontent.com/111929312/211943671-d85697e6-02a4-4e52-8d9c-8410c2f7c8b5.png)

**Crear una métrica o columna**: Click derecho sobre la tabla y seleccionamos la opción deseada 

![image](https://user-images.githubusercontent.com/111929312/211943773-1e0defab-3497-4cbb-b351-3894baebb23d.png)


**Algunos ejemplos**

![image](https://user-images.githubusercontent.com/111929312/211945583-f392e353-f757-480d-af04-e7c171a62db6.png)

![image](https://user-images.githubusercontent.com/111929312/211945603-2361f2e9-b44d-4a79-9779-1c97b1471c55.png)


### 4. Visualización de datos con informes     

**Principales opciones** 

![image](https://user-images.githubusercontent.com/111929312/212196291-1f48cb67-7507-4f85-9a71-701accfd05d5.png)

![image](https://user-images.githubusercontent.com/111929312/212196410-545b59b8-8761-4f20-9924-b0962b0431dd.png)


**Sugerencias**

* Utilizar imagen de fondo (template)

![image](https://user-images.githubusercontent.com/111929312/212196435-c07fe366-3c62-43f0-b897-f907d3784317.png)

* Seleccionar un estilo (recomendable usar el mismo estilo para todas las gráficas)

![image](https://user-images.githubusercontent.com/111929312/212196497-edf2a449-e7a6-4666-b37b-c1ac64967f77.png)

* Agregar o cambiar graficas

![image](https://user-images.githubusercontent.com/111929312/212196543-4eac55b0-577e-4d04-bf07-c44fa4228e70.png)

* Separar los filtros de las gráficas y paneles de métricas, para que el informe sea mucho más amigable e intuitivo para el usuario

![image](https://user-images.githubusercontent.com/111929312/212196589-942545ef-ecee-4fd4-8e4d-c08949b302df.png)

* Es importante elegir la gráfica correcta para representar la información 

![image](https://user-images.githubusercontent.com/111929312/212196639-bf29317b-e37b-493a-890b-65c0535318eb.png)

* Interacción entre gráficos

![image](https://user-images.githubusercontent.com/111929312/212196685-ae11ce64-9fcc-466a-b4de-646aa76b42f9.png)

<!--
# Referencias 
Agradecimiento por los conocimientos adquiridos a: Curso Completo de Power BI Desktop - Coursera Project Network -->

