# Variables

Las variables permiten guardar referencias a objetos para poder utilizarlos
posteriormente.

En Smalltalk una variable no contiene directamente al objeto, sino una
referencia a él.

## 1. Asignación `:=`

Para asignar un objeto a una variable se utiliza `:=`.

Por ejemplo:

    numero := 10

### Cómo se lee

    numero := 10

puede leerse como:

> "Asignar a la variable `numero` una referencia al objeto `10`."

Luego podemos utilizar la variable como si utilizáramos directamente al objeto:

    numero + 5

Resultado:

    15

En este caso `numero` referencia a `10`, por lo que es el receptor del mensaje
`+`.


## 2. Variables temporales

Las variables temporales se utilizan para almacenar objetos durante la ejecución
de un bloque de código o método.

Se declaran entre barras verticales `| |`:

    | numero |

También pueden declararse varias variables al mismo tiempo:

    | numero resultado |

Luego podemos asignarles objetos:

    numero := 10.
    resultado := numero * 2.

### Cómo se lee

La expresión:

    | numero resultado |

puede leerse como:

> "Declarar dos variables temporales llamadas `numero` y `resultado`."

Luego:

    numero := 10

asigna `10` a `numero`.

Y:

    resultado := numero * 2

evalúa `numero * 2` y guarda el resultado en `resultado`.


## 3. Declaración y asignación

Es importante diferenciar ambos conceptos.

### Declarar

Indica que una variable existe:

    | numero |

### Asignar

Hace que esa variable referencie un objeto:

    numero := 10

Por lo tanto, normalmente encontraremos ambas cosas juntas:

    | numero |

    numero := 10.


## 4. `nil`

Una variable temporal declarada pero a la que todavía no se le asignó otro
objeto inicialmente referencia a `nil`.

Por ejemplo:

    | numero |

En ese momento:

    numero

devuelve:

    nil

`nil` no significa que la variable no exista.

La variable existe, pero actualmente referencia al objeto especial `nil`.

Como todo en Smalltalk, `nil` también es un objeto.


## 5. Parámetros

Los parámetros son variables que reciben un objeto cuando se ejecuta un bloque
o un método.

Ya vimos un ejemplo en los bloques:

    [ :x | x * 2 ]

En este caso `x` es un parámetro.

No necesitamos asignarlo manualmente. Su valor se recibe al evaluar el bloque:

    [ :x | x * 2 ] value: 5

Durante esa ejecución:

    x = 5

## 6. Alcance

Una variable solamente puede utilizarse dentro del ámbito en el que fue
declarada.

Por ejemplo:

    | numero |

    numero := 10.
    numero * 2

La variable `numero` puede utilizarse dentro del contexto donde fue declarada.

También podemos declarar variables dentro de un bloque:

    [
        | numero |
        numero := 10.
        numero * 2
    ] value

En este caso, `numero` solamente existe dentro del bloque.

### Cómo se lee

    [
        | numero |
        numero := 10.
        numero * 2
    ] value

1. `[ ... ]` crea un bloque.
2. `| numero |` declara una variable temporal perteneciente a ese bloque.
3. `numero := 10` asigna `10` a la variable.
4. `numero * 2` produce `20`.
5. `value` ejecuta el bloque.

Una vez fuera del bloque, `numero` deja de estar disponible.

A esto se lo conoce como **alcance** o **scope** de una variable.

> La creación y ejecución de bloques se explica en
> [Bloques](06-bloques.md).