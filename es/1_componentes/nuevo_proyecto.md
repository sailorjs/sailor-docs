# CLI (Command Line Interface)

## Comandos Principales

### Nuevo Proyecto Base

Éste comando generará el scaffolding necesario para que puedas desarrollar un nuevo proyecto.

![](../img/new1.png)

Si has desarrollado antes para **Sails** nota como el scaffolding generado es similar pero extendido:

```bash
.
├── Gruntfile.js
├── LICENSE.md
├── README.md
├── api
├── app.js
├── app.json
├── assets
├── config
├── node_modules
├── package.json
├── tasks
├── test
├── translation
└── views
```

El comando admite algunos parámetros para que automáticamente enlace con tu cuenta de Github y genere los ficheros `package.json` y `README.md` asociados a la información proporcionada, como **descripción**, **organización** y **repositorio**:

![](../img/new2.png)
