Práctica entrenamiento 5: Git en local
**************************************
En esta práctica continuarás con el proyecto :file:`gitrain` que iniciaste en las prácticas de entrenamiento anteriores. Si no la tienes completada o quieres asegurarte que partes de donde lo debiste dejar, puedes descargar la cuarta parte aquí: `cuarta parte del proyecto gitrain <_static/gitrain4.zip>`__.

Recuerda hacer :command:`git status` y :command:`git log` cuando lo necesites.

La **novedad** en esta práctica guiada es que:

- Aprenderás a configurar Git para ignorar ciertos ficheros.

Paso 1: escribe un programa en Java
===================================
Crea una carpeta dentro de :file:`src` llamada :file:`java`. Ahora, dentro de esa carpeta :file:`java` crea un fichero :file:`Main.java` con un programa en Java que genere un número aleatorio entre 1 y 10 y lo muestre por pantalla:

.. code-block:: java

    import java.lang.Math;

    public class Main {
        public static void main(String[] args) {
            int numero = (int) (Math.random() * 10 + 1);
            System.out.println("El número que ha salido es: " + numero);
        }
    }

Paso 2: añade el nuevo fichero al área *stage*
===============================================
Añade el nuevo fichero :file:`Main.java` al aréa de preparación o *stage*.

Paso 3: compila el programa anterior
====================================
Entra a la carpeta donde está el programa en Java anterior y compílalo para obtener el :file:`Main.class`:

.. code-block:: console

    $ javac Main.java

Verás que se ha generado en el mismo lugar dicho fichero :file:`Main.class` y, por eso, puedes ejecutarlo:

.. code-block:: console

    $ java Main

Paso 4: fíjate en el estado de git
==================================
Si ejecutas un :command:`git status` verás que hay dos nuevos ficheros sin rastrear:

.. code-block:: console

    $ git status
    En la rama main
    Cambios a ser confirmados:
    (usa "git restore --staged <archivo>..." para sacar del área de stage)
        nuevos archivos: src/java/Main.java

    Archivos sin seguimiento:
    (usa "git add <archivo>..." para incluirlo a lo que se será confirmado)
        src/java/Main.class

Como ves aparece el fichero :file:`Main.java` en el área de preparación listo para el siguiente *commit* que venga y el fichero :file:`Main.class` fuera del seguimiento de Git.

Paso 5: creando y configurando .gitignore
=========================================
Crea el fichero :file:`.gitignore` dentro de la raíz del proyecto y escribe en él el patrón necesario para que Git ignore los ficheros :file:`.class` estén dónde estén.

Puedes probar si funciona el patrón ejecutando de nuevo el :command:`git status` y no debería aparecer el :file:`Main.class` por ningún lado, sino lo siguiente:

.. code-block:: console

    En la rama main
    Cambios a ser confirmados:
    (usa "git restore --staged <archivo>..." para sacar del área de stage)
        nuevos archivos: src/java/Main.java

    Archivos sin seguimiento:
    (usa "git add <archivo>..." para incluirlo a lo que se será confirmado)
        .gitignore

Paso 6: añade .gitignore al área *stage*
========================================
Añade el fichero :file:`.gitignore` al área de preparación o *stage*.

En el estado de Git verás:

.. code-block:: console

    En la rama main
    Cambios a ser confirmados:
    (usa "git restore --staged <archivo>..." para sacar del área de stage)
        nuevos archivos: .gitignore
        nuevos archivos: src/java/Main.java

Paso 7: crea el nuevo *commit*
===============================
Crea un nuevo *commit* con los cambios y el mensaje: `Añadido .gitignore y programa en Java.`

Paso 8: ver el historial de cambios
===================================
Si ejecutas el comando de Git para ver el histórico de cambios deberías ver estos 6 *commits*:

.. code-block:: console

    commit da5acbb0dd35da1145506d5d17868733f2449b4c (HEAD -> main)
    Author: Román Martínez <rgmf@riseup.net>
    Date:   Thu Oct 27 20:00:25 2022 +0200

        Añadido .gitignore y programa en Java.

    commit b1f80a9d4f67a7fe4b0d3070848c0e7bdc8b2e05
    Author: Román Martínez <rgmf@riseup.net>
    Date:   Thu Oct 27 17:12:23 2022 +0200

        Nuevo fichero done se explica qué es PHP.
        Traducido al español el fichero de Python.

    commit 8f8b69a5856e9ddbb3e4ab7aca24aec5bef1be27
    Author: Román Martínez <rgmf@riseup.net>
    Date:   Thu Oct 27 15:13:02 2022 +0200

        Quitado C, añadido Python y ampliado Java.

    commit c0841983944a4fd9edfc0f6316af76e84327c7f6
    Author: Román Martínez <rgmf@riseup.net>
    Date:   Thu Oct 13 13:40:34 2022 +0200

        Añadidos ficheros de texto con información sobre C y Java.

    commit 4cd4a901e559b54ff2953296a71a75570bb8cae2
    Author: Román Martínez <rgmf@riseup.net>
    Date:   Thu Oct 13 13:39:28 2022 +0200

        Logotipos de Java añadidos al proyecto.

    commit c7afc494c637463732d56711e9cc0da5bd274127
    Author: Román Martínez <rgmf@riseup.net>
    Date:   Thu Sep 22 17:44:35 2022 +0200

        He añadido un fichero README a mi proyecto.
