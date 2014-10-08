# Guía de estilo

## Ajusta los módulos

Como comentamos secciones atrás, a veces necesitas modificar un fichero de un módulo para que funcione correctamente en tu aplicación y debes realizar este proceso con el **mecanismo de precedencia** de **SailorJS**. Para ello deberás usar el **mecanismo de precedencia:**

1. Localiza el *path relativo* del fichero que quieres modificar. Por ejemplo, si queremos modificar el fichero *User* de *sailor-module-user*, el path relativo al módulo es *sailor-module-user/api/models/User.coffee*.
2. Crea el mismo fichero con el mismo *path* relativo en tu proyecto base. Es decir, crearemos el fichero *baseProject/api/models/User.coffee*.

Ahora el fichero *User* de tu proyecto base tendrá más precedencia que el fichero del módulo y por tanto será utilizado por el sistema.
