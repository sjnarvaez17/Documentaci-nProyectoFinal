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

![Diseño](https://github.com/leonardoZambranoCifuentes/Documentaci-nProyectoFinal/blob/master/Im%C3%A1genes%20del%20proyecto%20final-%20Aguirre-Lewis-Tiago/Arquitectura%20Soluci%C3%B3n%20final.jpeg)

### Diseño del Orquestador:

![Orquestador](https://github.com/leonardoZambranoCifuentes/Documentaci-nProyectoFinal/blob/master/Im%C3%A1genes%20del%20proyecto%20final-%20Aguirre-Lewis-Tiago/Dise%C3%B1o%20de%20la%20soluci%C3%B3n.jpeg)

### Desarrollo

### Docker-Compose.yml

Docker Compose es una herramienta para definir y ejecutar aplicaciones Docker de múltiples contenedores. Genera scripts que facilitan el diseño y la construcción de servicios o de aplicaciones con múltiples componentes lo que simplifica el uso de Docker. Se puede usar el DockerFile como un bloque de construcción para Docker Compose.

Para el proyecto creamos nuestra propia red, esto se aprecia en la siguiente imagen

![Red Propia](https://github.com/leonardoZambranoCifuentes/Documentaci-nProyectoFinal/blob/master/Im%C3%A1genes%20del%20proyecto%20final-%20Aguirre-Lewis-Tiago/Docker%20compose/Redes.jpeg)

También, se usó la base de datos distribuida MongoDB. Esta base de datos es de uso general, fue diseñada para desarrolladores de aplicaciones modernas y para la era de la nube. En la siguiente imagen podemos ver esto

![Base de Datos](https://github.com/leonardoZambranoCifuentes/Documentaci-nProyectoFinal/blob/master/Im%C3%A1genes%20del%20proyecto%20final-%20Aguirre-Lewis-Tiago/Docker%20compose/Base%20de%20datos%20mongoDB.jpeg)

Se realizó la configuración del Front-End

![](https://github.com/leonardoZambranoCifuentes/Documentaci-nProyectoFinal/blob/master/Im%C3%A1genes%20del%20proyecto%20final-%20Aguirre-Lewis-Tiago/Docker%20compose/Web%20Back-End.jpeg)

![](https://github.com/leonardoZambranoCifuentes/Documentaci-nProyectoFinal/blob/master/Im%C3%A1genes%20del%20proyecto%20final-%20Aguirre-Lewis-Tiago/Docker%20compose/Web%20Front-end.jpeg)

La configuración del proxy para el balanceador de carga en Nginx

![](https://github.com/leonardoZambranoCifuentes/Documentaci-nProyectoFinal/blob/master/Im%C3%A1genes%20del%20proyecto%20final-%20Aguirre-Lewis-Tiago/Docker%20compose/Proxy%20para%20el%20balanceador%20de%20carga-Nginx.jpeg)

También hay que configurar el archivo Nginx.conf, el código se muestra en las siguientes imágenes:

![](https://github.com/leonardoZambranoCifuentes/Documentaci-nProyectoFinal/blob/master/Im%C3%A1genes%20del%20proyecto%20final-%20Aguirre-Lewis-Tiago/C%C3%B3digo%20del%20Nginx%20.jpeg)

![](https://github.com/leonardoZambranoCifuentes/Documentaci-nProyectoFinal/blob/master/Im%C3%A1genes%20del%20proyecto%20final-%20Aguirre-Lewis-Tiago/Nginx%20Conf.jpeg)

