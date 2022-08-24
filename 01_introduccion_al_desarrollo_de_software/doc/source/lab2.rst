Laboratorio 2: generación de bytecode
*************************************
En este laboratorio vas a generar el código intermedio bytecode de Java desensamblado, para poder visualizar, qué aspecto tiene dicho código intermedio.

Antes, tienes que instalar el ``JDK``. En los equipos del aula ya está instalado, así que solo lo tienes que hacer en tu ordenador o portátil siempre que este *lab* lo vayas a realizar desde tu equipo personal.

Paso 1: escribir el programa
============================
Copia y pega el código fuente en Java que tienes aquí en tu editor de textos favorito y guárdalo con el nombre :file:`Main.java`.

.. code-block:: Java

    public class Main {
        public static void main(String[] args) {
            System.out.println("Números del 1 al 10:");
            for (int i = 1; i <= 10; i++) {
                System.out.print(i + " ");
            }
            System.out.println();
        }
    }

Paso 2: compilar programa en Java
=================================
Cuando tenemos un programa en Java en un simple fichero, compilar dicho programa es muy sencillo (sin ayuda de IDEs ni herramientas gráficas).

Tan solo tienes que abrir una terminal, situarte donde está el fichero :file:`Main.java` y ejecutar el compilador de Java :command:`javac` tal que así:

.. code-block:: console

    $ javac Main.java

Tras ejecutar este comando verás que se ha generado un fichero con el mismo nombre pero con extensión ``.class``, en este ejemplo :file:`Main.class`, que contiene el *bytecode* de Java ejecutable por la ``JVM`` o Máquina Virtual de Java.

Si intentas abrir este ``.class`` con un editor verás una serie de símbolos sin sentido. Recuerda que el código objeto es ininteligible para el ser humano.

Paso 3: análisis del bytecode
=============================
Cuando no dispones de los ficheros con el código fuente en Java, puedes usar la herramienta ``javap`` para desensamblar un fichero ``.class`` tal que así:

.. code-block:: console

    $ javap -c Main.class > Main.dis

Tras ejecutar dicho comando verás el código desensamblado en el fichero llamado :file:`Main.dis`. Ábrelo con tu editor de textos favorito y observa el resultado.

Paso 4: visualizar el código máquina
====================================
Para poder echar un vistazo al código máquina, en formato hexadecimal, de un programa compilado en Java, debes usar el siguiente comando:

.. code-block:: console

    $ java -XX:+UnlockDiagnosticVMOptions -XX:+PrintAssembly Main > Main.asm

Donde:

- **java**: se trata del comando que llama a la máquina virtual de Java para ejecutar un programa.
- **-XX:+UnlockDiagnosticVMOptions**: es una opción necesaria para ver el código máquina.
- **-XX:+PrintAssembly**: es para que te muestre el código ensamblador en hexadecimal.
- **Main**: es el nombre del programa (coincide con el nombre de la clase a ejecutar).
- **Main.asm**: nombre del fichero donde escribe el resultado.

Este comando escribe el contenido en un fichero llamado :file:`Main.asm`. Ábrelo con tu editor de textos favorito y observa el resultado.

Entrega
=======
Hazme entrega de los siguientes ficheros:

- :file:`Main.java`
- :file:`Main.class`
- :file:`Main.dis`
- :file:`Main.asm`

Criterios de evaluación
=======================
En esta práctica se aplica el ``Resultado de Aprendizaje 1: reconoce los elementos y herramientas que intervienen en el desarrollo de un programa informático, analizando sus características y las fases en las que actúan hasta llegar a su puesta en funcionamiento.``. Y en concreto los siguientes criterios de evaluación:

- c) Se han diferenciado los conceptos de código fuente, código objeto y código ejecutable. (20%)
- d) Se han reconocido las características de la generación de código intermedio para su ejecución en máquinas virtuales. (10%)
