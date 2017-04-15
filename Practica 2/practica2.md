#Redes y comunicaciones - 2017 Practica 2

####Requerimientos
1. _Para realizar esta práctica deberá descargar la máquina virtual provista. Puede ver la URL de descarga
en el sitio de la cátedra en https://catedras.info.unlp.edu.ar/.
Una vez descargado el archivo, haciendo doble click en el mismo debería abrirse un cuadro de diálogo que permita configurar algunos parámetros del sistema. Se pueden aceptar los valores por defecto haciendo simplemente click en Importar. Se recomienda hacer un snapshot de la VM antes de empezar a usarla, para poder volver atrás en caso de que algo deje de funcionar._
_Los datos de acceso a la máquina virtual son:_
	+ _Usuario: redes_
	+ _Contraseña: redes_
	+ _Contraseña root: redes_

####Introduccion
2.  _¿Cuál es la función de la capa de aplicación?_
> + Provee servicios de comunicacion a los usuarios y a las
aplicaciones, incluye las aplicaciones mismas.
> + Interfaz con el usuario(User Interface) u otras
aplicaciones/servicios.
> + Las aplicaciones de red pertenecen a esta capa.
> + Existen aplicaciones que **no** son de red que deben trabajar
con aplicaciones/servicios para lograr acceso a la red.

3. _Si dos procesos deben comunicarse:_
	a. ¿Cómo podrían hacerlo si están en diferentes máquinas?
> Utilizan el intercambio de mensajes a través de la red. El proceso emisor crea y envía los mensajes, y el receptor los recibe y responde si es apropiado hacerlo. Los protocolos de la capa de aplicación definirán el formato y orden en que deben enviarse esos mensajes, y las acciones a tomar en consecuencia a la llegada de un mensaje.	
	
4. _Explique brevemente cómo es el modelo Cliente/Servidor. De un ejemplo de un sistema Cliente/Servidor en la “vida cotidiana” y un ejemplo de un sistema informático que siga el modelo Cliente/Servidor.
¿Conoce algún otro modelo de comunicación?_	
> En la arquitectura Cliente/Servidor un host cliente se comunica con otro, servidor, enviando solicitudes. Los clientes se comunican sólo con el servidor _no entre ellos_, y posiblemente desde IP dinámica -al contrario del servidor, con IP fija-. Es común que un host actúe como cliente y servidor de un servicio, o que haya solicitudes y envío de información en ambas direcciones; en este caso, se denomina cliente al host que comienza la sesión. Ejemplo: Un servidor Web -i.e. Apache- y un browser -i.e. Mozilla Firefox-. Otros modelos de comunicación son: P2P (Peer to Peer, los clientes se comunican entre ellos directamente y posiblemente con un servidor que administra las IP de los clientes conectados) y sistemas híbridos (un servidor coordina algunas tareas y adminsitra las IP cliente, y los clientes se comunican entre ellos tras interactuar con el servidor).

5. _Describa la funcionalidad de la entidad genérica “Agente de usuario” o “User agent”._
> Un user agent es la interfaz entre el usuario final y una aplicación de red (por ejemplo, el browser en el caso de la WEB). Implementa la parte cliente de algunos protocolos de aplicación. 

#####HTTP
6. _¿Qué son y en qué se diferencian HTML y HTTP?_
> + HTML(HyperText Markup Language) es un lenguage el cual se utiliza para la elaboracion de la estructura de una pagina web. Es un estándar que sirve de referencia del software que conecta con la elaboración de páginas web en sus diferentes versiones, define una estructura básica y un código (denominado código HTML) para la definición de contenido de una página web, como texto, imágenes, videos, juegos, entre otros. 
> + HTTP(Hypertext Transfer Protocol) es el protocolo de comunicación que permite las transferencias de información en la World Wide Web. HTTP define la sintaxis y la semántica que utilizan los elementos de software de la arquitectura web (clientes, servidores, proxies) para comunicarse.

7. _Utilizando la VM, abra una terminal. Investigue sobre el comando curl y analice para qué sirven los siguientes parámetros (-I, -H, -X, -s)._
> + **curl -l**: sirve para listar solo nombres cuando se estra trabajando con el portocolo FTP.
> + **curl -H**: sirve para reemplazar un encabezado existente usado por curl al enviar un pedido HTTP a un servidor. Por ejemplo, curl al enviar un pedido HTTP a un servidor uno de sus encabezados es `User-Agent: curl/7.54.0-DEV`, pero si usamos por ejemplo `curl -H "User-Agent: Chrome/56.0"`al servidor le aparecerar que la aplicacion la cual le esta haciendo una peticion es la especificada en el parametro(en este caso un navegador chrome version 56.0).
> + **curl -X**: curl, por defecto, si no se le especifica al hacer un pedido a un servidor mediante HTTP utiliza el metodo GET. Si se quiere utilzar metodos como PUT y DELETE(que son considerados "custom-methods") se necesita especificarle el parametro -X. Ejemplo `curl -X PUT`.
> + **curl -s**: modo silencioso. No muestra barra de progreso o mensajes de error, pero si muestra los datos que se le pidieron.

8. _Ejecute a continuación los siguientes comandos:_
	+ curl -v -s www.redes.unlp.edu.ar > /dev/null
	+  curl -I -v -s www.redes.unlp.edu.ar
	
		+ ¿Qué diferencias nota entre cada uno?
		+ ¿Qué ocurre si en el primer comando quita la redirección a /dev/null? ¿Por qué no es necesaria en el segundo comando?
		+ ¿Cuántas cabeceras viajaron en el requerimiento? ¿Y en la respuesta?

>+ Las diferencias entre ambos es que uno hace un pedido HTTP con el metodo GET y otro con el metodo HEAD(-I). Ademas el primero a diferencia del segundo guarda el resultado del GET en /dev/null.
>+ Si al primer comando se le quita la redireccion a /dev/null imprimira lo que reciba del metodo GET en pantalla. El segundo comando no necesita la redireccion porque al ser un metodo HEAD solo devuelve los encabezados del Cliente y Servidor, y no el cuerpo de la pagina.
> + 4 en el requerimiento y 8 en la respuesta.

9. _Ejecute una vez más el comando curl www.redes.unlp.edu.ar pero sólo muestre los encabezados y luego
responda:_
	**a**. ¿Es posible determinar qué servidor web se utiliza para servir la página?
	**b**. ¿Cuál es el código de respuesta que devolvió el servidor? ¿Qué otros códigos existen y qué significan? Investigue genéricamente los tipos de error 2XX, 3XX, 4XX y 5XX.
	**c**. ¿Cuándo fue la última vez que se modificó la página?
	**d**. Solicite la página nuevamente con curl usando GET, pero esta vez indique que quiere obtenerla sólo si la misma fue modificada en una fecha posterior a la que efectivamente fue modificada. ¿Cómo lo
hace? ¿Qué resultado obtuvo? ¿Puede explicar por qué y para qué sirve?
	**e**. ¿Qué significa el encabezado ETag?

> **a**: si, en el encabezado llamado "Server". En el caso de la web de la catedra, el servidor que se utiliza para servir la pagina es un Apache/2.4.7 (Ubuntu).
>**b**: el servidor devolvio el codigo 200 OK. Otros codigos que podria llegar a devolver serian: 301 Moved Permanently, 400 Bad Request, 403 Access Forbidden, 404 Not Found, 405 Method Not Allowed, 500 Internal Server Error (CGI Error), 501 Method Not Implemented.
>**c**: Last-Modified: Wed, 16 Mar 2016 20:41:34 GMT+3.
>**d**: Con el comando `If-Modified-Since` pasandole como parametro una fecha que sea superior a la recibida en el encabezado `Last-Modified`es posible que el metodo GET devuelva el cuerpo de la pagina solo si la pagina fue modificada despues de la fecha especificada en el parametro de If-Modified-Since, Ejemplo: `curl -H "If-Modified-Since: Wed, 22 Oct 2016 21:54:45 GMT" www.redes.unlp.edu.ar`. El resultado al poner una fecha posterior a la ultima modificada es de que no imprima nada ya que no hubo una modificacion posterior a la fecha indicada.
>**e**: Un ETag es un identificador opaco asignado por un servidor web a una versión específica de un recurso que se encuentra en una URL. Si el contenido del recurso en esa URL cambia, se le asigna un nuevo y diferente ETag.





















