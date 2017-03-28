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
