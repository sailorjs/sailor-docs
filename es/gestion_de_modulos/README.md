# Gestión de Módulos

Cuando estás usando el sistema a veces necesitas coaccionarte de que cierto módulos están disponibles para su uso,  ya sea porque definen lógica de negocio que necesitas tener acceso desde otra parte del código, porque ciertas partes de tu código sólo puede ser definido si se usa un módulo específico o cualquier otra situación similar.

Desde **SailorJS** queremos que todas esas situaciones no sean un problema, sino una **ventaja**.

El sistema de módulos está pensado para que partes de tú código sean independendientes unas de otras. Lo que se conoce como **desacoplar**.

Pero piensa más allá: ¿No sería deseable hacer que tú código se comportara de una manera estándar por defecto y que en base a otros módulos ampliara su funcionalidad, complementándose?

Vamos a exponer esta idea con un ejemplo.

Imagina que estás trabajando con un modelo `User` en un módulo llamado `sailor-module-user`. Éste modelo define las propiedades más básicas que debe tener un usuario: *nombre*, *email* y *contraseña*. todas estas propiedades están dentro del dominio usuario. El código es bueno y haces commit.

Ahora piensas en ir un poco más allá, y piensas que estaría bien que tus usuarios pudieran mandarse mensajes entre ellos. Pero ello complica un poco la lógica del módulo: necesitas agregar un nuevo modelo `Message` y agregar dos colecciones a tu modelo `User`: una colección para guardar los mensajes de entrada (**inbox**) y otra para los mensajes de salida (**outbox**). Ya no lo ves tan claro.

Ahora, reflexiona sobre lo anterior. ¿Tiene sentido tener un modelo `Message` definido en tú módulo `sailor-module-user`? ¿Pertenece al mismo dominio? ¿Queremos que, por defecto, los usuarios puedan intercambiar mensajes, o queremos que sea una características añadida?

Lo ideal para resolver el problema sería definir dos módulos distintos, pero complementarios: `sailor-module-user` y `sailor-module-message`, que se comportaran de la siguiente manera:

* `sailor-module-user` define un esquema estándar de `User` con *nombre*, *email* y *contraseña*.
* Si el sistema carga `sailor-module-message` entonces tendremos disponible un modelo `Message`.
* Puesto que tenemos un modelo `Message` disponible, nuestro `sailor-module-user` agrega *inbox* y *outbox* en `User`, de manea que podamos soportar mensajería entre usuarios.

De esta manera nuestro código se **adapta** en base a si otros módulos están disponibles, **complementándose** y ampliando la **funcionalidad** global del sistema.

En ésta sección vamos a ver cómo vas a poder hacer precisamente esto.
