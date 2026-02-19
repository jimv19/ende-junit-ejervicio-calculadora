# Testing con Junit

Este es un ejemplo sencillo de pruebas unitarias usando Junit 5

Observa que este proyecto no tiene ninguna clase con el método `main`, no nos hace fatal. Además, tampoco tiene ningún `scanner` ni ningún `print`.

Haz un fork de este proyecto en tu repositorio de Github y contesta a las siguientes preguntas:

1. ¿Qué sentido puede tener este proyecto y para que lo podrías usar?
Este proyecto tiene como objetivo principal aprender y practicar pruebas unitatias con JUnit 5, haciendo los test pertinentes a cada método.
En el observamos que no  tenemos main ni tampoco scanner ni print, todo es de manera automatizada.

2. Revisa las pruebas de la suma y comenta lo que te parezca de interés
Observamos en la suma 
En la primera de sumarPositivos, la prueba nos da correcta por que el resultado es el mismo que al esperado.
Sin embargo en el metodo sumarPositivosMal vemos que  la prueba falla intencionadamente por que el resultado es diferente al esperado. 
Tambien observamos despues 4 pruebas  automatizadas. Estos es muy interesante por que  vemos que con JUnit podemos automatizar las pruebas, lo que nos ahorraria tiempo en proyecto más grandes



3. Realiza un estudio de caja negra de la división e implementa las pruebas en junit: Se realizará en markdown.

## Estudio de caja negra - Método división

El estudio de caja negra se hace sin mirar el código interno, solo pensando en:

Entradas posibles

Salidas esperadas

Casos límite

Casos erróneos

| Caso | Dividendo | Divisor | Resultado esperado | Tipo de caso |
|------|------------|----------|--------------------|--------------|
| 1 | 10 | 2 | 5 | Caso normal |
| 2 | -10 | 2 | -5 | Signo negativo |
| 3 | 10 | -2 | -5 | Signo negativo |
| 4 | -10 | -2 | 5 | Ambos negativos |
| 5 | 0 | 5 | 0 | Cero en dividendo |
| 6 | 5 | 0 | Excepción | División por cero |





## Instrucciones

El alumno deberá hacer un fork de este proyecto e implementar la solución solicitada (preguntas y código).

>Se deberá utilizar este fichero, y los artefactos de código del proyecto, para resolver el ejercicio.


**Si no se puede acceder al repositorio la evaluación del ejercicio será de 0. No se evaluarán entregas modificadas/entregadas fuera del plazo establecido en la tarea**