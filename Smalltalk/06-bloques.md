# Bloques

Un bloque representa un fragmento de código que puede almacenarse y ejecutarse
posteriormente.

Se escribe entre corchetes:

    [ 2 + 3 ]

Crear el bloque no implica ejecutar inmediatamente su contenido.

## 1. `value`

Para evaluar un bloque se utiliza el mensaje `value`.

    [ 2 + 3 ] value

Resultado:

    5

## 2. Bloques con parámetros

Un bloque puede recibir uno o más parámetros.

    [ :x | x * 2 ]

En un bloque:

- `[` y `]` delimitan el bloque.
- `:x` declara un parámetro llamado `x`.
- `|` separa los parámetros del código que ejecutará el bloque.
- `x * 2` es el código que se ejecutará.

### Cómo se lee

La expresión:

    [ :x | x * 2 ]

puede leerse como:

> "Un bloque que recibe un valor `x` y devuelve `x * 2`."

Definir el bloque no ejecuta todavía su contenido. Para evaluarlo debemos
enviarle un mensaje.

Por ejemplo:

    [ :x | x * 2 ] value: 5

puede leerse como:

> "Ejecutar este bloque utilizando `5` como valor de `x`."

Durante la ejecución:

    x = 5

por lo tanto:

    x * 2
    5 * 2
    10

El resultado del bloque es:

    10

## 3. Bloques con varios parámetros

Un bloque puede recibir más de un parámetro.

    [ :x :y | x + y ]

### Cómo se lee

Podemos separar la expresión en:

    [ :x :y | x + y ]
      ────   ─────
     parámetros   código

- `:x` → primer parámetro.
- `:y` → segundo parámetro.
- `|` → finaliza la declaración de parámetros.
- `x + y` → código que ejecuta el bloque.

Puede leerse como:

> "Un bloque que recibe `x` e `y` y devuelve la suma de ambos."

Para evaluarlo:

    [ :x :y | x + y ] value: 3 value: 4

### Cómo se lee

> "Ejecutar el bloque utilizando `3` como `x` y `4` como `y`."

Por lo tanto:

    x = 3
    y = 4

    x + y
    3 + 4
    7

Resultado:

    7

## 4. Los bloques son objetos

Los bloques también son objetos.

Esto significa que pueden:

- guardarse en variables,
- pasarse como argumentos,
- recibir mensajes,
- ejecutarse cuando sea necesario.

Por ejemplo, suponiendo que `operacion` es una variable previamente definida:

    operacion := [ :x | x * 2 ].

    operacion value: 5

Resultado:

    10

### Cómo se lee

Primero:

    operacion := [ :x | x * 2 ]

guarda el bloque en la variable `operacion`.

Luego:

    operacion value: 5

envía el mensaje `value:` al bloque almacenado en `operacion`, utilizando `5`
como argumento.

El bloque ejecuta:

    5 * 2

y devuelve:

    10


Esta capacidad permite utilizar bloques para implementar comportamientos como
condicionales, iteraciones y operaciones sobre colecciones.