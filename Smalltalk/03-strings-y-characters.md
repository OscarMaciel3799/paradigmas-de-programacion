# Strings y Characters

## 1. String

Un `String` representa una cadena de caracteres y se escribe entre comillas simples.

    'Hola'

Un String puede contener uno o varios caracteres:

    'Paradigmas de Programación'

Incluso:

    'A'

continúa siendo un String.

## 2. Character

Un `Character` representa un único carácter y se escribe utilizando `$`.

    $A

Por lo tanto:

    'A'    "String"
    $A     "Character"

son objetos diferentes.

## 3. Mensajes comunes de String

### `size`

Devuelve la cantidad de caracteres.

    'hola' size

Resultado:

    4

### `asUppercase`

Devuelve el String convertido a mayúsculas.

    'hola' asUppercase

Resultado:

    'HOLA'

### `reversed`

Devuelve el String con sus caracteres en orden inverso.

    'hola' reversed

Resultado:

    'aloh'

### `includes:`

Indica si un String contiene determinado Character.

    'Hola' includes: $o

Resultado:

    true

### `copyFrom:to:`

Devuelve una parte del String comprendida entre dos posiciones.

    'Paradigmas' copyFrom: 1 to: 4

Resultado:

    'Para'

## 4. Conversión entre Character y número

### `asciiValue`

Devuelve el valor numérico correspondiente a un Character.

    $A asciiValue

Resultado:

    65

### `asCharacter`

Convierte un valor numérico en su Character correspondiente.

    65 asCharacter

Resultado:

    $A