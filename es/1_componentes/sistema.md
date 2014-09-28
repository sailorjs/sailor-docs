# El Sistema

## Sails, el framework de tus sueños

El sistema está basado en [Sails](http://sailorjs.org/), que es framework para NodeJS. Algunas de las características a destacar de este framework son:

* 100% JavaScript
* Base de Datos agnóstica (serialización mediante su propio *ORM*).
* Soporte para *real time* a través de sockets.
* Orientado para la creación de API's.
* Soporte para diversos aspectos de seguridad, tales como *CSRF*, *CORS*, *JSONP*,... ([más información](http://sailsjs.org/#/documentation/concepts/Security)).

Por lo tanto, todo el *how-to* para crear aplicaciones en Sailor está heredado directamente de Sails (definición de rutas, controladores, políticas, servicios,...) y es por ello que si quieres desarrollar para Sailor tendrás que aprender primero cómo lo hace Sails.

Algunas recursos interesantes sobre este aspecto son:

* [Sails.org](http://sailsjs.org/) es su página web y documentación oficial.
* [Sails101](https://github.com/sails101) son casos prácticos donde tratan las dudas más relevantes a la hora de desarrollar.
* [Sailscasts](https://irlnathan.github.io/sailscasts/) es una colección de emisiones donde tratan todos los aspectos que debes saber.

## Sailor, más allá del barco

Como hemos dicho, Sailor está basado en el núcleo de Sails. Por eso te estarás preguntando ahora mismo,.. ¿Qué hace exactamente Sailor?

* Sails es un framework multipropósito. Con **SailorJS** nos centraremos sólo en el backend, por lo que tendrás que utilizar un framework para el frontend de tu aplicación (AngularJS, EmberJS, Backbone, Atoms,...) y conectarlo con la librería **sailor-client**.

* **SailorJS** extiende Sails para soportar algunas otras cosas que Sails no soporta de serie, como el sistema de módulo o el sistema de traducción propio.

Puedes ver **SailorJS** como *high level* por encima de Sails, que define la manera de encapsular código. Te recomendamos leer la sección **Módulos** y **Guía de estilo** para obtener una visión más definida.

## Componentes internos

Además del núcleo de [Sails](http://sailorjs.org) el sistema proporciona algunas extensiones adicionales que debes tener en cuenta a la hora de desarrollar, pues no sólo forman parte de la **guía de estilo** para desarrollar módulos en Sailor, sino que te hará el proceso mucho más fácil:

* **sailor-translate** proporciona multidioma para las respuestas del servidor.
* **sailor-validator** valida parámetros en las solicitudes a tu servidor.
* **sailor-errorify** la serialización de los mensajes para que estén bien formateado en el lado del cliente.

Como ves, los tres módulos están altamente relacionados: usaremos errorify para serializar validaciones que se apoyará en translate para obtener los mensajes en diferentes idiomas.

Cada componente interno tiene su análogo en un módulo para que puedas utilizarlo cómodamente. Te recomendamos visitar la sección **Módulos por defecto** y **Guía de Estilo** para tener más información.
