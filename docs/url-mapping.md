### URL Mapping

Para poder ejecutar nuestro código java en un sistema web, necesitamos un servidor Web que pueda 
atender [HttpServletRequests](https://programacion.net/articulo/servlets_basico_108/6) como por 
ejemplo [Tomcat 8+](http://tomcat.apache.org/). Lo que en pocas palabras va a suceder es que el 
servidor va a transformar las [solicitudes HTTP]( https://www.tutorialspoint.com/http/http_requests.htm) 
en llamadas a métodos de java. Para esto necesitamos que de alguna manera se pueda mapear 
un meotodo a una URL, y lo mas importante que podamos pasarle parámetros dinámicos. 

Para esto vamos a hacer uso de una anotación que es @RequestMapping el ejemplo de como lo vamos a usar es el siguiente

```
@RequestMapping(path = "/holaMundo", method = RequestMethod.GET)
public String holaMundo() {
    return "Hola Mundo desde Spring MVC";
}
```
Bien de esta forma lo que veremos por pantalla al poner en el navegador `http://localhost:8080/proyecto-limpio-spring/holaMundo` 
es que se va a llamar al método holaMundo y el navegador va a renderizar la respuesta de este método, en este caso el string “Hola Mundo desde Spring MVC”

> Recordemos que la URL va a depender del puerto que asignamos y la URL base que definimos, la que está aquí es de ejemplo para la que esta predefinida en el proyecto entregado

Ahora bien, nosotros vamos a querer que ese String pueda cambiar dinámicamente. 
Para esto vamos a necesitar pasarle un parámetro. Esto lo logramos pasándole parámetros en 
forma de querystring. Un querystring básicamente es una forma de enviar parámetros utilizando 
el protocolo HTTP, separamos la ubicación de un recurso por ej /holaMundo con un ? de esta forma 
podríamos tener una URL así `http://localhost:8080/proyecto-limpio-spring/hola?nombre=Pedro` esto 
significa que vamos a llamar al método que tenga el mapeo de `hola` con el parámetro `nombre` Pedro.

Para esto utilizaremos una anotación @RequestParam que va a indicar que ese parámetro de nuestro 
método se va a mapear desde la URL con un querystring

##### Caso 1
```
@RequestMapping(path = "/hola", method = RequestMethod.GET)
public String hola(@RequestParam String nombre) {
    return String.Format("Hola %s", nombre);
}
```

##### Caso 2
```
@RequestMapping(path = "/hola", method = RequestMethod.GET)
public String hola(@RequestParam(name="parametroNombre") String nombre) {
    return String.Format("Hola %s", nombre);
}
```
Como se puede ver hay dos formas de mapear el parámetro
* Infiriendolo del nombre que se le dio al parámetro (Caso 1)
* Indicando el nombre especifico del parámetro usando name=”<NOMBREPARAMETRO>”  (Caso 2)


Esto lo conseguimos utilizando la anotación @RequestParam en el parámetro seleccionado, y 
poniendo un detalle mas en el path del @PathVariable, que es encerrar entre llaves el 
parámetro seleccionado quedando nuestro ejemplo algo así.

##### Caso 1
```
@RequestMapping(path = "/hola/{nombre}", method = RequestMethod.GET)
public String hola(@PathVariable String nombre) {
    return String.Format("Hola %s", nombre);
}
```

##### Caso 2

```
@RequestMapping(path = "/hola/{parametroMapeado}", method = RequestMethod.GET)
public String hola(@PathVariable(name= "parametroMApeado") String nombre) {
    return String.Format("Hola %s", nombre);
}
```

Un caso importante es destacar que los parámetros pueden no ser obligatorios, para ello 
solo debemos marcarlos en la anotación que usemos como por ejemplo:

```
@RequestMapping(path = "/hola", method = RequestMethod.GET)
public String hola(@RequestParam(name= "nombre") String nombre, @RequestParam(name= "edad",required = false)Integer edad) {
    return String.Format("Hola %s", nombre);
}
```

###### Referencias:
* [Servlet](https://programacion.net/articulo/servlets_basico_108/6)
* [HTTP Protocl](https://www.tutorialspoint.com/http/http_requests.htm)
* [REST Service](https://www.codigonaranja.com/2018/restful-web-service)
* [RequestMapping](https://www.baeldung.com/spring-requestmapping)
* [RequestParam](https://www.baeldung.com/spring-request-param)
* [Spring Annotations](https://www.baeldung.com/spring-mvc-annotations)