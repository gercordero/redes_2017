# Redes y comunicaciones - 2017 Practica 1

1. _¿Qué es una red? ¿Cuál es el principal objetivo para construir una red?_
> Una red de computadoras es un grupo de computadoras/dispositivos interconectados. El objetivo de formar un red de computadoras es el de compartir recursos: dispositivo, información, servicios.

2. _¿Qué es Internet? Describa los principales componentes que permiten su funcionamiento._
> Internet es un conjunto descentralizado de redes de computadoras que utilizan la familia de protocolos TCP/IP, lo cual garantiza que las redes físicas heterogéneas que la componen formen una red lógica única de alcance mundial.
Los principales componentes que permiten el funcionamiento de Internet son:
  + Computadoras, en el modelo de Internet: Hosts (PCs, Laptops, Servidores).
  + Routers, switches, Gateways, Acces Points.
  + Placas de red, Modems.
  + Vínculos / Enlaces conformados por: cables, fibras ópticas, señales electromagnéticas, antenas, interfaces, etc.
  + Programas: Browsers, Servidores web, Clientes de Mail, Servidores de Streaming, etc.

3. _¿Qué son las RFCs?_
  > Request for Comments (RFCs abreviado) son una serie de publicaciones del grupo de trabajo de ingeniería de Internet que describen diversos aspectos del funcionamiento de Internet y otras redes de computadoras, como protocolos, procedimientos, etc. Cada RFC constituye un monográfico o memorando que ingenieros o expertos en la materia han echo llegar al IETF.

4. _¿Qué es un protocolo?_
  > Un protocolo es un conjunto de reglas que especifican el intercambio
  de datos u ordenes durante la comunicación entre las entidades que forman parte de una red. Permiten la comunicación y están implementados en las componentes. Un protocolo define el formato, el orden de los mensajes y las acciones que se llevan a cabo en la transmisión y/o recepción de un mensaje o evento.

5. _¿Por qué dos máquinas con distintos sistemas operativos pueden formar parte de una misma red?_
> Pueden formar parte de la misma red gracias a los protocolos.

6. _¿Cuáles son las 2 categorías en las que pueden clasificarse a los sistemas finales o End Systems? Dé un
ejemplo del rol de cada uno en alguna aplicación distribuida que corra sobre Internet._
> Las dos categorias son: cliente y servidor. Un ejemplo de rol del lado del servidor es: un servidor Apache, o un servidor Web y del lado del cliente un browser.

7. _¿Cuál es la diferencia entre una red conmutada de paquetes de una red conmutada de circuitos?_
> La conmutación de paquetes es un método de envío de datos en una red de computadoras. Un paquete es un grupo de información que consta de dos partes: los datos propiamente dichos y la información de control, que indica la ruta a seguir a lo largo de la red hasta el destino del paquete. Existe un límite superior para el tamaño de los paquetes; si se excede, es necesario dividir el paquete en otros más pequeños, por ej. Ethernet usa tramas (frames) de 1500 bytes, mientras que FDDI usa tramas de 4500 bytes.
  + Los paquetes forman una cola y se transmiten lo más rápido posible.
  + Permiten la conversión en la velocidad de los datos.
  + La red puede seguir aceptando datos aunque la transmisión sea lenta.
  + Existe la posibilidad de manejar prioridades (si un grupo de información es más importante que los otros, será transmitido antes que dichos otros).
  ![comutacion_de_paquetes](https://cloud.githubusercontent.com/assets/13878860/24382175/e3b0742e-1354-11e7-9288-7d7e9c00239c.gif)
 > La conmutación de circuitos es un tipo de conexión que realizan los diferentes nodos de una red para lograr un camino apropiado para conectar dos usuarios de una red de telecomunicaciones. A diferencia de lo que ocurre en la conmutación de paquetes, en este tipo de conmutación se establece un canal de comunicaciones dedicado entre dos estaciones. Se reservan recursos de transmisión y de conmutación de la red para su uso exclusivo en el circuito durante la conexión. Ésta es transparente: una vez establecida parece como si los dispositivos estuvieran realmente conectados.

8. _Analice qué tipo de red es una red de telefonía y qué tipo de red es Internet._
>Una red de telefonía es una red de conmutación de circuitos y Internet es una red de conmutación de paquetes.

9. _¿Qué ventajas tiene una implementación basada en capas o niveles?_
> A principio de los 80' las compañı́as comenzaron a
implementar redes propias (privadas y cerradas). Estas fueron las primeras redes propietarias las cuales tenian sus propias especificaciones (protocolos), esto hacia que fueran incompatibles entre si, complejas y que la evolucion de las mismas fuese lenta. Por este motivo se creo el modelo de capas mejor conocido como Layering cuya funcion es dividir la complejidad en componentes reusables.
En cuestion el Layering brinda los siguientes beneficios:
  + Reduce complejidad en componente más pequeñas.
  + Las capas de abajo ocultan la complejidad a las de arriba,
abstracción.
  + Las capas de arriba utilizan servicios de las de abajo:
Interfaces, similar a APIs.
  + Los cambios en una capa no deberı́an afectar a las demás
si la interfaz se mantiene.
  + Facilita el desarrollo, evolución de las componentes de red
asegurando interoperabilidad.
  + Facilita aprendizaje, diseño y administración de las redes.

10. _¿Cómo se llama la PDU de cada una de las siguientes capas: Aplicación, Transporte, Red y Enlace?_


  |Capa      |PDU                   |
  |----------|:---------------------|
  |Aplicacion|Aplication byte stream|
  |Transporte|TCP Segment           |
  |Red       |IP Datagram           |
  |Enlace    |Ethernet Frame        |

11. _¿Qué es la encapsulación? Si una capa realiza la encapsulación de datos, ¿qué capa del nodo receptor
realizará el proceso inverso?_
>Encapsulación es un método de diseño modular de protocolos de comunicación en el cual las funciones lógicas de una red son abstraídas ocultando información a las capas de nivel superior.

12. _Describa cuáles son las funciones de cada una de las capas del stack TCP/IP o protocolo de Internet._


  |Capa      |Funcion                                               |
  |----------|:-----------------------------------------------------|
  |Aplicacion|Servicios de red a los usuarios, a procesos y aplicaciones. Tambien representacion de datos y encripcion.       |
  |Transporte|Conexion entre terminales y fiabilidad.               |
  |Red       |Determinacion de camino y IP (Direccionamiento logico)|
  |Enlace    |Comunicacion entre entes directamente conectados. Comunicar una misma red. Acceso al Medio. |
  |Fisica    |Transportar la informacion como señal por el medio fisico. Caracteristicas fisicas. Informacion binaria, digital.            |

13. _Compare el modelo OSI con la implementación TCP/IP._

  `Modelo de capas OSI:`


  |Capa        |Funcion                                               |
  |------------|:-----------------------------------------------------|
  |Aplicacion  |Servicios de red a los usuarios y a procesos, aplicaciones.                                                       |
  |Presentacion|Representacion de datos y encripcion (formato de los datos.)                                                             |
  |Sesion      |Comunicacion entre hosts (mantener track de sesiones de la aplicacion.)                                                     |
  |Transporte  |Conexion entre terminales y fiabilidad.               |
  |Red         |Determinacion de camino y IP (Direccionamiento logico)|
  |Enlace      |Comunicacion entre entes directamente conectados. Comunicar una misma red. Acceso al Medio.                           |
  |Fisica      |Transportar la informacion como señal por el medio fisico. Caracteristicas fisicas. Informacion binaria, digital.      |


>Similitudes:
  + Ambos se dividen en capas.
  + Ambos tienen capas de aplicación, aunque incluyen servicios
  + distintos.
  + Ambos tienen capas de transporte similares.
  + Ambos tienen capa de red similar pero con distinto nombre.
  + Se supone que la tecnologı́a es de conmutación de paquetes
  (no de conmutación de circuitos).
  + Es importante conocer ambos modelos.

>Diferencias:
  + TCP/IP combina las funciones de la capa de presentación y de
sesión en la capa de aplicación.
  + TCP/IP combina la capas de enlace de datos y la capa fı́sica
del modelo OSI en una sola capa.
  + TCP/IP más simple porque tiene menos capas.
  + Los protocolos TCP/IP son los estándares en torno a los cuales
se desarrolló Internet, de modo que la credibilidad del modelo
  + TCP/IP se debe en gran parte a sus protocolos.
  + El modelo OSI es un modelo “más” de referencia, teórico,
aunque hay implementaciones.


# Extra

#### Explicacion mas detallada sobre el encapsulamientos
*Suponiendo que una persona envia a otra un mail los pasos de encapsulamiento en el model TCP/IP serian los siguientes:*

  1\. *Crear los datos* (Capa de Aplicacion).

  >Cuando un usuario envía un mensaje de correo electrónico, sus caracteres alfanuméricos se convierten en datos que puedan recorrer la red. Si es necesario, la capa de presentación recodifica el mensaje para que pueda ser entendido en el otro extremo.

  2\. *Dividir los datos para ser transportados deextremo a extremo* (Capa de Transporte).

  >Los datos del usuario se dividen para ser transportados por la red. Esta función la realiza la capa de transporte. Cada fragmento que crea esta capa se denomina segmento. Cada segmento incluye una información de control específica del protocolo que se este usando en esta capa.

  3\. *Agregar la dirección de red al encabezado* (Capa de Red).

  >La capa de red hace que un segmento se coloque en uno o varios
paquetes o datagramas, que contienen el encabezado de red con las direcciones del host origen y del host destino. Estas direcciones ayudan a los dispositivos de red a enviar los paquetes a través de la red por una ruta seleccionada.

  4\. *Agregar la dirección local al encabezado de enlace de datos* (Capa de Enlace).

  >Cada dispositivo debe poner el paquete dentro de una trama, función de la que se encarga la capa de enlace. La trama tendrá como destinatario el más próximo dispositivo de red conectado directamente en el enlace.

  5\. *Realizar la conversión a bits para su transmisión* (Capa Fisica).

  >La trama por fin debe convertirse en un patrón de unos y ceros (bits) para su transmisión a través del medio (por lo general un cable).

  ![encapsulamiento](https://cloud.githubusercontent.com/assets/13878860/24420003/8dd98c96-13f1-11e7-823d-606fd39f5e4c.jpg)
