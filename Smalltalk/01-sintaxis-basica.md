# Sintaxis básica de Smalltalk

Smalltalk es un lenguaje orientado a objetos en el que los objetos se comunican
mediante el envío de **mensajes**.

Una de las ideas fundamentales para entender Smalltalk es:

> Todo es un objeto y los objetos se comunican enviándose mensajes.


## 1. Receptor y mensaje

Una expresión en Smalltalk puede entenderse como el envío de un mensaje a un objeto.

Por ejemplo:

    5 + 6

En esta expresión:

- `5` es el **receptor**.
- `+` es el **mensaje**.
- `6` es el **argumento**.

De forma general:

    RECEPTOR MENSAJE

o, si el mensaje necesita información:

    RECEPTOR MENSAJE ARGUMENTO


## 2. Tipos de mensajes

Smalltalk posee tres tipos principales de mensajes.


### 2.1 Mensajes unarios

No reciben argumentos.

Su estructura es:

    RECEPTOR MENSAJE

Ejemplo:

    20 factorial

- Receptor: `20`
- Mensaje: `factorial`


### 2.2 Mensajes binarios

Reciben exactamente un argumento y normalmente están representados mediante
símbolos.

Su estructura es:

    RECEPTOR MENSAJE ARGUMENTO

Ejemplo:

    5 + 6

- Receptor: `5`
- Mensaje: `+`
- Argumento: `6`


### 2.3 Mensajes de palabra clave

Reciben uno o más argumentos y se reconocen porque cada parte del mensaje
termina con `:`.

Ejemplo con un argumento:

    #(1 3 5 7) at: 2

- Receptor: `#(1 3 5 7)`
- Mensaje: `at:`
- Argumento: `2`

También pueden recibir varios argumentos:

    'Paradigmas' copyFrom: 1 to: 4

En este caso el mensaje completo es:

    copyFrom:to:

y recibe dos argumentos: `1` y `4`.


## 3. Orden de evaluación

Smalltalk no utiliza la precedencia matemática tradicional de operadores.

Los mensajes se evalúan en el siguiente orden:

1. **Mensajes unarios**
2. **Mensajes binarios**
3. **Mensajes de palabra clave**

Cuando varios mensajes tienen la misma prioridad, se evalúan de
**izquierda a derecha**.


### 3.1 Mensajes con la misma prioridad

Por ejemplo:

    4 + 5 * 2

`+` y `*` son mensajes binarios, por lo que tienen la misma prioridad.

Smalltalk evalúa de izquierda a derecha:

    (4 + 5) * 2

Resultado:

    18

Esto es diferente de la precedencia matemática tradicional, donde la
multiplicación tendría prioridad.


## 4. Mensajes anidados

El receptor o los argumentos de un mensaje pueden ser el resultado de otros
mensajes.

Por ejemplo:

    'hola' size + 4

Primero se evalúa el mensaje unario:

    'hola' size

que devuelve `4`, y luego:

    4 + 4

Resultado:

    8

El orden de evaluación visto anteriormente permite determinar cómo se resuelven
expresiones más complejas.

Por ejemplo:

    3 + 4 * 2

Como `+` y `*` son mensajes binarios y tienen la misma prioridad, se evalúan
de izquierda a derecha:

    (3 + 4) * 2

Resultado:

    14

## 5. Paréntesis

Los paréntesis permiten modificar explícitamente el orden de evaluación.

    4 + (5 * 2)

Primero se evalúa:

    5 * 2

y luego:

    4 + 10

Resultado:

    14

## 6. Resumen

Para leer una expresión Smalltalk:

1. Identificar el **receptor**.
2. Identificar qué **mensaje** recibe.
3. Identificar sus **argumentos**, si los tiene.
4. Determinar si los mensajes son **unarios, binarios o de palabra clave**.
5. Aplicar el orden de evaluación:

       Unarios → Binarios → Palabra clave

6. Para mensajes de la misma prioridad:

       Izquierda → Derecha

7. Los paréntesis permiten forzar otro orden de evaluación.