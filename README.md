# Inglés API-Cation

La aplicación Inglés API-cation tiene como objetivo principal la traducción de palabras en inglés al idioma español. Se mostrarán ejemplos de oraciones de uso de la palabra; además, si la palabra a traducir es un verbo, se mostrará las diferentes conjugaciones del mismo. 

La aplicación entiende que el idioma inglés no se traduce de forma literal, por lo que muestra diferentes estilos y ejemplos de traducciones. Estos estilos son consumidos por otras API realizadas por terceros. 

Ingles API-cation, muestra una interfaz amigable con el usuario, para que sea sencillo de usar y muy útil; cumpliendo con todas las expectativas del usuario final.


## Iniciando

### Pre-requisitos

* Ubuntu Server 18.04 LTS
* PHP 7.x
* Mysql 
* Composer
* Framework CakePHP 4.x

### Instalación

El proyecto Inglés API-cation se implementó en un Ubuntu Server, en este servidor se instalaron todos los pre-requisitos indicados en el punto anterior, para poder probar y/o modificar nuestro proyecto, debes descomprimirlo en tu propio servidor o máquina local.

Cuando empieces a probar el proyecto, lo más probable es que te aparezcan los siguientes warnings:

```
Warning(512): projectroot/tmp/cache/persistent is not writable 
Warning(512): projectroot/tmp/cache/models is not writable
```

```
Warning(2): Cannot modify header information - headers already sent by (output started at
projectroot/vendor/cakephp/cakephp/scr/Error/Debugger.php)
```

Ambos warnings se deben a permisos del usuario al momento de descomprimir el proyecto en el nuevo servidor o computadora local. Estos warnings se solucionan con los siguientes comandos:

```
sudo chown 'nombredeusuario':www-data -R tmp/
```

```
chmod g+w -R tmp/
```
## Arquitectura

<a href="https://imgur.com/MDgBf0N"><img src="https://i.imgur.com/MDgBf0N.jpg" title="source: imgur.com" /></a>

* **index.php:** Archivo índice que llama al método autoloader().
* **Autoloader:**  Esta clase se encuentra en la carpeta vendor/composer. Se encarga de cargar todas las clases y librerías al comienzo de la ejecución del código.
* **Load Application & bind to HttpServer:** Como siguiente paso, se carga la aplicación web, y se enlaza a nuestro servidor web o servidor HTTP. El estándar HTTP define dos tipos de mensajes: Request y Response.
* **Middleware:** El middleware utilizado será el PSR-7 que es el que usa el framework CakePHP. PSR-7 propone que Request y Response sean inmutables.
* **Controller:** Carpeta creada en src/. Se accede a ella después de que el haya habido respuesta del middleware. Esta, se conecta con e la capa del modelo. 
* **Component:** Son las clases que vamos a implementar para consumir las apis de nuestros compañeros
* **Model:** El modelo contendrá las tablas y entidades que se van a consumir de la base de datos 
* **View:** El componente vista es el encargado de mostrar las respuestas que obtiene del controlador, nuevamente mediante el middleware PSR-7, ahora con el Response, mostramos la petición al usuario final de forma amigable.

## Metodología SCRUM

Para el proyecto se utilizó la metodología SCRUM, junto con Kanvas para realizar las historias de usuario. El proyecto adaptó esta metodología y la plasmó en un tablero TRELLO (https://trello.com/b/FYblIVxF). Únicamente los miembros del tablero pueden verlo y modificarlo, sin embargo, mostramos como es que se desarrolló hasta el primer Sprint.

<a href="https://imgur.com/KpOHpcj"><img src="https://i.imgur.com/KpOHpcj.png" title="source: imgur.com" /></a>


## Autores

* **Diego Añazco** - *Estudiante de Ing. Software - Universidad La Salle* 
* **María Pinto** - *Estudiante de Ing. Software - Universidad La Salle* 
* **Luis Flores** - *Estudiante de Ing. Software - Universidad La Salle* 
* **Ángel Astorga** - *Profesor de Ing. Software - Universidad La Salle* 

## Licencia

Este proyecto esta licenciado por...

## Agradecimientos

* Agredecemos a la Universidad La Salle - Arequipa, por brindarnos la oportunidad de diseñar la aplicación.

