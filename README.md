# WhatsAPI

Interfaz de WhatsApp Messenger

**Proyecto original de [venomous0x WhatsAPI](https://github.com/venomous0x/WhatsAPI)**
**[shirioko](https://github.com/shirioko)**

Soporte en español de WhatsAPI, ejemplos básicos, etc...

**NOTA:** En la wiki puedes encontrar una guía básica para empezar a usar la API, cualquier otro tipo de dudas/problemas en la sección de issues. En la wiki también podrás encontrar la manera correcta de poner código en los posts de la sección issues.

**--> Antes de preguntar, echad un ojo a la [wiki](https://github.com/mgp25/WhatsAPI-Spanish/wiki)**

- **[WA Tools](http://watools.es):** Un servicio gratuito donde podreis comprobar las funcionalidades de la API, a parte, podreis mandar mensajes anónimos, mensajes multimedia (imágenes y música), ver perfiles y última conexión incluso si la persona lo tiene en 'no visible para los demas', obtener tu contraseña de WhatsApp, comprobar si tu cuenta esta bloqueado y mucho más :)

----------

### Nota 15 de Marzo, 2014

El repositorio oficial de WhatsAPI vuelve estar activo tras la petición DCMA [DCMA takedown](https://github.com/github/dmca/blob/master/2014-02-12-WhatsApp.md).

### Nota 30 de Julio, 2013
*Nueva política en los repositorios de WhatsAPI:*

*No damos soporte a los usuarios que intentan mandar mensajes masivos con esta API(Por ejemplo, mandando muchos mensajes en vez de utilizar la herramienta bulk.php que esta en el repositorio).*
*Mandar anuncios por WhatsApp va directamente en contra de su política (EULA) y no sabemos cuando un usuario va a mandar spam, mandar mensajes masivos, etc.*
*Tampoco voy a perder tiempo en descubrir/hacer métodos para destruir esta preciosa plataforma libre de anuncios/publicidad, algo insegura, pero al menos no tiene publicidad.*
*Todo el mundo tiene la libertad de usar esta API, pero no habrán más mensajes/reportes sobre bloqueo después de haber mandado mensajes a usuarios aleatorios*

*En las famosas palabras de Heath Ledger interpretando Joker (sacado completamente de contexto por mi):*

**El dinero es lo de menos, lo que importa es mandar un mensaje**

*\- [shirioko](https://github.com/shirioko)*

----------

### Nota 14 de Julio, 2013
*Eventos renombrados:*
- *Una gran cantidad de eventos han sido renombrados para un mejor entendimiento con los nuevos nombres de los métodos/funciones.*
- *Todos los nombres de los eventos y parámetros están listados en el archivo EVENTS.md*


----------

### Nota Julio 10, 2013
*Otro cambio importante en el código*
- *SE HAN RENOMBRADO CASI TODOS LOS MÉTODOS!! El antiguo código ya no funcionará, lo lamentamos, pero era necesario una interfaz más limpia. Por favor, mira el nuevo código.*
- *Los métodos han sido renombrados para dar consistencia a la API*
- *Movimiento inicial a aliniar el código con PSR-2 (http://www.php-fig.org/psr/2/)*
- *NO se usa usa IMEI o MAC del dispositivo, repito, NO se usa el IMEI o la MAC del dispositivo.*
- *[La nueva token de Android usada](https://github.com/karolsarnacki/whatsapp/commit/55d8233b852ecd9f6a6f845586e91e6fadbd0c44#L1L20) por WP7 parece que no funciona más. ¿Larga vida al token WP7?*

----------


### Nota Junio 18, 2013

*Especial agradecimiento a:*
- *[Ali Hubail](https://github.com/hubail) y*
- *[Ahmed Moh'd](fb.com/ahmed.mhd) por permitir que este proyecto sea posible*
- *[Jannik Vogel](https://github.com/JayFoxRox) por conseguir el token de WhatsApp, quizás alguien deba escribir un libro sobre eso algún día...*
- *[Tarek Galal](https://github.com/tgalal) por proporcionar las ultimas funciones a yowsup*
- *[Atans](https://github.com/atans) y*
- *[Jonathan Williamson](https://github.com/jonnywilliamson) por diferentes parches*

*\- [shirioko](https://github.com/shirioko)*


----------

### ¿Qué es WhatsApp?
Según [la compañia](http://www.whatsapp.com/):

> “WhatsApp Messenger es una aplicación de mensajería multiplataforma que te permite enviar y recibir mensajes sin pagar por SMS. WhatsApp Messenger está disponible para iPhone, BlackBerry, Windows Phone, Android y Nokia, y todos esos dispositivos pueden comunicarse del uno al otro! Debido a que WhatsApp Messenger usa el plan de datos que ya tienes para email e internet, no hay un coste adicional para enviar mensajes y mantenerte en contacto con tus amigos.
> Además de aprovechar de la mensajería básica, usuarios WhatsApp pueden crear grupos, y enviar entre ellos un número ilimitado de imágenes, videos y mensajes de audio.”

Final del 2011: 1 billon de mensajes cada día, ~20 millones de usuarios.

### XMPP modificado
WhatsApp usa algún tipo de servidor XMPP customizado, llamado internamente FunXMPP, que es básicamente una versión ampliada.

### Procedimiento del login (inicio de sesión)
Como XMPP, WhatsApp utiliza JID (Jabber ID) y una contraseña para entrar con éxito al servicio. La contraseña se genera por el servidor y se recibe al momento del registro.


La JID es una concatenación entre el código del país y el número de móvil.

El inicio de sesión utiliza la autenticación de acceso Digest.

### Enviar Mensaje
Los mensajes se envían básicamente en forma de paquetes TCP, a raíz de un formato propio cd WhatsApp (a diferencia de lo que se define en el RFC XMPP).

Los mensajes son de nivel de aplicación utilizando cifrado RC4 keystreams

### Envío de mensajes multimedia
Fotos, vídeos y archivos de audio compartidos con los contactos WhatsApp se hacen a través de HTTP a un servidor antes de ser enviado al destinatario(s) junto con una miniatura de archivo multimedia codificado en base64 (si es aplicable), junto con el enlace HTTP generado como el cuerpo del mensaje.

### Sistema de eventos
WhatsApi utiliza un gestor de eventos (creada por [Facine] (https://github.com/facine)), que le permite responder a ciertos eventos.

Lista de los eventos y el código de ejemplo sobre cómo enlazar un controlador de eventos:
https://github.com/shirioko/WhatsAPI/wiki/WhatsApi-events

# FAQ


**¿Qué pasa con los caracteres hexadecimales flotantes en todo el código?**

Mayormente caracteres / comandos o datos con formato de control de propiedad de WhatsApp acuerdo a las especificaciones de su servidor, el almacenamiento en los diccionarios predefinidos dentro de los clientes.

**¿Cuál es su plan de desarrollo futuro?**

No tengo ninguno. Generalmente ire investigando por cuenta propia y desarrollando aquello que me parezca más interesante.

**¿Se ejecutará a través de Internet?**

Puedes probar WhatsAppea.me un servicio online que te permite hablar con tus contactos de WhatsApp - [http://whatsappea.me](https://www.whatsappea.me) 

**¿Puedo recibir chats?**

De hecho, utilizando el mismo mecanismo de enchufe-receptor. Pero hay que analizar los datos entrantes. Funciones de análisis no se incluyen en esta versión, tal vez en la próxima?

**Creo que el código es desordenado.**

Está funcionando, ¿no?

**¿Cómo puedo obtener mi contraseña?**

Registre un número usando WhatsAPI o WART (WhatsApp Registration Tool) (creada por [Shirioko] (https://github.com/shirioko))


# NOTA

- El PoC es extensible para contener todas las características y funciones que cualquier usuario dispondría con su versión en el móvil, al igual que los oficiales, en realidad podría ser aún mejor.
- Durante las dos semanas de análisis de los mecanismos de servicio, nos topamos con serios fallos en el diseño y seguridad (que arreglaron algunos de ellos desde 2011). Para una empresa con tal base de usuarios masiva, esperábamos mejores prácticas de ingeniería y seguridad.

# Licencia

MIT


# mgp25

Actualmente desarrollo yo solo, pero sería genial que la gente participase y aportase su granito de arena :)
Trabajo activamente en esta API, muchas de las actualizaciones en este repositorio estan siendo incorparadas a la repo oficial que lleva Shirioko.


# WATools Actualizado 2014

Herramienta online que te permite ver la imagen de perfil, estado y última conexión de una persona, así como mandar mensajes y archivos de manera anónima.

WATools [http://watools.es](https://www.watools.es)

# WhatsApp Tracker

Una utilidad de consola, que permite ver la última hora en línea de cualquier contacto aunque lo tenga oculto o tenga su privacidad oculta para ciertos usuarios. Más información y código en:

[WhatsApp Tracker](https://github.com/mgp25/WhatsApp-Tracker)
