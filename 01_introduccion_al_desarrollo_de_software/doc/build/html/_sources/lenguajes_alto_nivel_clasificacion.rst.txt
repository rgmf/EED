Lenguajes de alto nivel: clasificación
**************************************
En el apartado anterior ya estudiamos la evolución histórica de los lenguajes de programación: máquina, ensamblador y alto nivel.

En este apartado nos vamos a centrar en los lenguajes de alto nivel, que al final son estos con los que vas a aprender a programar en este ciclo.

Dentro del mundo de los lenguajes de alto nivel existen varios paradigmas que determinan, en cierto modo, cómo se escriben y estructuran los programas. Algunos de los paradigmas más populares son: programación estructurada, programación modular y programación orientada a objetos (POO).

.. seealso::

    **Speedcoding**, **Speedcode** o **SpeedCo** es el primer lenguaje de alto nivel, creado para un ordenador IBM 701 por John W. Backus en 1953.

    No obstante, el primer lenguaje con cierta popularidad fue **Fortran**, creado por la propia IBM en 1957. Hoy en día se sigue usando.

    Fue en 1972, cuando Dennis Ritchie  diseñó el lenguaje **C** que ha influenciado a casi la totalidad de lenguajes populares de hoy en día, como **C++**, **Java**, **Python**, **PHP** o **JavaScript**, por ejemplo. Hoy en día, **C** es ampliamente utilizado para la creació de programas de sistema como son los sistemas operativos y aplicaciones para sistemas embebidos.

Código espagueti: paradigma a evitar
====================================
El código espagueti es un **término peyorativo** para los programas de computación que tienen una estructura de control de flujo compleja e incomprensible. Su nombre deriva del hecho que este tipo de código parece asemejarse a un plato de espaguetis, es decir, un montón de hilos intrincados y anudados.

Tradicionalmente suele asociarse este estilo de programación con lenguajes básicos y antiguos, donde el flujo se controlaba mediante sentencias de control muy primitivas como goto y utilizando números de línea.

Para evitar este *paradigma* hay que emplear alguno de los paradigmas que te explico en los siguientes apartados.

Programación estructurada
=========================
Este es un paradigma de programación cuyo objetivo es mejorar la claridad, calidad y el tiempo de desarrollo de los programas haciendo un uso extensivo de:

- Estructuras de control de selección del flujo :code:`if/then/else`.
- Estructuras de control de repetición (bucles) :code:`while` y :code:`for`.
- Estructuras de bloque: bloques de código relacionados y agrupados de alguna manera.
- Subrutinas: secuencias de instrucciones del programa que realizan una tarea específica, agrupadas como una unidad.

.. note::

    En diferentes lenguajes de programación, a las **subrutinas** se les puede llamar: **rutina**, **subprograma**, **función**, **método** o **procedimiento**.

Las ventajas de este paradigma son:

- Los programas son más fáciles de entender y leer.
- Los programas son más rápidos.
- La estructura de los programas es clara.
- Se construyen programas con más rapidez.
- Se facilita la depuración y detección de errores.
- Se reducen los costes de mantenimiento.

Los inconvenientes de este paradigma son:

- Todo el programa se concentra en un único bloque (si se hace demasiado grande es difícil de manejar y mantener).
- No permite reutilización eficaz de código, ya que todo va "en uno". Es por esto que a la programación estructurada le sustituyó  la programación modular, donde los programas se codifican por módulos y bloques, permitiendo mayor funcionalidad.

.. note::

    Ejemplos de lenguajes estructurados: **Fortran**, **Pascal** y **C**.

Programación modular
====================
La programación modular es un paradigma de programación que consiste en dividir un programa en módulos o subprogramas con el fin de hacerlo más legible y manejable.

Se presenta históricamente como una evolución de la programación estructurada para solucionar problemas de programación más grandes y complejos de lo que esta puede resolver.

Esto se suele traducir en que un programa está formado por varios ficheros, y en la práctica cada fichero sería un modulo, una parte del programa, que se ha dividido en diferentes piezas.

Está a medio camino entre la programación estructurada y la programación orientada a objetos.

Programación orientada a objetos
================================
Después de comprender que la programación estructurada no es útil cuando los programas se hacen muy largos, es necesaria otra  técnica de programación que solucione este inconveniente. Nace así la programación orientada a objetos.

Los lenguajes de programación orientados a objetos tratan a los programas no como un conjunto ordenado de instrucciones (tal como sucedía en la programación estructurada) sino como un conjunto de objetos que colaboran entre ellos para realizar acciones.

Su primera desventaja es clara: no es una programación tan intuitiva como la estructurada.

A pesar de eso, mucho del software que produce se hace usando esta técnica por las siguientes razones:

- El código es reutilizable.
- Si hay algún error, es más fácil de localizar y depurar en un objeto que en un programa entero.

.. note::

    Ejemplos de lenguajes orientados a objetos: **C++** y **Java**.
