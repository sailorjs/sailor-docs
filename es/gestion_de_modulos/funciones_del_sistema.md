# Gestión de Módulos

## Funciones del Sistema

En el sistema se proporcionan una serie de funciones en `sails.modules` que son:

* **availables()**
* Retorna: Una lista de tipo `array` con los nombres de los módulos cargados por el sistema.


* **size()**
* Retorna: `Integer` que representa el Nº de módulos cargado por el sistema.


* **isAvailable(nombreModulo)**
* Retorna: `Boolean` que representa si un determinado módulo ha sido cargado por el sistema.


* **errorHandler(nombreModulo)**
* Retorna: Lanza en el sistema un `Error`.


* **shield(nombreModulo...)**
* Retorna: Lanza un `Error` si alguno de los nombre de módulos proporcionados como argumento variable no ha sido cargado por el sistema.

<br><br>

La función `shield` es una combinación del resto de funciones para hacer fácil la protección de las dependencias de un módulo.

Si, por ejemplo, hemos definido un `sailor-module-group` que necesita para operar que `sailor-module-user` esté definido, podemos proteger su uso declarando en `api/hooks` un inicializador de la siguiente manera:

```coffee
sails.modules.shield 'sailor-module-user'
```

Si quisiéramos especficiar varias dependencias lo haríamos así:

```coffee
sails.modules.shield 'sailor-module-user', 'sailor-module-message'
```

Como puedes comprobar, para hacer a las funciones lo haremos a través del objeto global `sails`.
