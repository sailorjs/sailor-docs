# Gestión de Módulos

## Sistema de precedencia

A veces necesitamos ajustar el comportamiento de un módulo y para ello debemos modificar su código para que se adapte bien al comportamiento de nuestro sistema.

Para ello, conviene no modificar el módulo directamente, pues si lo hacemos perderemos los cambios efectuados cada vez que actualicemos el módulo.

Utilizaremos entonces el **sistema de precedencia**: declararemos el mismo fichero en la base de nuestro proyecto para que el sistema sepa que debe utilizarlo en vez de utilizar el declarado en el módulo (el sistema entenderá entonces que el declarado en la base del proyecto tiene más precedencia y por tanto debe ser cargado en vez de cargar el fichero original del módulo).

Un ejemplo de funcionamiento sería el siguiente:

1. Localiza el *path relativo* del fichero que quieres modificar. Por ejemplo, si queremos modificar el fichero *User* de *sailor-module-user*, el path relativo al módulo es *sailor-module-user/api/models/User.coffee*.
2. Crea el mismo fichero con el mismo *path* relativo en tu proyecto base. Es decir, crearemos el fichero *baseProject/api/models/User.coffee*.

Ahora el fichero *User* de tu proyecto base tendrá más precedencia que el fichero del módulo y por tanto será utilizado por el sistema.
