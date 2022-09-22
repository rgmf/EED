Lenguajes de programación: evolución histórica
**********************************************
Los lenguajes de programación han sufrido una evolución importante. Los primeros ordenadores eran programados por medio de **lenguaje máquina**, en binario directamente; con el **lenguaje ensamblador** se facilitó la programación añadiendo mnemotécnicos y alejándose del código binario; por último, hoy en día, tenemos **lenguajes de alto nivel** que son fáciles de aprender y, además, hacen la programación más fácil.

En los siguientes apartados te explico brevemente cómo funciona cada uno de los tres tipos de lenguajes.

Lenguaje máquina
================
Se trata de un lenguaje de programación de bajo nivel, consistente en **instrucciones en binario** que se usan para el control de un procesador o CPU. Cada instrucción hace que la CPU realice una tarea específica como: cargar un valor en un registro, almacenar un valor en memoria, saltar a una posición de memoria dada o realizar una operación aritmético-lógica, por ejemplo.

.. note::

    Hoy en día escribir programas en lenguaje máquina es muy raro.

Cada CPU tiene un juego de instrucciones. Si quieres programar en lenguaje máquina tienes que aprender a usar el juego de instrucciones de la CPU a programar, y no te servirá para otra CPU.

Por ejemplo, en las CPU de arquitectura MIPS todas las instrucciones son de 32 bits. Te muestro, a continuación, la instrucción que se usaría para cargar el valor que hay en la celda de memoria 68 a partir de la 8ª celda al registro número 8::

    100011 00011 01000 00000 00001 000100

Estos son los significados de los bits::

    100011    00011    01000    00000 00001 000100
   |------|  |-----|  |-----|  |------------------|
       |        |        |              |
       |        |        |              +---- Dirección de memoria: 68 en decimal
       |        |        |
       |        |        +------------------- Número a partir del cual se busca en memoria: 8 en decimal
       |        |
       |        +---------------------------- Número de registro donde se carga el valor: 3 en decimal
       |
       +------------------------------------- Código de operación: 35 en decimal

Lenguaje ensamblador
====================
Se trata de un lenguaje de bajo nivel, más sencillo de aprender y programar que el lenguaje máquina. Este lenguaje también es dependiente de la arquitectura de la CPU a programar.

En este lenguaje se usan **mnemotécnicos** que representan las instrucciones del microprocesador.

Los programas escritos en lenguaje ensamblador tienen que ser traducidos a lenguaje máquina para que se puedan ejecutar y, como en el caso del lenguaje máquina, no son portables de una CPU a otra.

.. note::

    Hoy en día tampoco se escriben programas en ensamblador salvo en casos muy concretos como: el *bootloader* de los sistemas operativos y otras partes del mismo que tienen que ver con la parte que arranca y carga el sistema operativo en la memoria.

Por ejemplo, en las CPU de arquitectura x86, para cargar el número 61 en hexadecimal (97 en decimal) al registro ``AL`` se haría de la siguiente manera en ensamblador::

    MOV AL, 61h

Una vez traducida esta instrucción a binario, lenguaje máquina, quedaría tal cual::

    10110000 01100001

Estos bits tienen el siguiente significado::

    1011   0000   01100001
       |     |         |
       |     |         |
       |     |         +------ Número 61 en hexadecimal o 97 en decimal
       |     |
       |     +---------------- Código para el registro AL (número 0 en decimal)
       |
       +---------------------- Código para la instrucción MOV (mover un valor a un registro)

Por último, te muestro un programa escrito en ensamblador para CPU de arquitectura x86 que suma los números 14 y 10:

.. code-block:: asm

    .globl main
        .type main, @function

    main:
        movl $14, %eax
        movl $10, %ebx
        add %eax, %ebx

.. note::

    En los lenguajes ensamblador, como ves, se usan identificadores para las instrucciones y registros de la CPU. Así, ``eax``, ``ebx`` o ``ebx`` son identificadores de tres de los registros de las CPU x86. Y ``movl`` o ``add`` son instrucciones de la arquitectura de CPU x86.

Lenguaje de alto nivel
======================
Estos lenguajes son fáciles de usar y aprender porque **usan un léxico, sintaxis y semántica cercano al ser humano**. Estos lenguajes ocultan los detalles de la arquitectura de la CPU a programar, no hace falta aprenderse el juego de instrucciones del microprocesador, lo que hace mucho más fácil la programación. Así pues, estos lenguajes no dependen de la arquitectura de la CPU.

Cuando aprendes a usar un lenguaje de alto nivel es fácil la transición a otro lenguaje. Por ejemplo, si aprendes a programar en ``Java`` te resultará muy fácil pasar a programar con ``PHP`` o ``Python`` por ejemplo.

Un ejemplo de programa en ``C`` que carga dos valores en memoria y los suma dejando el resultado en otra posición de memoria sería el siguiente:

.. code-block:: C

    int main(int argc, char **argv)
    {
        int num1, num2, resultado;

        num1 = 14;
        num2 = 10;

        resultado = num1 + num2;

        return 0;
    }

En resumen
==========

.. list-table:: Resumen de lenguajes de programación
    :widths: 33 33 33
    :header-rows: 1

    * - Lenguaje Máquina
      - Lenguaje Ensamblador
      - Lenguaje de Alto Nivel

    * - La programación es compleja
      - Facilita la programación aunque sigue siendo difícil escribir programas
      - La programación es fácil

    * - Las instrucciones son en binario
      - Se programa usando mnemotécnicos (instrucciones complejas)
      - Se utilizan sentencias y órdenes con un léxico, sintaxis y semántica cercano al lenguaje humano

    * - Estos programas se pueden ejecutar directamente
      - Necesita traducción al lenguaje máquina para poder ejecutarse
      - Necesita traducción al lenguaje máquina para poder ejecutarse

    * - Es único para cada procesador (no es portable de un equipo a otro)
      - Hay diferentes lenguajes de ensamblador por cada arquitectura de CPU
      - Son independientes de la CPU

    * - Hoy día nadie programa en este lenguaje
      - Se usa en caso muy concretos, sobre todo en el desarrollo de programas de sistema
      - Son los que se usan hoy en día
