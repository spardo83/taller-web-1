### ¿Qué es MVC?

MVC Modelo-Vista-Controlador (Model-View-Controller) corresponde a un patrón de arquitectura de 
software cuya intención es separar los datos de la lógica de negocio, tiene su origen como idea en 
la década del 70 mucho antes de que la web existiera y su aplicación general en la **década del 80**. 
Esto es importante de destacar para poder separar la spring o cualquier otro framework que 
utilice el patrón del concepto en sí.
En este patrón podemos ver tres objetos claramente definidos que actúan en conjunto

* **Controlador**: Acepta las entradas y las convierte en comandos para el modelo o la vista
* **Vista**: Es la representación de la información, cualquiera sea esta. (Recordemos que MVC no se limita a la web)
* **Modelo**: Es el componente central del patrón, es la estructura de datos independiente de la interfaz de usuario.

Ahora bien, en spring vamos a utilizar este patrón de arquitectura, pero adaptado a la web, por lo que la interacción seria como la de la imagen ->

![Grafico MVC](https://github.com/spardo83/taller-web-1/docs/assets/mvc-graphic.png)

Referencias:
* [Wikipedia (Ingles)](https://en.wikipedia.org/wiki/Model%E2%80%93view%E2%80%93controller)
* [Wikipedia (Espeañol)](https://es.wikipedia.org/wiki/Modelo%E2%80%93vista%E2%80%93controlador)
* [Spring MVC](https://docs.spring.io/spring/docs/current/spring-framework-reference/web.html)
