# Colecciones

Las colecciones permiten almacenar y trabajar con conjuntos de objetos.

## 1. Array

Un `Array` es una colección de tamaño fijo.

### Array literal

Un Array puede escribirse directamente utilizando `#()`:

    #(1 3 5 7)

Los Arrays pueden contener objetos de distintos tipos:

    #(1 'hola' $A 3.5)

A diferencia de los arrays de lenguajes con tipado estático como Java o C++,
no es necesario que todos sus elementos sean del mismo tipo.

## 2. Índices

Las posiciones de las colecciones en Smalltalk comienzan en `1`.

    #(10 20 30) at: 1

Resultado:

    10

## 3. `size`

Devuelve la cantidad de elementos de una colección.

    #(10 20 30) size

Resultado:

    3

## 4. `at:`

Devuelve el elemento ubicado en una determinada posición.

    #(1 'hola' $A 3.5) at: 2

Resultado:

    'hola'

## 5. `includes:`

Indica si una colección contiene determinado objeto.

    #(1 2 3) includes: 2

Resultado:

    true

## 6. `reversed`

Devuelve una colección con sus elementos en orden inverso.

    #(1 2 3) reversed

Resultado:

    #(3 2 1)

## 7. Concatenación `,`

Permite concatenar colecciones.

    #(1 2 3), #(4 5 6)

Resultado:

    #(1 2 3 4 5 6)

## 8. Creación de Arrays

También podemos crear Arrays enviando mensajes a la clase `Array`.

    Array new

crea un Array vacío.

También podemos especificar su tamaño:

    Array new: 4

Resultado:

    #(nil nil nil nil)