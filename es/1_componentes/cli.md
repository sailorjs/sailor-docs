# CLI (Command Line Interface)

Es la línea de comandos de Sailor que interactúa directamente con el usuario. A través del CLI podrás:

* Crear la estructura base para tus proyectos.
* Crear la estructur apara desarrollar un nuevo módulo.
* Arrancar el servidor, tanto para entornos de pruebas como para producción.
*

## Instalación

### Prerequisitos

Antes de instalar **SailorJS** en tu sistema deberás contar con la última versión estable de NodeJS y NPM (Sistema de paquetes para NodeJS).

Si tienes dudas sobre este proceso te recomendamos que visites su [página web oficial](http://nodejs.org/download/).

### Instalando SailorJS

Simplemente utiliza el gestor de paquetes NPM para obtener la última versión de **SailoJS**. Abre un nuevo terminal y escribe:

```bash
npm install sailorjs -g
```

Lo cual instalará **SailorJS** de manera global en tu sistema.

## Comandos Principales

Una vez que tengas instalado **SailorJS** podrás interactuar con su CLI (*Client Line Interface*) mediante el cual podrás realizar tareas como:

* Crear el scaffolding para un nuevo proyecto base.
* Ejecutar tu proyecto base.
* Crear el scaffolding para desarrollar un nuevo módulo.

Ejecuta el comando `sailor` en el terminal para invocar al CLI:

![](../img/cli.png)

Si tienes duda sobre algún comando utiliza el parámetro `--help`.

## Comandos Principales

### Nuevo Proyecto Base

![](../img/new1.png)

Cuando creas un nuevo proyecto, éste tiene algunas dependencias del sistema **SailorJS** que son instalas automáticamente.

Nota que si proporcionas bien los parámetros como `description`, `organization` y `repository` automáticamente se crearán tu fichero `package.json` y `README.md` para enlazar con los comandos proporcionados.

La mayor parte de las dependencias son para preparar tu entorno de testing, del que hablaremos más adelante.

![](../img/new2.png)

### Nuevo Módulo

![](../img/newmodule1.png)

El proceso de creación de un módulo es similar al de un proyecto, excepto que las dependencias que necesita son muchas menos, pues está pensado para formar parte de un sistema mayor.

![](../img/newmodule2.png)

Nuevamente la mayor parte de las dependencias generadas tienen que ver con la suite de testing.

### Ejecutar tu servidor

![](../img/lift1.png)

![](../img/lift2.png)

Básicamente se proporcionan dos comandos útiles:

* `--silly` imprime por pantalla todo el debug del sistema de bootstrapping y es útil a la hora de desarrollar.
* `--production` prepara el entorno para ejecutarse en un sistema de producción final.
