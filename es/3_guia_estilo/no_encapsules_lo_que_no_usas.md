# Guía de estilo

## No encapsules lo que no usas

Cuando generamos un scaffolding para un nuevo módulo se crea el scaffold con todas las posibilidades de extensión existentes: *adapters*, *api*, *config*, *translations*, *views*...

Si no vas a utilizar alguno de éstos apartados asegúrate de eliminarlos antes de exponer tu módulo a la comunidad.

La razón por la que están presentes es para que un desarrollador sepa las posibilidades disponibles para clasificar su código.
