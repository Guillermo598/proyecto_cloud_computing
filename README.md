# Proyecto Cloud Computing
### Integrantes:
Guillermo Franco y Diego Linares

## Introducción

El próposito del Proyecto Final del Curso de Cloud Computing es demostrar el funcionamiento de un aplicativo de microservicios que sea *deployeable* en la nube. A este fin, proponemos hacer pruebas con este modelo para entender el funcionamiento de cada uno de sus componentes en un ambiente correspondiente a Cloud Computing. Robot-Shop es un repositorio de desarrollo demostrativo en el que se puede observar el trabajo de una aplicación multi-container. Este permite correrse en diferentes ambientes, en nuestro caso, Kuvernetes, para observar el funcionamiento de cada uno de los componentes de la misma. 

## ¿Por qué elegimos este Proyecto?

Hay 2 razones principales por las cuales consideramos el uso de una aplicación como un proyecto ideal. En primer lugar, la diversa cantidad de técnicas que utiliza. En casos actuales es esperable que las soluciones de Cloud no se limiten a un único tipo de trabajo. Por ende, creemos que este es un reflejo más fiel de lo que se puede lograr al aplicar múltiples técnicas en un ambiente en la nube.

En segundo lugar, el repositorio permite funcionar como un *sandbox* en el cual se puede probar diferentes experimentos de monitoreo. Esta cantidad de libertad nos permite dejar de lado los diferentes puntos de implementación y enfocarnos más en los efectos de diferentes pruebas en el *deployment*. 

## ¿Cómo lo vamos a medir?
Se optó por utilizar la plataforma de Google Cloud. Esta tiene soporte nativo de Kubernetes, y es muy útil para visualizar todas las métricas deseadas. 

![image](https://user-images.githubusercontent.com/38139707/178636104-328bd6b8-d321-43e7-9103-3557a5b52f5a.png)

Utilizamos un Dockerfile proveido por el autor, que permite crear usuarios y simular compras. El script se modifico para que reciba los parametros que deseamos, y apunte al ip del cluster.

![image](https://user-images.githubusercontent.com/38139707/178636085-91966265-5b98-44d8-a90a-d6eb2dd9388d.png)

Estos son los servicios que son creados por la aplicación. A cada uno se le agregó un Horizontal Pod Autoscaler, a travez de la plataforma, para que replique los pods de acuerdo a la métrica deseada. 

![image](https://user-images.githubusercontent.com/38139707/178636066-90a2887f-777b-4a67-8ec1-def8f38b7d6d.png)

Por último, se creó un dashboard con algunas de las métricas del cluster. Se mide la utilización de los CPUs de cada nodo, y la memoria y cpu por cada servicio. 

### Referencias
* https://github.com/instana/robot-shop
