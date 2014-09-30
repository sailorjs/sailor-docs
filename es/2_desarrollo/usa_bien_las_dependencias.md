# Usa bien las dependencias

Si tu módulo tiene dependencias externas deberás declararlas de manera correcta en `package.json`. Recuerda que:

* Si es una dependencia que sólo necesitas para desarrollar estará situada dentro de **devDependencies**.
* Si es una dependencia que necesita tu módulo para funcionar estará situada dentro de *dependencies*.

Hay que prestar especialmente atención a la versión de la dependencia que queremos usar. Cuando declaramos algo como esto:

```
"dependencies": {
    "bcryptjs": "*"
  }
```

Estamos declarando que queremos la última versión disponible. Cuidado porque puede **romper tu código**. Desde **SailorJS** realizamos este tipo de declaraciones para:

* Asegurarnos de que tenemos la versión más actualizada de la dependencia.
* Si la dependencia rompe el código, detectarlo rápidamente y re-adaptar el módulo.

Con ello evitamos estancarnos en una versión antigua de la dependencia y tener que chequear manualmente si hay una nueva actualización.

Cuando declaramos la dependencia de esta manera automáticamente **npm** buscará en sus repositorios oficiales. Si queremos usar una dependencia que no está en **npm** pero sí en una cuenta de **Github** podremos hacerlo declarandola de la siguiente manera:

```
"dependencies": {
    "bcryptjs": "git://github.com/sailorjs/sailorjs"
  }
```

Nota que el sistema de versiones en éste aspecto es limitado y que siempre traerá la última versión.
