Práctica entrenamiento 3: Git en local
**************************************
En esta práctica continuarás con el proyecto :file:`gitrain` que iniciaste en las prácticas de entrenamiento anteriores. Si no la tienes completada o quieres asegurarte que partes de donde lo debiste dejar, puedes descargar la segunda parte aquí: `segunda parte del proyecto gitrain <_static/gitrain2.zip>`__.

Recuerda hacer :command:`git status` y :command:`git log` cuando lo necesites.

Las **novedades** en esta parte son:

- Aprenderás a modificar ficheros.
- Aprenderás a eliminar ficheros.
- Aprenderás la diferencia entre ficheros no **rastreados** y ficheros sin **seguimiento**.

Paso 1: modificaciones en el repositorio
========================================
Abre el fichero :file:`java.txt` y añade, al final del fichero, el siguiente texto::

    El lenguaje de programación Java fue desarrollado originalmente por James Gosling, 
    de Sun Microsystems (constituida en 1983 y posteriormente adquirida el 27 de enero
    de 2010 por la compañía Oracle)

Paso 2: eliminar fichero
========================
Elimina el fichero :file:`c.txt`.

Paso 3: añadir un nuevo fichero
===============================
Crea un nuevo fichero dentro de :file:`src/txt/` con el nombre :file:`python.txt` y el siguiente texto::

    Python is a high-level, general-purpose programming language.
    Its design philosophy emphasizes code readability with the use 
    of significant indentation.

Paso 3: ver estado
==================
Si ejecutas un :command:`git status` verás la siguiente información:

.. code-block:: console

    En la rama main
    Cambios no rastreados para el commit:
    (usa "git add/rm <archivo>..." para actualizar a lo que se le va a hacer commit)
    (usa "git restore <archivo>..." para descartar los cambios en el directorio de trabajo)
        borrados:        src/txt/c.txt
        modificados:     src/txt/java.txt

    Archivos sin seguimiento:
    (usa "git add <archivo>..." para incluirlo a lo que se será confirmado)
        src/txt/python.txt

    sin cambios agregados al commit (usa "git add" y/o "git commit -a")

Como ves, aparecen **cambios no rastreados** y **archivos sin seguimiento**. ¿Qué diferencia hay?

- Los cambios **no rastreados** son cambios sobre ficheros que ya existían en el último *commit* que no están en el área de preparación o *stage*.
- Los archivos **sin seguimiento** son archivos que no están en el último *commit* (son nuevos) y que no se han añadido al área de preparación o *stage*.

En general hay tres cambios:

- Eliminado el fichero :file:`src/txt/c.txt`,
- Modificado el fichero :file:`src/txt/java.txt` y
- Nuevo fichero :file:`src/txt/python.txt`.

De momento, estos cambios no están preparados para el siguiente *commit*, es decir, no están en el stado *stage*.

Paso 4: preparar siguiente commit
=================================
Vamos a preparar el siguiente *commit* (instantánea) con todos los cambios realizados. Para ello, hay que añadir todos los cambios anteriores al área de preparación o *stage*. ¿Cómo? con el comando :command:`git add` como ves a continuación:

.. code-block:: console

    $ git add src/txt/c.txt src/txt/java.txt src/txt/python.txt

Ahora, si ejecutas el comando :command:`git status` verás la siguiente información:

.. code-block:: console

    En la rama main
    Cambios a ser confirmados:
    (usa "git restore --staged <archivo>..." para sacar del área de stage)
        borrados:        src/txt/c.txt
        modificados:     src/txt/java.txt
        nuevos archivos: src/txt/python.txt

Como ves, ahora sí están preparados todos los cambios para realizar el *commit*, es decir, la instantánea.

Paso 5: hacer el commit
=======================
Realiza el *commit* añadiendo el siguiente mensaje: `Quitado C, añadido Python y ampliado Java.`

Paso 6: revisa el historial
===========================
Si echas un vistazo al historial deberías ver los siguientes *commits*:

.. code-block:: console

    commit 8f8b69a5856e9ddbb3e4ab7aca24aec5bef1be27 (HEAD -> main)
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
