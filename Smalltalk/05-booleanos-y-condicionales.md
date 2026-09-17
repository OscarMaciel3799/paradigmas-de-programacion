# Booleanos y condicionales

Los valores booleanos permiten representar condiciones lógicas y controlar
qué partes del código deben ejecutarse.

## 1. Booleanos

Smalltalk posee dos valores booleanos:

    true
    false

Al igual que el resto de los elementos de Smalltalk, son objetos y pueden
recibir mensajes.

## 2. Comparaciones

Las comparaciones producen como resultado un valor booleano.

| Mensaje | Significado |
|---|---|
| `=` | Igual |
| `~=` | Distinto |
| `<` | Menor |
| `>` | Mayor |
| `<=` | Menor o igual |
| `>=` | Mayor o igual |

Por ejemplo:

    5 > 3

Resultado:

    true

## 3. Operaciones lógicas

Los booleanos pueden recibir mensajes para realizar operaciones lógicas.

### `&`

AND lógico.

    true & false

Resultado:

    false

### `|`

OR lógico.

    true | false

Resultado:

    true

### `not`

Niega un valor booleano.

    true not

Resultado:

    false

## 4. Condicionales

En Smalltalk los condicionales también se realizan mediante mensajes.

### `ifTrue:`

Ejecuta un bloque cuando el receptor es `true`.

    5 > 3 ifTrue: [
        Transcript show: 'Es mayor'
    ]

### `ifFalse:`

Ejecuta un bloque cuando el receptor es `false`.

    5 < 3 ifFalse: [
        Transcript show: 'La condición es falsa'
    ]

### `ifTrue:ifFalse:`

Permite definir qué ejecutar para ambos resultados.

    5 > 3
        ifTrue: [ Transcript show: 'Es mayor' ]
        ifFalse: [ Transcript show: 'No es mayor' ]

Esto muestra una característica importante de Smalltalk:

    condición ifTrue: [...] ifFalse: [...]

no es una estructura especial como el `if` de muchos otros lenguajes.

`ifTrue:ifFalse:` es un mensaje enviado a un objeto booleano.