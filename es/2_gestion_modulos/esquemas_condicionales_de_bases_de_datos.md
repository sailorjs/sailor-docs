# Gestión de Módulos

## Esquemas condicionales de bases de datos

Como hemos dicho en la introducción, sería deseable que el comportamiento de nuestros módulos se adaptase al resto de módulos, de manera que podamos definir un comportamiento estándar y un comportamiento **condicional**.

Esta característica del sistema pasa por el **esquema de base de datos**.

**SailorJS** extiende el **ORM** proporcionado por **Sails** para soportar dicha característica.

Veamos a continuación cómo sería un esquema típico de modelo `User` en nuestro módulo `sailor-module-user`:


```coffee
schema: true
attributes :
    username   : type: 'string', notNull: true
    email      : type: 'email', unique: true, required: true
    passports  : collection: 'Passport', via: 'user'
```

Si en base a dicho esquema quisiéramos declarar atributos condiciones a otras colecciones no existentes en el módulo, lo declararíamos de la siguiente manera:

```coffee
schema: true
attributes :
    username   : type: 'string', notNull: true
    email      : type: 'email', unique: true, required: true
    passports  : collection: 'Passport', via: 'user'

conditional:
    Message:
        attributes:
            inbox: collection: 'Message'
            outbox: collection: 'Message'
```

De ésta manera estamos diciendo en el apartado `conditionals` que, si está disponible el modelo `Message`, entonces al esquema estándar añadidos dos atributos: **inbox** y **outbox**, que son colecciones de dicho modelo.

Si aparte del modelo `Message` quisieramos añadir cualquier otro, basta añadirlo como otra condición:

```coffee
schema: true
attributes :
    username   : type: 'string', notNull: true
    email      : type: 'email', unique: true, required: true
    passports  : collection: 'Passport', via: 'user'

conditional:
    Message:
        attributes:
            inbox: collection: 'Message'
            outbox: collection: 'Message'
    Group:
        attributes:
            group: collection: 'Group'
```

Por supuesto también podremos declarar funciones propias de modelo:

```coffee
schema: true
attributes :
    username   : type: 'string', notNull: true
    email      : type: 'email', unique: true, required: true
    passports  : collection: 'Passport', via: 'user'

conditional:
    Message:
        attributes:
            inbox: collection: 'Message'
            outbox: collection: 'Message'
    Group:
        attributes:
            group: collection: 'Group'
            groups: ->
                count: @group.length
                groups: @group
```
