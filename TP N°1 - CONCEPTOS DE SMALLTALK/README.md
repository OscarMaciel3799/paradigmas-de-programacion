# ¿Por qué el código de estos TPs se ve así?

Si nunca usaste Pharo/Smalltalk, esto capaz te llame la atención: no hay un botón "Run" ni un comando tipo `python archivo.py` que ejecute el archivo y te muestre el resultado en una terminal. Pharo no funciona así.

## Por qué Pharo es distinto

En lenguajes como Python, Java o C, uno escribe un archivo con código y lo **corre** de punta a punta: el programa arranca, hace lo que tiene que hacer, y termina.

Pharo no tiene "archivos que se ejecutan". Es un entorno **vivo**: todo el tiempo hay un espacio de objetos en memoria (la "imagen"), y uno interactúa con él escribiendo expresiones sueltas en una ventana llamada **Playground** y pidiéndole a Pharo que las evalúe una por una (o de a bloques) con atajos de teclado (`Do it`, `Print it`). El resultado de una expresión aparece pegado al lado del código, no en una consola centralizada y solo se puede ver **una expresión a la vez**.

Esto es genial para explorar y probar cosas interactivamente, pero es un problema si uno quiere:
- Correr **todos los ejercicios de un TP juntos**, de una sola vez.
- Ver **todos los resultados juntos**, en orden, como en la terminal de cualquier otro lenguaje.
- Que quien abra el archivo en el repo entienda qué hace cada línea sin tener que ir clickeando una por una dentro de Pharo.

## La solución: usar el Transcript como si fuera una terminal

Pharo sí tiene una ventana llamada **Transcript**, que funciona como una consola de texto donde se puede ir escribiendo mensajes. La usamos para simular el comportamiento de un `print()` normal: en vez de dejar la expresión sola, la envolvemos así:

​```smalltalk
Transcript show: 'Ej 1.a: '; show: (5 + 6) printString; cr.
​```

Esto se lee como: "mostrame la etiqueta 'Ej 1.a: ', después el resultado de `5 + 6` convertido a texto, y saltá de línea". Con esto, se puede seleccionar **todo el archivo de una** y ejecutarlo junto (`Ctrl+A` → `Ctrl+D`), y los resultados de todos los ejercicios van apareciendo en el Transcript, uno debajo del otro, igual que si hubieras corrido un script y visto el output en una terminal.

## Qué es la resolución real de cada ejercicio


La parte que efectivamente responde al ejercicio de la guía es lo que está entre paréntesis — por ejemplo `(5 + 6)` o `(20 factorial)`. Todo el resto (`Transcript show:`, la etiqueta, `printString`, `cr`) es solamente el "cable" que conectamos para poder ver y agrupar esos resultados como si fuera una terminal.