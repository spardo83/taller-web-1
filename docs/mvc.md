### �Qu� es MVC?

MVC Modelo-Vista-Controlador (Model-View-Controller) corresponde a un patr�n de arquitectura de 
software cuya intenci�n es separar los datos de la l�gica de negocio, tiene su origen como idea en 
la d�cada del 70 mucho antes de que la web existiera y su aplicaci�n general en la **d�cada del 80**. 
Esto es importante de destacar para poder separar la spring o cualquier otro framework que 
utilice el patr�n del concepto en s�.
En este patr�n podemos ver tres objetos claramente definidos que act�an en conjunto

* **Controlador**: Acepta las entradas y las convierte en comandos para el modelo o la vista
* **Vista**: Es la representaci�n de la informaci�n, cualquiera sea esta. (Recordemos que MVC no se limita a la web)
* **Modelo**: Es el componente central del patr�n, es la estructura de datos independiente de la interfaz de usuario.

Ahora bien, en spring vamos a utilizar este patr�n de arquitectura, pero adaptado a la web, por lo que la interacci�n seria como la de la imagen ->

![Grafico MVC](https://github.com/spardo83/taller-web-1/docs/assets/mvc-graphic.png)

Referencias:
* [Wikipedia (Ingles)](https://en.wikipedia.org/wiki/Model%E2%80%93view%E2%80%93controller)
* [Wikipedia (Espea�ol)](https://es.wikipedia.org/wiki/Modelo%E2%80%93vista%E2%80%93controlador)
* [Spring MVC](https://docs.spring.io/spring/docs/current/spring-framework-reference/web.html)
