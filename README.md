# Encabezado Principal

### Integrantes del Equipo

* Carl Lewis Ochoa Álvarez - A00310516
* Andres Aguirre - A00329792
* Leonardo Zambrano Cifuentes - A00027552.
* Santiago Narvaez Prado - A00027544.

### Objetivos

* Diseñar la arquitectura de un sistema distribuido que implemente un conjunto de microservicios, considerando las implicaciones técnicas asociadas con su escalabilidad, tolerancia a fallos y concurrencia, y las mejoras en el desempeño a través de la asignación o reasignación de los recursos y tareas.

* Desplegar un sistema distribuido, teniendo en cuenta las estrategias de administración de sus recursos consideradas en el diseño.

* Gestionar el servicio distribuido, haciendo uso de herramientas de monitoreo y provisionamiento

### Diseño de la solución:

Siguiendo los pasos del método de la ingeniería y el proceso de despliegue de software, procedemos al diseño de nuestra solución. En la siguiente imagen, podemos observar que proponemos en la parte superior un balanceador de cargas, el cual cumplirá con las funciones de un proxy, con los cuales se comunicarán cada uno de los módulos correspondientes al Front-End(web). Se podrán tener varios módulos web, donde un usuario final podrá interactuar con los microservicios implementados y a su vez, estos se encontrarán comunicados con una base de datos, el cual almacenará toda la información que se obtenga y con la cual se inicializaran los datos en el Back-End.

[imagen de diseño]

![Diseño](https://github.com/leonardoZambranoCifuentes/Documentaci-nProyectoFinal/blob/master/Im%C3%A1genes%20del%20proyecto%20final-%20Aguirre-Lewis-Tiago/Arquitectura%20Soluci%C3%B3n%20final.jpeg)

### Diseño del Orquestador:

![Orquestador](https://github.com/leonardoZambranoCifuentes/Documentaci-nProyectoFinal/blob/master/Im%C3%A1genes%20del%20proyecto%20final-%20Aguirre-Lewis-Tiago/Dise%C3%B1o%20de%20la%20soluci%C3%B3n.jpeg)

### Desarrollo

### Docker-Compose.yml

Docker Compose es una herramienta para definir y ejecutar aplicaciones Docker de múltiples contenedores. Genera scripts que facilitan el diseño y la construcción de servicios o de aplicaciones con múltiples componentes lo que simplifica el uso de Docker. Se puede usar el DockerFile como un bloque de construcción para Docker Compose.

Para el proyecto creamos nuestra propia red, esto se aprecia en la siguiente imagen

![Red Propia](https://github.com/leonardoZambranoCifuentes/Documentaci-nProyectoFinal/blob/master/Im%C3%A1genes%20del%20proyecto%20final-%20Aguirre-Lewis-Tiago/Docker%20compose/Redes.jpeg)

También, se usó la base de datos distribuida MongoDB. Esta base de datos es de uso general y es no relacional, fue diseñada para desarrolladores de aplicaciones modernas y para la era de la nube. Los parametros para su configuración son el puerto, la red a la cual pertenece, en este caso pertenece a la creada por nosotros que recibe por nombre "app-network", el nombre del contenedor y su respectiva imagen. En la siguiente ilustración podemos ver la configuración implementada para su despliegue en uno de los contenedores.

![Base de Datos](https://github.com/leonardoZambranoCifuentes/Documentaci-nProyectoFinal/blob/master/Im%C3%A1genes%20del%20proyecto%20final-%20Aguirre-Lewis-Tiago/Docker%20compose/Base%20de%20datos%20mongoDB.jpeg)

Se realizó la configuración del Back-End, donde se especifica la red en donde se va a encontrar y los puertos que nos van a permitir establecer comunicación con dichos recursos, los cuales corresponden al 3000:3000 (host:contenedor). Si accedemos a localhost:3000 vamos a observar cada uno de los objetos en formato JSON, que se encuentran almacenados en la base de datos.

![](https://github.com/leonardoZambranoCifuentes/Documentaci-nProyectoFinal/blob/master/Im%C3%A1genes%20del%20proyecto%20final-%20Aguirre-Lewis-Tiago/Docker%20compose/Web%20Back-End.jpeg)

En la siguiente imagen, se visualiza la configuración que se realizó para que se realizara comunicación entre el back y el front. Para esto, se configura en el parámetro 'depends_of' con 'aik-app-api', con la intencion dar la instrucción que éste servicio podrá desplegarse solamente si ya está desplegado el back, ya que a partir de éste ultimo se actualizarán los componentes gráficos configurados. Es importante destacar el parámetro "scale", donde se indica que existirán dos instancias de éste servicio (replicación)
![](https://github.com/leonardoZambranoCifuentes/Documentaci-nProyectoFinal/blob/master/Im%C3%A1genes%20del%20proyecto%20final-%20Aguirre-Lewis-Tiago/Docker%20compose/Web%20Front-end.jpeg)

La configuración del proxy para el balanceador de carga en Nginx

![](https://github.com/leonardoZambranoCifuentes/Documentaci-nProyectoFinal/blob/master/Im%C3%A1genes%20del%20proyecto%20final-%20Aguirre-Lewis-Tiago/Docker%20compose/Proxy%20para%20el%20balanceador%20de%20carga-Nginx.jpeg)

También hay que configurar el archivo Nginx.conf, el código se muestra en las siguientes imágenes:

![](https://github.com/leonardoZambranoCifuentes/Documentaci-nProyectoFinal/blob/master/Im%C3%A1genes%20del%20proyecto%20final-%20Aguirre-Lewis-Tiago/C%C3%B3digo%20del%20Nginx%20.jpeg)

![](https://github.com/leonardoZambranoCifuentes/Documentaci-nProyectoFinal/blob/master/Im%C3%A1genes%20del%20proyecto%20final-%20Aguirre-Lewis-Tiago/Nginx%20Conf.jpeg)





