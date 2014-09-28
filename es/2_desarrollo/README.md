# Guía de estilo

## Preferimos CoffeeScript

Aunque JavaScript es igual de válido, preferimos utilizar a CoffeeScript ya que es más legible, más fácil de mantener y más rápido para desarrollar.

## No encapsules lo que no vayas a usar

Cuando generamos un scaffolding para un nuevo módulo se crea el scaffold con todas las posibilidades de extensión existentes: *adapters*, *api*, *config*, *translations*, *views*...

Si no vas a utilizar alguno de éstos apartados asegúrate de eliminarlos antes de exponer tu módulo a la comunidad.

La razón por la que están presentes es para que un desarrollador sepas las posibilidades disponibles para clasificar su código.

## Usa multidioma cuando lo necesites

**sailor-translator** se usa de manera global en el sistema.
Puedes usarlo tanto en tun proyecto base como en un módulo.

Si necesitas enviar texto desde tu servidor a tu cliente, definivitamente tiene que usarlo.

La manera de usarlo es muy sencilla:

* Declara las cadenas multidioma en `translations/*.tl`
* Ejecuta la rutina `grunt translate_compile` para generar el fichero `config/translations.coffe` (si estás en desarrollo pero ejecutar `grunt translate_compile:dev` para permanecer en segundo plano).

Cuando lances tu proyecto base las traducciones estarán disponibles desde el objeto Translator. Si tienes dudas, **léete la documentación** ó mira algún módulo desarrolado por el equipo.

## Testea siempre

Como hemos dicho anteriormente, desde el momento que generas tu proyecto base o módulo podrás empezar a testear tu código.

En ambos casos para lanzar los tests tendrás que ejecutar el comando `npm test`:

-- SCREEN --

Por defecto se incluyen algunos test a modo de ejemplo. Te aconsejamos ver tests de otros módulos para dividir bien tus tests.
