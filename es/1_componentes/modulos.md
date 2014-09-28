# Módulos

## Propósito

El sistema de módulos de **SailorJS** nos permite hacer nuestro código más flexible, siempre y cuando esté debidamente encapsulado.

## FIRST

A la hora de diseñar el sistema de módulos nos inspiramos en otros sistemas de componentes como [Polymer](https://www.polymer-project.org/) o [bower](http://bower.io/) y nos dimos cuenta que cada uno de los módulos en los que vamos a dividir nuestra aplicación deben cumplir una serie de características muy específicas para que el sistema pudiese tratarlos correctamente.

Esas características se conocen como [FIRST](http://addyosmani.com/first/) y debes tenerlas muy presentes a la hora de desarrollar tus módulos para que el resto de la comunidad pueda usarlos.

### Focused

Cada módulo debe estar enfocado en realmente en lo que queremos que haga. El núcleo del módulo debe ser el objetivo que queremos que dicho módulo satisfaga y escribiremos el mínimo código necesario para que ese propósito se cumpla.

### Independent

Un módulo debe ser independiente del código de cualquier otro módulo. Queremos matizar ese *debe* porque hay una serie de escenarios donde es difícil cumplir esta premisa y deben considerarse como casos de estudio.

Entre los módulos existen una serie de dependencias que están presentes en la mayoría de los módulos, como:

* El sistema de traducción (sailor-translate)
* El sistema de serialización de errores (sailor-errorify)
* El sistema de validación (sailor-validator)

A ésta serie de dependencias utilizada por todos los módulos las llamaremos **dependencias compartidas**.

Para evitar estas dependencias, el sistema tiene una manera de inyectarlas en el caso de que las necesitemos. Así, todos los módulos tendrán la misma dependencia (con lo que reducimos el código de nuestra build) y la misma versión (con lo que será más fácil mantenerlo).

Para ver cómo hacemos esto, mira el fichero `test/init.test.coffee` de cualquier módulo. Si atendemos a la siguiente línea de código:

```coffee
scripts.linkDependency dependency for dependency in SCOPE.DEPENDENCIES
```

y en donde:

```
SCOPE.DEPENDENCIES : ['sailor-translate', 'sailor-validator', 'sailor-errorify']
```

Lo que estamos haciendo es linkear la dependencia directamente desde el sistema, de tal manera que podamos usarla en nuestro módulo sin necesita de instalarla nuevamente.


### Reusable



### Small

No intentaremos abarcar diferentes *features* es un mismo módulo. En vez de eso, crearemos un nuevo módulo por cada *feature*.

No encapsularemos en un método código-por-si-acaso.

### Testable


