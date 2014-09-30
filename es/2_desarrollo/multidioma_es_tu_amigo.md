# Multidioma es tu amigo

**sailor-translator** se usa de manera global en el sistema.
Puedes usarlo tanto en tun proyecto base como en un módulo.

Si necesitas enviar texto desde tu servidor a tu cliente, definivitamente tiene que usarlo.

La manera de usarlo es muy sencilla:

* Declara las cadenas multidioma en `translations/*.tl`
* Ejecuta la rutina `grunt translate_compile` para generar el fichero `config/translations.coffe` (si estás en desarrollo puedes ejecutar `grunt translate_compile:dev` para permanecer en segundo plano y compilar automáticamente).

Ahora las traducciones de ése módulo estarán disponibles de manera global en tu proyecto base.

Para saber cómo acceder a ellas te recomendamos [leerte la documentación](https://github.com/sailorjs/sailor-translate) o [ver algunos ejemplos en los módulos oficiales](https://github.com/sailorjs/sailor-module-lastfm/blob/master/api/controllers/lastFMController.coffee#L11).
