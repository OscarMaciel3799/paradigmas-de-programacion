# Números y operaciones

En Smalltalk los números son objetos y las operaciones matemáticas se realizan
mediante el envío de mensajes.

## 1. Operaciones básicas

| Mensaje | Operación | Ejemplo |
|---|---|---|
| `+` | Suma | `5 + 6` |
| `-` | Resta | `10 - 3` |
| `*` | Multiplicación | `5 * 7` |
| `/` | División | `2 / 6` |
| `//` | División entera | `5 // 2` |
| `\\` | Resto de la división | `4 \\ 3` |

## 2. División `/`

Smalltalk puede conservar de forma exacta el resultado de una división entre
enteros utilizando fracciones.

    2 / 6

Resultado:

    1/3

## 3. División entera `//`

Devuelve el resultado entero de la división.

    5 // 2

Resultado:

    2

## 4. Resto `\\`

Devuelve el resto de una división entera.

    4 \\ 3

Resultado:

    1

## 5. `factorial`

Mensaje unario que devuelve el factorial del número receptor.

    5 factorial

Resultado:

    120

## 6. Notación científica

Los números también pueden expresarse utilizando notación científica:

    6.3e2

equivale a:

    6.3 × 10²

es decir:

    630