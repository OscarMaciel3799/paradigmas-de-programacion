# Clases y objetos

Smalltalk es un lenguaje orientado a objetos.

Una de sus ideas fundamentales es:

> Todo es un objeto.

Números, Strings, colecciones e incluso las propias clases son objetos y pueden
recibir mensajes.


## 1. Objetos

Un objeto combina información con un determinado comportamiento.

Los objetos interactúan mediante el envío de mensajes.

Por ejemplo:

    5 factorial

### Cómo se lee

- `5` es un objeto.
- `factorial` es el mensaje que recibe.

Otro ejemplo:

    'hola' size

El objeto `'hola'` recibe el mensaje `size` y responde con:

    4


## 2. Clases

Todo objeto es instancia de alguna clase.

Una clase define qué características y comportamientos tendrán sus instancias.

Podemos conocer la clase de un objeto enviándole el mensaje `class`:

    5 class

    'hola' class

    #(1 2 3) class

### Cómo se lee

Por ejemplo:

    'hola' class

puede leerse como:

> "Enviar el mensaje `class` al objeto `'hola'` para conocer a qué clase pertenece."


## 3. Instancias

Un objeto perteneciente a una clase se denomina **instancia** de esa clase.

Por ejemplo, diferentes Strings son objetos diferentes:

    'hola'
    'Smalltalk'
    'Paradigmas'

pero todos son instancias de una clase que representa Strings.

Podemos comprobar su clase utilizando:

    'hola' class

    'Smalltalk' class


## 4. Creación de objetos

Muchas clases permiten crear nuevas instancias mediante el mensaje `new`.

Por ejemplo:

    Array new

### Cómo se lee

    Array new

puede leerse como:

> "Enviar el mensaje `new` a la clase `Array` para crear una nueva instancia."

En esta expresión:

- `Array` → receptor.
- `new` → mensaje unario.
- resultado → una nueva instancia de `Array`.

También existen mensajes de creación que reciben argumentos:

    Array new: 5

En este caso se crea un Array con espacio para cinco elementos.


## 5. Las clases también son objetos

Una característica importante de Smalltalk es que las propias clases también
son objetos.

Por eso una clase puede actuar como receptor de un mensaje:

    Array new

    Date today

    Time now

Por ejemplo:

    Date today

puede leerse como:

> "Enviar el mensaje `today` al objeto `Date`."

Esto permite entender por qué en Smalltalk utilizamos la misma sintaxis para
enviar mensajes tanto a objetos comunes como a clases.


## 6. Mensajes y métodos

Un **mensaje** y un **método** no son exactamente lo mismo.

Un mensaje representa una solicitud enviada a un objeto:

    5 factorial

En este caso:

    factorial

es el mensaje.

El **método** es el código que determina cómo responde el objeto a ese mensaje.

De forma simplificada:

    objeto → recibe un mensaje → ejecuta un método → produce un resultado

Por ejemplo:

    'hola' size

1. `'hola'` recibe el mensaje `size`.
2. Se ejecuta el método correspondiente.
3. Se obtiene como resultado `4`.

Por lo tanto:

> El mensaje indica **qué se solicita** y el método define **cómo se responde**.


## 7. Estado y comportamiento

Los objetos pueden pensarse a partir de dos conceptos principales:

- **Estado:** información que mantiene el objeto.
- **Comportamiento:** operaciones que el objeto puede realizar o mensajes a
  los que puede responder.

Las clases permiten definir ese estado y comportamiento para sus instancias.

Más adelante, al crear nuestras propias clases, estos conceptos permitirán
definir objetos con sus propios datos y métodos.