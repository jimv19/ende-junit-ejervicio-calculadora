# Testing con Junit

Este es un ejemplo sencillo de pruebas unitarias usando Junit 5

Observa que este proyecto no tiene ninguna clase con el método `main`, no nos hace fatal. Además, tampoco tiene ningún `scanner` ni ningún `print`.

Haz un fork de este proyecto en tu repositorio de Github y contesta a las siguientes preguntas:

1. ¿Qué sentido puede tener este proyecto y para que lo podrías usar?
Este proyecto sirve para practicar como funcionan las pruebas unitarias con *JUnit 5*. No es una aplicion completa si no un proyecto pensado para aprender a comprobar si los métodos de una clase funcionan bien.
En una empresa, un proyecto asi se usaría para:
    * Asegurarse de  que el codigo  funciona antes de fusionarlo con el resto del programa.
    * Evitar errores cuando alguien modifica una parte del código.
    * Comprobar automáticamente que los métodos siguen devolviendo lo que deben.
    * Apresnder a trabajar con calidad, que es algo que se pide mucho en entornos profesionales.

Aunque no tenga main, ni scannerm ni nada que se ejecute, tiene sentido por que su objetivo no es usar el programa, si no probarlo.

Tacmbién observamos el desarrollo de carpetas tiene la estructura tipica de un proyecto Java con Maven.

```bash
 src/main/
```
Aquí van las *clases normales*, las que contienen los métodos que queremos probar. Por ejemplo, si hay una clase *calculadora*, aqí estará su codigo.

```bash
src/test/java
```
Aquí van las *clases de prueba*, que son las que usan JUNIT5.
Normalemente se llaman igual que la clse que prueban, pero añadiendo *test*.
*   clase: *Calculadora*
*   test *CalculadoraTest*

Como están hechas las pruebas.
 Las pruebas usan  anotaciones de  *JUnit 5* como:
 *  @Test --> marca un método como prueba.
 *  assertEquals, asserTrue, assertThrows --> sirven para  comprobar resultados.

 Las pruebas que más llaman la atención suelen ser:

*   Pruebas de excepciones, porque permiten comprobar que un método falla cuando debe fallar.

*   Pruebas de casos límite, como dividir entre cero o sumar números negativos.

*   Pruebas que cubren varios casos, no solo uno.

En general, el proyecto está organizado para que sea fácil ver qué método se prueba y qué se espera de él.


2. Revisa las pruebas de la suma y comenta lo que te parezca de interés.
Lo primero que llama la atención es que hay una prueba correcta y una prueba que está hecha para fallar:

*   sumarPositivos() → esta prueba está bien hecha: 2 + 3 = 5.

*   sumarPositivosMal() → esta prueba está mal a propósito: espera 4 cuando el resultado real es 5.

Esto sirve para ver cómo JUnit marca una prueba como fallida y cómo se comporta el sistema cuando algo no funciona como debería.

Tambien se observa la prueba múltiple de la suma esta usa assertAll, que permite agrupar varias comprobaciones dentro de un mismo test. Esto hace que se puedan probar distintos casos (positivos, cero y negativos) de forma ordenada sin crear muchos métodos separados. Además, aunque una de las comprobaciones falle, las demás también se ejecutan, y JUnit muestra exactamente cuál ha fallado. Gracias a esto se puede ver de un vistazo si el método sumar funciona correctamente en diferentes situaciones.

3. Realiza un estudio de caja negra de la división e implementa las pruebas en junit: Se realizará en markdown.

## Estudio de caja negra - Método división
El estudio de caja negra se hace sin mirar el código, solo analizando las entradas, las salidas y los casos que pueden aparecer según los valores que reciba el método.

**Entradas**
El método recibe dos números enteros:

*   dividendo

*   divisor

**Salidas**
El método puede devolver:

*   un número entero (resultado de la división entera)

*   una excepción cuando el divisor es 0

**Valor intermedio**
Se utiliza un valor que no sea límite, por ejemplo: 4

**Combinación de entradas (producto cartesiano)**
Para cubrir todos los casos posibles, se combinan todos los valores límite e intermedios del dividendo con todos los valores límite e intermedios del divisor.
Esto permite ver cómo se comporta el método en distintas situaciones:

*   división entre números positivos

*   división entre números negativos

*   división de positivo entre negativo

*   división de negativo entre positivo

*   división entre 0 (errores)

*   división con 1 y –1 (límites del divisor)

*   división con números grandes (casos normales)

| #  | Dividendo (a) | Divisor (b) | Resultado esperado | Tipo de caso                         |
|----|----------------|-------------|--------------------|---------------------------------------|
| 1  | 12             | 6           | 2                  | Normal: positivo entre positivo       |
| 2  | -12            | 6           | -2                 | Normal: negativo entre positivo       |
| 3  | 12             | -6          | -2                 | Normal: positivo entre negativo       |
| 4  | -12            | -6          | 2                  | Normal: negativo entre negativo       |
| 5  | 0              | 6           | 0                  | Normal: dividendo cero                |
| 6  | 12             | 0           | Error (excepción)  | Error: divisor cero                   |
| 7  | 0              | 0           | Error (excepción)  | Error: divisor cero                   |
| 8  | 1              | 1           | 1                  | Valor límite: +1 / +1                 |
| 9  | -1             | 1           | -1                 | Valor límite: -1 / +1                 |
| 10 | 1              | -1          | -1                 | Valor límite: +1 / -1                 |
| 11 | 12             | 1           | 12                 | Normal: divisor límite +1             |
| 12 | 12             | -1          | -12                | Normal: divisor límite -1             |






## Instrucciones

El alumno deberá hacer un fork de este proyecto e implementar la solución solicitada (preguntas y código).

>Se deberá utilizar este fichero, y los artefactos de código del proyecto, para resolver el ejercicio.


**Si no se puede acceder al repositorio la evaluación del ejercicio será de 0. No se evaluarán entregas modificadas/entregadas fuera del plazo establecido en la tarea**