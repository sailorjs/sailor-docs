# Módulos

## Propósito

El sistema de módulos de **SailorJS** nos permite hacer nuestro código más flexible, siempre y cuando esté debidamente encapsulado.

## FIRST

A la hora de diseñar el sistema de módulos nos inspiramos en otros sistemas de componentes como [Polymer](https://www.polymer-project.org/) o [bower](http://bower.io/) y nos dimos cuenta que cada uno de los módulos en los que vamos a dividir nuestra aplicación deben cumplir una serie de características muy específicas para que el sistema pudiese tratarlos correctamente.

Esas características se conocen como [FIRST](http://addyosmani.com/first/) y debes tenerlas muy presentes a la hora de desarrollar tus módulos para que el resto de la comunidad pueda usarlos.

### Focused

Cada módulo debe estar enfocado en realmente en lo que queremos que haga. El núcleo del módulo debe ser el objetivo que queremos que dicho módulo satisfaga y escribiremos el mínimo código necesario para que ese propósito se cumpla.

### Independent

Un módulo debe ser independiente del código de cualquier otro módulo.

Eso no quita el hecho de que un módulo pueda apoyarse en otro módulo cuando haga falta.

Por ejemplo, si estamos desarrollando *sailor-module-calendar* y necesitamos validar una fecha delegaremos entonces en *sailor-module-validator* dicha tarea.

### Reusable

Como finalidad última, al final lo que perseguimos es que no tengamos que reescribir lo que ya escribimos bien un día.

Puesto que los módulos tienen un carácter general y es en la aplicación base donde haremos de *maestro de ceremonias* podemos llegar a pensar que un módulo no puede ser correctamente usado a menos que sea modificado. *Parece no encajar bien*.

Piensa en el siguiente ejemplo: en *sailor-module-user* declaramos un modelo *User* que usaremos en nuestra aplicación, pero en dicho módulo el modelo aparece aislado puesto sólo existe ese modelo en el módulo, pero en una aplicación real, dicho modelo estará relacionado con otros, como *Lista de Amigos*, *Mensajes*, *Calendario*,...

Para hacer visible dicha relación tendremos que añadir al modelo *User* una *Foreign key* que referenciará a cada uno de los anteriores modelos citados...

¿Significa entonces que tendremos que modificar el modelo User del módulo?

Si hicieramos dicha acción romperíamos el esquema de los módulos. Es más, cuando el módulo se actualizase de forma independentiente a nuestra aplicación, perderíamos toda modificación que hayamos hecho sobre el módulo. Definitivamente no podemos hacer eso, pero entonces, ¿Cuál es la solución?

En **SailorJS** se utiliza un mecanismo de precedencia. Puesto que el scaffolding básico de un proyecto base y un módulo no difere, si declaremos el fichero que queremos sobreescribir en la base de nuestro proyecto éste tendrá más preferencia y por lo tanto será cargado por el sistema en vez de utilizar la versión del módulo.

Te recomendamos leer la sección **XXXX** en **Guía de Estilo**.

### Small

No intentaremos abarcar diferentes *features* es un mismo módulo. En vez de eso, crearemos un nuevo módulo por cada *feature*.

No encapsularemos *código-por-si-acaso* porque lo que estamos haciendo es ensuciar el código de nuestra arquitectura y el de resto de miembros de la comunidad. *Mantenlo sencillo, ¡Estúpido!*.

### Testable

Un sello de calidad de software es, sin duda, que tu código tenga tests. Si tu código no tiene tests asociados, no sirve para nada.

Sabemos que realizar testing desde el lado del servidor puede volverse una tarea tediosa puesto que a veces es más difícil realizar el setup de tu entorno de pruebas que el propio test.

Por eso, desde **SailorJS** en el momento que generas tu proyecto base o módulo se te proporcionará todo el setup necesario para que puedas escribir tus tests antes que tú código.

## Módulos por defecto

Análoga con la parte de **Componentes Internos del sistema** se proporcionan una serie de módulos que vienen por defecto y que podrás utilizar en tu desarrollo.

Visita la sección XXXX.
