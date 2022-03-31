# Integradora II

## contenido
<details>
  <summary>Tabla contenidos</summary>
  <ol>
    <li>
      <a href="#acerca-del-proyecto">Acerca de Proyecto</a>
      <ul>
        <li><a href="#descripción">Descripción</a></li>
        <li><a href="#objetivos">Objetivos</a></li>
        <li><a href="#organigrama">Organigrama</a></li>
        <li><a href="#diagrama-gantt">Diagrama Gantt</a></li>
      </ul>
    </li>
    <li>
      <a href="análisis-de-la-solución">Análisis de la Solución</a>
      <ul>
        <li><a href="#requerimientos">Requerimientos</a></li>
        <li><a href="#diagrama-casos-de-uso">Diagrama de Casos de Uso</a></li>
      </ul>
    </li>
    <li>
      <a href="#diseño-de-la-solución">Diseño de la Solución</a>
      <ul>
        <li><a href="#modelo-relacional">Modelo No Relacional</a></li>
        <li><a href="#diagrama-de-componentes">Diagrama de Componentes</a></li>
      </ul>
    </li>    
    <li>
      <a href="#implementación">Implementación</a>
      <ul>
        <li><a href="#estándares-codificación">Estándares Codificación</a></li>
        <li><a href="#arquitectura">Arquitectura</a></li>
      </ul>
    </li>      
    <li>
      <a href="#pruebas">Pruebas</a>
      <ul>
        <li><a href="#casos-de-prueba">Casos de prueba</a></li>
        <li><a href="#ejecución">Ejecución</a></li>
      </ul>
    </li>       
    <li><a href="#guias">Guias</a></li>
    <li><a href="#contribucion">Contribución</a></li>
    <li><a href="#licencia">licencia</a></li>
    <li><a href="#contacto">Contacto</a></li>
    <li><a href="#participantes">Participantes</a></li>
  </ol>
</details>

## Acerca del proyecto
<!-- Descripción -->
### Nombre del proyecto:
Proyecto de Índices de Vegatación para el estado de Guanajuato.

#### Descripción.
La aplicación web está enfocada a permitirle al usuario analizar algunos índices de vegetación en cada uno
de los 46 municipios que conforman el estado de Guanajuato, México, por medio de 2 colecciones de
imágenes proporcionadas por 2 de los más importantes satélites que sirven para trabajar con
teledetección, dichos satélites son Sentinel 2 y Landsat 8, dichos satélites le entregan al usuario un análisis
de la región basado en el satélite, el índice de vegetación y la fecha seleccionada, con la finalidad de
brindar al usuario una variedad más amplia de opciones y combinaciones a la hora de obtener su análisis.

Al momento de generar un análisis de algún índice de vegetación, el usuario tiene la posibilidad de trazar
polígonos en alguna región o una porción de un terreno en específico del municipio, para posteriormente
contar con la posibilidad de descargar una imagen del área trazada con extensión GeoTIFF, finalmente el
usuario tiene la opción de trabajar con dichas imágenes en alguna herramienta de software adicional para
el uso de estas, tales como Google Earth Pro o QGIS por mencionar algunas.

<!-- Objetivos -->
#### Objetivos.
Generar una herramienta de analisis de indices de vegetación en cada municipio del estado de Guanajuato, con el fin  de que el usuario pueda visualizar, analizar y  utilizar la información para adaptarla a sus necesidades.

<!-- Organigrama -->
#### Organigrama.
El control del proceso de asignación y realización de actividades fue implementado con ayuda de Jira Software, la cual es una herramienta en línea para la administración de proyectos de software con el objetivo de documentar el seguimiento del desarrollo de las diferentes actividades que se van desarrollando a lo largo de la implementación de un proyecto con el fin de documentar los avances de cada integrante del equipo de una manera más organizada y coherente.
El control de Actividades del equipo se encuentra en la siguiente [liga...][organigrama-url]

<!-- Diagrama Gantt -->
#### Diagrama Gantt.
Diagrama Gantt.

El diagrama de Gantt generado a partir del control de actividades del orgnanigrama definido en el punto anterior,
se puede encontrar en el siguiente [enlace...][gantt-url]

## Análisis de la Solución
<!-- Requerimientos -->
#### Requerimientos.
•	RF1 Registro de Usuario
El registro de usuario es el mecanismo mediante el cual se puede registrar una nueva cuenta con el objetivo de obtener acceso al aplicativo. Durante el proceso de creación de una cuenta el usuario debe ingresar algunos datos por medio de un formulario.
o	Nombre de la cuenta (Opcional)
o	Email de la cuenta (Obligatorio)
o	Contraseña (Obligatoria de más de 4 caracteres)
o	Confirmación de contraseña 

•	RF2 Inicio de Sesión
Una vez que el usuario ha creado su cuenta en el sistema, para acceder al aplicativo es necesario iniciar sesión por medio del formulario de ingreso en el cual se solicitan 2 campos.
o	Email del usuario (Obligatorio)
o	Contraseña del usuario (Obligatoria)

•	RF3 Análisis de Índices
El tercer requerimiento es el análisis de diferentes índices de cada municipio del estado de Guanajuato, México, basados en las imágenes obtenidas por medio de las colecciones de imágenes de los satélites de Sentinel 2 y Landsat 8.
Para realizar un análisis el usuario debe seleccionar algunos campos por medio de un panel principal de selección.
o	Selector de Municipio: El usuario debe seleccionar el municipio del estado de Guanajuato que desea analizar.
o	Selector de Colección: Se debe seleccionar la colección de imágenes o el satélite del cual se desea obtener las imágenes ya sea Sentinel 2 o Landsat 8.
o	Selector de Índice: El usuario puede seleccionar 3 índices diferentes de análisis.
	RGB: Este índice entrega un análisis en color natural del área.
	NDVI: Este índice entrega el análisis normalizado de la vegetación en la zona.
	NDWI: Este índice entrega el análisis normalizado del agua en la zona.
o	Selector de Fecha: El usuario puede seleccionar la fecha de la cual desea obtener el análisis, considerando que Sentinel 2 trabaja con lapsos de 7 días y Landsat 8 con lapsos de 16 días de distancia.

•	RF4 Trazado de Polígonos
El cuarto requerimiento obtenido es el trazado de áreas o porciones de terreno por delimitación por polígonos, este requerimiento permite al usuario delimitar una zona específica de trabajo.
El usuario debe seleccionar una casilla de verificación que le permite dibujar una zona por medio de punteros que formaran un polígono que rodea el área de trabajo.

•	RF5 Descarga de Imágenes
El quinto requerimiento es la opción de descarga de la imagen generada a través de la definición del área trazada por polígonos, pues el usuario puede descargar la imagen del área en formato GeoTIFF para su trabajo posterior en algún sistema de información geográfica (SIG).
El usuario debe seleccionar el link de descarga de la imagen generada para que esta se descargue automáticamente.

<!-- Diagrama de Casos de Uso -->
#### Diagrama Casos de Uso.
![Casos de Uso][Casos-url]
<!-- Diseño del proyecto -->
## Diseño de la Solución.
•	Base de datos maps (No relacional-MongoDB) Montada en Atlas.

•	Aplicación web Desarrollada en el Framework Node JS.

•	Aplicación web Desarrollada en Google Earth Engine Code Editor.
<!-- Modelo Relacional -->
#### Modelo No Relacional.
![Modelo][Modelo-url]
<!-- Diagrama de Componentes -->
#### Diagrama de Componentes.
![Diagrama Componentes][Componente-url]
<!-- Implementación del proyecto -->
## Implementación.
•	Base de datos maps (No relacional-MongoDB) Montada en Atlas.

Se desarrollo una base de datos no relacional haciendo uso del 
gestor de base de datos MongoDB, la cual posteriormente fue 
montada en un cluster de MongoDB Atlas con el objetivo de que 
la  base de datos este sostenida en la nube y el servicio pueda
utilizarse en cualquier momento.

El motivo por el cual se decidio utilizar una base de datos 
No relacional, es debido a su gran flexibilidad, agilidad y
escalabilidad a la hora de almacenar grandes cantidades de datos.

•	Aplicación web Desarrollada en el Framework Node JS.

Se desarrollo una aplicación web haciendo uso del Framework
Node JS en conjunto con el lenguaje Javascript.La razón principal
por la cual se decidió elegir el Framework Node JS para la 
implementación del proyecto de Google Earth Engine, es debido a la 
estrecha relación que existe entre este Framework y el lenguaje de 
programación JavaScript.

Por otro lado, este framework cuenta con una optimización de recursos 
muy buena para el desarrollo de proyectos grandes y complejos como lo 
es este proyecto, ya que no requiere de grandes requerimientos de hardware 
y software para ejecutarse de manera correcta, así mismo implementa una rapidez
de desarrollo que es de gran utilidad para reducir en gran medida el tiempo de
desarrollo del proyecto.

•	Aplicación web Desarrollada en Google Earth Engine Code Editor.

La mayor parte del código fuente de la aplicación fue desarrollado con
ayuda del editor de código de Google Earth Engine, El motivo por el cual se
utilizó esta tecnología para este proyecto, es su funcionalidad que permite 
trabajar y mostrar en tiempo real la ejecución de la aplicación de forma rápida
y sencilla para el manejo de datos geográficos satelitales que son de vital 
importancia y que fueron de gran utilidad para el desarrollo de los requerimientos
del proyecto. 
<!-- Estándares de Codificación -->
#### Estándares Codificación.
Estándares empleados en la codificación

En el siguiente enlace se encuentra un archivo con los estándares
de codificación implementados en la [aplicación...][estandar-url]

<!-- Arquitectura MVC y Middleware -->
#### Arquitectura.
•	Patrón de diseño
  MVC: Durante el desarrollo del proyecto se implemento el Modelo Vista Controlador
  el cual es un estilo de arquitectura de software que separa los datos de la aplicación,
  la interfaz de usuario, y la lógica de control en tres componentes distintos.

  -El Modelo contiene una representación de los datos que maneja el sistema, su lógica de negocio, y sus mecanismos de persistencia.

  -La Vista, o interfaz de usuario, que compone la información que se envía al cliente y los mecanismos interacción con éste.

  -El Controlador, que actúa como intermediario entre el Modelo y la Vista, gestionando el flujo de información entre ellos y las transformaciones para adaptar los datos a las necesidades de cada uno.
 
•	Patrón de seguridad

  bcryptjs: Es una función de hashing de passwords para encriptar contraseñas de usuario,
  esta dependecia fue de gran utlidas para asegurar la seguridad en las contraseñas de 
  usuario.

  express-session: El middleware express-session almacena los datos de sesión en el servidor,sólo guarda el ID de sesión en la propia cookie, no los datos de sesión. Esta dependencia 
  fue fundamental para el manejo de inicios de sesión con express.

  passport-local: Este módulo sirve para permitir autenticarse utilizando un nombre de usuario y contraseña en aplicaciones Node.js. Al conectarse a Passport, la autenticación local se puede integrar de manera fácil y discreta en cualquier aplicación o marco que admita el middleware de estilo Connect , el cual esta incluido en Express, razón por la cual se trabajo con esta dependencia en el proyecto.

<!-- Pruebas proyecto -->
## Pruebas.
<!-- Casos de prueba -->
#### Casos de prueba.
--RF1 Registro de Usuario--

CP01_Registro de un Usuario.

CP02_Registro de un Usuario Repetido.

CP03_Registro de Usuario con contraseña de menos de 4 caracteres.

CP04_Registro de Usuario con correo en formato invalido.

CP05_Registro de Usuario que introduce una confirmación de contraseña diferente.

--RF2 Inicio de Sesión--

CP06_Inicio de Sesión con cuenta registrada.

CP07_Inicio de Sesión con cuenta no registrada.

CP08_Inicio de Sesión sin ingreso de correo y contraseña.

CP09_Cerrar Sesión.

CP10_Denegación de Rutas.

--RF3 Análisis de índices--

CP11_Selección del municipio.

CP12_Seleccion de colección (satélite).

CP13_Seleccion de área con sentinel2 y con el índice RGB.

CP14_Seleccion de área con Sentinel 2 y con el índice NDVI y Sentinel2.

CP15_Seleccion de área con Sentinel 2 y con el índice NDWI.

CP16_Seleccion de área con Landsat8 y con el índice RGB.

CP17_Seleccion de área con Landsat8 y el índice NDVI.
CP18_Seleccion de área con Landsat8 y con el índice NDWI.

--RF4 Trazado de Polígonos--

CP19_Trazado de Polígonos.

--RF5 Descarga de Imágenes--

CP20_Descarga de Imágenes.

<!-- Ejecución Casos de prueba -->
#### Ejecución.
Los resultados de ejecución de casos de prueba se encuentran disponibles en el siguiente [enlace…][pruebas-url]


<!-- Iniciando -->
## Iniciando
<!-- Requisitos -->
### Requisitos
Requisitos de Instalación.

•	Node JS

•	VS Code 

•	Descargar Código Fuente de Github.
<!-- Instalación -->
### Instalacion
Instalación del Software

Para lograr la instalacion de la aplicacion de forma correcta atra vez de este github sera unica y exclusivamente si se siguen los 
siguienetes pasos a realizar:

  1.-Una vez accedido al link del repositorio, se tendra que descargar
  o bien se clone en la carpeta seleccionada, para empezar la instalacion
  el proyecto de manera local.

  2.-Una vez descargado en su equipo de computo, sera necesario 
  descomprimir el archivo rar llamado OptimenMaps-main.

  3.- Una vez descomprimido sera necesario de abrir el entorno de 
  desarrollo, llamado Visual Stdio Code, el cual permitara abrir los
  archivos.

  4.- Dentro de Visual Studio se tendra que dar clic al boton "Files" y
  luego a "Open Folders" para abrir el archivo NodeJS y así tenerlo en el
  entorno.

  5.- Por ultimo al tener el archivo habierto, sera necesario de apretar,
  las teclas " CTRL+SHIFT+M " para abrir la consola y una vez habierta,
  se tendra que dirigir al apartado "Terminal" en este apartado se podran
  ejecutar distintos comandos y en esta ocacion se ejecutara el comando

  npm Install

  para poder instalar todas las dependencias que contiene.
  un proyecto y por ultimo sera necesario de ejecutar el comando

  npm run dev.

## Guias
Guias de Uso.

En el siguiente enlace se encuentra una pequeña guia de uso detallada
de la forma de uso de la [aplicación...][guia-url]

## contribucion
Agradecimientos especiales a Carlos Saúl Navarro ING.AGR por su
gran contribución de conocimientos impartidos de manera virtual
por medio de su contenido publicado en la plataforma Youtube.

El contenido se puede consultar en el siguiente [enlace...][contribucion-url]

## Licencia
Licencia.

## Contacto
•	Kevin Leonel --Email: kevorvs@gmail.com Tel: 418-113-2739

•	Cristian Israel --Email: bukigem84@gmail.com Tel: 418-100-2177

•	Oscar Arturo --Email: oscargr4824@gmail.comTel: 418-111-8023

•	Alfonso --Email:h hell.faith2238@gmail.com Tel: 418-114-1557
## Participantes
•Kevin Leonel Valdez Sánchez

•Cristian Israel Buclón Pedroza

•Oscar Arturo Guajardo Robles

•Alfonso Alberto Ferro Bortolotti

[organigrama-url]:https://utng.atlassian.net/jira/software/projects/GEO/boards/2/backlog?selectedIssue=GEO-31
[gantt-url]:https://docs.google.com/spreadsheets/d/1rkuLsl1tamH4W2bh5Htx5j1Fur-tqTLR/edit?usp=sharing&ouid=100668929262925714548&rtpof=true&sd=true
[estandar-url]:https://drive.google.com/file/d/1J9REbqCNSdwR_MSIuLWJEpHEJjOjOS7I/view?usp=sharing
[pruebas-url]:https://drive.google.com/file/d/1w-Delo3tBvYU2E1_9CYL-5U-wUfp85uW/view?usp=sharing
[guia-url]:https://drive.google.com/file/d/1nq5cdg5AnpFfz82L2ZEOYj9CVCnVIf0b/view?usp=sharing
[contribucion-url]:https://www.youtube.com/channel/UCX2SmNiGKRq9wZRN85RHHBA
[Casos-url]:https://user-images.githubusercontent.com/88465297/160028834-069438fd-fc61-491c-815d-2b4bc9d9b2e6.png
[Modelo-url]:https://user-images.githubusercontent.com/88465297/160037552-2d8b33e8-7818-41e3-859b-9be4db7a10e1.jpg
[Componente-url]:https://user-images.githubusercontent.com/88465297/160040322-6561d39b-9d99-4f52-9e9f-767c9acb3c29.png


