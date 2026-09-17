# Bucles e iteraciones

Smalltalk permite repetir código utilizando mensajes y bloques.

A diferencia de lenguajes como Java o C++, muchas iteraciones no se escriben
mediante estructuras como `for` o `while`, sino enviando mensajes a objetos.


## 1. `timesRepeat:`

Permite ejecutar un bloque una determinada cantidad de veces.

    5 timesRepeat: [
        Transcript show: 'Hola'; cr
    ]

### Cómo se lee

    5 timesRepeat: [ ... ]

puede leerse como:

> "Repetir este bloque 5 veces."

En esta expresión:

- `5` → receptor.
- `timesRepeat:` → mensaje.
- `[ ... ]` → bloque que se ejecutará cinco veces.


## 2. `to:do:`

Permite recorrer un rango de números.

    1 to: 5 do: [ :numero |
        Transcript show: numero; cr
    ]

### Cómo se lee

    1 to: 5 do: [ :numero | ... ]

puede leerse como:

> "Desde 1 hasta 5, ejecutar el bloque para cada número."

En cada ejecución el parámetro `numero` toma un valor diferente:

    1
    2
    3
    4
    5

El mensaje completo es:

    to:do:

y recibe dos argumentos:

1. `5`
2. `[ :numero | ... ]`


## 3. `whileTrue:`

Permite repetir un bloque mientras una condición sea verdadera.

    | numero |
    numero := 1.

    [ numero <= 5 ] whileTrue: [
        Transcript show: numero; cr.
        numero := numero + 1
    ]

### Cómo se lee

    [ condición ] whileTrue: [ código ]

puede leerse como:

> "Mientras la condición sea verdadera, ejecutar el segundo bloque."

En este caso:

1. Se evalúa `numero <= 5`.
2. Si devuelve `true`, se ejecuta el segundo bloque.
3. Se vuelve a evaluar la condición.
4. El proceso continúa hasta que la condición devuelve `false`.


## 4. `whileFalse:`

Funciona de manera inversa a `whileTrue:`.

    [ condición ] whileFalse: [
        código
    ]

### Cómo se lee

> "Mientras la condición sea falsa, ejecutar el bloque."

La repetición termina cuando la condición devuelve `true`.


## 5. Iterar colecciones con `do:`

Las colecciones pueden recibir el mensaje `do:` para ejecutar un bloque sobre
cada uno de sus elementos.

    #(10 20 30) do: [ :numero |
        Transcript show: numero; cr
    ]

### Cómo se lee

    coleccion do: [ :elemento | ... ]

puede leerse como:

> "Para cada elemento de la colección, ejecutar este bloque."

En el ejemplo, `numero` toma sucesivamente los valores:

    10
    20
    30


## 6. Diferencia con un `for` tradicional

En otros lenguajes podríamos encontrar una estructura como:

    for (...)

En Smalltalk es habitual pedirle directamente a un objeto que realice la
iteración.

Por ejemplo:

    5 timesRepeat: [ ... ]

    1 to: 5 do: [ :numero | ... ]

    coleccion do: [ :elemento | ... ]

Esto mantiene la idea fundamental del lenguaje:

> Los objetos reciben mensajes.