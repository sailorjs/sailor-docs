# Guía de estilo

## Cuida el esquema de tu API

Puesto que el diseño de los módulos lo haremos basándonos en el diseño de API's RESTful deberás comprender e interiorizar cómo funciona REST y cual debe ser el patrón de acceso, utilizar correctamente los verbos, ...

Si quieres aprender más sobre cómo crear API's RESTful en NodeJS te recomendamos el siguiente recurso de [Node.js Madrid Meetup (sólo español)](http://files.meetup.com/9727852/Desarrollo%20de%20APIs%20RESTful%20con%20NodeJS.pdf).

Algunas de las pautas básicas que todos los módulos deben soportar son:

* Utilizamos la *feature* principal que queremos soportar con nuestro módulo como punto de partida de la API. Si, por ejemplo, estamos desarrollando un módulo de usuarios, el punto de partida será `http://host:port/**user**`. Por convenio utiliza siempre un sustantivo en **forma singular**.

* Siempre que necesitemos discriminar un recurso de la API lo haremos usando su **identificador único** a través de un parámetro en la URL. Es decir, si necesitamos recuperar un determinado usuario, haremos la consulta con la forma:

```
GET http://host:port/user/5
```

Si entonces necesitamos recuperar o modificar una colección asociada a ese usuario

```
POST http://host:port/user/5/following
```

* Intenta ajustar el tipo de información que devuelve cada una de las respuestas.

Por ejemplo, imagina que queremos recuperar la información de un usuario, pero, eso no significa que queramos explíctamente toda la información, sino un resumen de ésta:

```
GET http://host:port/user/3
```
que retorna:

```json
{
    "createdAt": "2014-10-07T09:30:10.862Z",
    "email": "kiko@sailor.com",
    "follower": 0,
    "following": 1,
    "id": 3,
    "online": true,
    "rol": "user",
    "updatedAt": "2014-10-07T09:31:04.220Z",
    "username": null
}
```

Nota cómo se ha omitido la lista de usuarios a los que seguimos (`following`) y se ha sustituido por el número de usuarios totales. Por otro lado, tendremos un path exclusivo de nuestra API para recuperar los usuarios de ésta lista:

```
GET http://host:port/user/3/following
```

que retorna:

```json
{
    "count": 1,
    "following": [
        {
            "createdAt": "2014-10-07T09:30:41.927Z",
            "email": "Elena@sailor.com",
            "followers": 0,
            "following": 0,
            "id": 4,
            "online": true,
            "rol": "user",
            "updatedAt": "2014-10-07T09:31:04.245Z",
            "username": null
        }
    ]
}
```

* Es muy importante que el tipo de respuesta a una determinada acción sea el adecuado. Recuerda que:

  + **1xx** Son de carácter informativo.
  + **2xx** Son para expresar que la acción ha tenido éxito.
  + **3xx** Son para redirección.
  + **4xx** Son para expresar errores en el cliente.
  + **5xx** Son para expresar errores en el servidor.

Para saber cuándo debes utilizar cada una de éstas respuestas te recomendamos ver la [tabla resumen de REST API Tutorial](http://www.restapitutorial.com/lessons/httpmethods.html).

Desde `sailor-module-response` se te proporcionan los shorcuts de respuesta más comúnes, como:

```
200 OK
400 Bad Request
404 Not Found
403 Forbidden
401 Unauthorized
500 Server Error
...
```

Siguiendo estas pautas el acceso se hará de una forma común. Escribir una pequeña documentación asociada al módulo también es un paso muy importante para que la comunidad entienda cómo utilizarlo (La mejor documentación son los tests).

Si necesitas respuestas más concretas o quieres ampliar tu conocimiento en la materia te recomendamos visitar la web [httpstatus.es](http://httpstatus.es/).

Si necesitas mejorar tus conocimientos aquí te dejamos una [buena guía práctica](https://github.com/interagent/http-api-design) basada en el diseño realizado por [Heroku para su API](https://devcenter.heroku.com/articles/platform-api-reference).

