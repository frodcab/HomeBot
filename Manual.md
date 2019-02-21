Manual
#
Bienvenido al breve manual que vamos a seguir para generar el bot

En primer lugar necesitaremos configurar el elemento que recibe la información de telegram. Para ello necesitaremos un token valido que tneemos que obtener a traves de @botfahter en telegram. Tras recopilar la información, nos dará los datos necesarios para poder utilizar el bot.

A continuación, tras haber obtenido el token, nos vamos a nuestro node-red (http://ipRaspberryVirtual:1880) y genramos un notod Telegram Receiver. Tras configurarlo aparecerá como en la imagen

![Imagen del nodo de receiver](https://raw.githubusercontent.com/frodcab/HomeBot/master/imgs/Receiver.PNG) 

como puedes ver, en la imagen hemos incluido un nuevo nodo, Authorized?. El nodo nos permite revisar quien es el destinatario del mensaje para actuaer en consecuencia. Es decir, nos da la opcion d econvertir este bot en un bot privado.

A continuación vamos a generar una respuesta. Para poder responder necesitamos un nodo Sender. Como ya hemos configurado nuestro bot de telegram para funcionar con Node-Red, la configuración es sencilla, simplemente implementamos el mismo bot que en el receiver.

![Imagen del nodo de sender](https://raw.githubusercontent.com/frodcab/HomeBot/master/imgs/Sender.PNG) 

Una vez que somos capaces de contestar a un mensaje, vamos a añdir un nodo "topic". Este nodo nos va a permitir tener conversaciones, ya que mantiene una temática comun cuando nosotros la fijamos. Además, mediante el nodo "rules" vamos a separar la logica que se refiere a los comandos y la conversaión propiamente dicha

![Imagen del nodo de topic](https://raw.githubusercontent.com/frodcab/HomeBot/master/imgs/Topic.PNG) 

Como todos conocemos, los bots de telegran tipicamente se guian por comandos. Los comandos son palabras precedidas por el caracter "/", donde a continuación del propio comando aparece, o no, información complementaria para realizar la orden. Un ejemplo sencillo sería "/apaga luces" frente a "/apaga horno". 

![Imagen del nodo de comandos](https://raw.githubusercontent.com/frodcab/HomeBot/master/imgs/Comands.PNG) 

Finalmente, para poder mantener una conversación, nos apoyamos en el nodo "ecolect" que permite emplear extracción sintáctica sobre frases definidas, de manera que podemos contruir sencillas respuestas a preguntas y añadir inteligencia a medida que ampliamos las ramas del árbol de decisión. El nodo inicial aparecería así:

![Imagen del nodo de ecolect](https://raw.githubusercontent.com/frodcab/HomeBot/master/imgs/ecolect.PNG) 

A medida que hagamos crecer este árbol, mayor será la inteligencia (y la complejidad!) de nuestro bot. Para mantenerlo lo más sencillo posible, es importante que dentro de los ámbitos de una conversación empleemos los topic, de manera que siempre sepamos "de lo que nos está hablando" el usuario cuando responde a una pregunta, es decir, nunca perdamos el contexto.




