Laboratorio 1: generación de código máquina
*******************************************
En este laboratorio vas a generar el código máquina de una programa escrito en lenguaje de programación de alto nivel ``C``.

Antes, tienes que instalar el compilador de ``C`` llamado ``gcc``. En los equipos del aula ya lo tienes instalado. Si usas tu portátil u ordenador y usas Windows puedes seguir los pasos que se indican en la siguiente web: `instalar gcc en Windows 10 <https://platzi.com/tutoriales/1469-algoritmos/1901-como-instalar-gcc-para-compilar-programas-en-c-desde-la-consola-en-windows/>`__.

Una vez tengas ``gcc`` instalado, sigue los pasos que se indican a continuación.

Paso 1: escribir el programa
============================
Copia y pega el código fuente que tienes aquí en tu editor de textos favorito y guárdalo con el nombre :file:`main.c`.

.. code-block:: c

    #include <stdio.h>

    int main (int argc, char **argv)
    {
        printf ("Números del 1 al 10:\n");
        for (int i = 1; i <= 10; i++)
        {
            printf("%d ", i);
        }
        printf("\n");

        return 0;
    }

Paso 2: genera el código ensamblador
====================================
Aunque no es necesario, en este paso vas a generar el código fuente en ensamblador equivalente.

Para ello, abre una terminal, sitúate en el directorio donde tienes el fichero con el código fuente :file:`main.c` y ejecuta el siguiente comando:

.. code-block:: console

    $ gcc -S main.c -o main.asm

Tras ejecutar dicho comando verás que hay un nuevo fichero :file:`main.asm` que contiene el código fuente en ensamblador.

Paso 3: genera el código objeto
===============================
Para obtener el código objeto, usa el compilador de ``C`` de la siguiente manera. Abre la terminal y situate donde está el fichero :file:`main.c` y ejecuta el compilador así:

.. code-block:: console

    $ gcc -c main.c -o main.o

Paso 4: inspeccionar el código objeto
=====================================
El código objeto no se puede visualizar. Intenta abrir el fichero :file:`main.o` para comprobar que no se puede ver nada, no es inteligible para el ser humano.

No obstante se puede desensamblar para inspeccionar el código objeto en hexadecimal. Abre la terminal y sitúate en el directorio donde está el fichero :file:`main.o` y ejecuta la siguiente orden:

.. code-block:: console

    $ objdump -d main.o > main.o.hex

Este comando genera una representación en hexadecimal, con sus respectivos mnemotécnicos en ensamblador, y lo guarda en el fichero :file:`main.o.hex`. Ábrelo para verlo.

Paso 5: generar el código máquina ejecutable
============================================
El código objeto :file:`main.o` no se puede ejecutar, porque falta enlazarlo con bibliotecas del lenguaje ``C``, entre otras cosas.

Para poder ejecutar el programa que escribiste en el Paso 1 usando el lenguaje de programación ``C``, tienes que compilar de la siguiente forma:

.. code-block:: console

    $ gcc main.c -o main

Como siempre, antes de ejecutar ese comando tienes que situarte en el directorio donde está el fichero :file:`main.c`. Verás que se generará un fichero, con el código máquina ejecutable, llamado :file:`main`.

Paso 6: ejecuta el programa
===========================
Tienes que ejecutar el código máquina ejecutable que tienes en el fichero :file:`main`. Abre la termina, sitúate en el directorio donde está el programa (fichero :file:`main`) y ejecútalo tal que así:

.. code-block:: console

    $ ./main

Verás que muestra los primeros 10 números.

Entrega
=======
Hazme entrega de los siguientes ficheros:

- :file:`main.c`
- :file:`main.asm`
- :file:`main.o`
- :file:`main.o.hex`
- :file:`main`

Criterios de evaluación
=======================
En esta práctica se aplica el ``Resultado de Aprendizaje 1: reconoce los elementos y herramientas que intervienen en el desarrollo de un programa informático, analizando sus características y las fases en las que actúan hasta llegar a su puesta en funcionamiento.``. Y en concreto los siguientes criterios de evaluación:

- c) Se han diferenciado los conceptos de código fuente, código objeto y código ejecutable. (20%)
- d) Se han reconocido las características de la generación de código intermedio para su ejecución en máquinas virtuales. (10%)
