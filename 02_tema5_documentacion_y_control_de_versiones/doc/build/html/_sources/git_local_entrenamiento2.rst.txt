Práctica entrenamiento 2: Git en local
**************************************
En esta práctica continuarás con el proyecto **gitrain** que iniciaste en la práctica de entrenamiento 2.

Para desarrollar esta segunda parte necesitas haber completado la primera de las partes. Si no la tienes completada o quieres asegurarte que partes de donde lo debiste dejar, puedes descargar la primera parte aquí: `primera parte del proyecto gitrain <_static/gitrain1.zip>`__.

En esta segunda parte de entrenamiento voy a ser menos explícito, las instrucciones no van a venir acompañadas de los comandos ni los detalles a realizar.

Recuerda hacer :command:`git status` y :command:`git log` cuando lo necesites.

La **novedad** en este ejercicio se encuentra en el último punto donde aprenderás a volver a un *commit* anterior para deshacer una serie de cambios. En este último punto voy a ser bastante explícito. Si no lo entiendes no dudes en preguntar.

Paso 1: jerarquía de directorios
================================
Crea dentro de la carpeta :file:`gitrain` la siguiente jerarquía de directorios:

.. figure:: ./img/gitrain_jerarquia.png
    :width: 60%
    :align: center

.. important:: 
    Las carpetas no se tienen (ni se pueden) añadir al repositorio Git. Más adelante, cuando se incluyan ficheros dentro de las carpetas se irán añadiendo dichas carpetas contenedoras.

Paso 2: descargar imágenes
==========================
Descarga la siguiente imagen y guárdala en la carpeta :file:`img`:

.. figure:: ./img/java_logo.jpg
    :width: 40%
    :align: center

Y descarga la siguiente imagen y guárdala en la carpeta :file:`png`:

.. figure:: ./img/java_logo.png
    :width: 25%
    :align: center

Paso 3: añadir imágenes
=======================
Añade las dos imágenes anteriores al seguimiento de Git y crea un commit con el mensaje **Logotipos de Java añadidos al proyecto.**.

Paso 4: crear ficheros de texto
===============================
En la carpeta :file:`txt` crea los siguientes ficheros de texto:

- Fichero de texto con nombre :file:`c.txt` y el siguiente contenido:

.. code-block:: text

    C es un lenguaje de programación de propósito general originalmente
    desarrollado por Dennis Ritchie entre 1969 y 1972 en los Laboratorios Bell.

- Fichero de texto con nombre :file:`java.txt` y el seguiente contenido:

.. code-block:: text

    Java es un lenguaje de programación y una plataforma informática que fue
    comercializada por primera vez en 1995 por Sun Microsystems.

Paso 5: añadir ficheros de texto
================================
Añade los dos ficheros de texto que acabas de crear al seguimiento de Git y crea un commit con el mensaje **Añadidos ficheros de texto con información sobre C y Java.**.

Paso 6: eliminar fichero
========================
Si ejecutas un :command:`git log` para ver el historial de cambios (de *commits*) verás las siguiente información (3 *commits*):

.. code-block:: console

    commit ccfa4ff42ec4682d0d352d92c1065c01e9ffd0b5 (HEAD -> main)
    Author: Román Martínez <rgmf@riseup.net>
    Date:   Sun Sep 25 18:08:44 2022 +0200

        Añadidos ficheros de texto con información sobre C y Java.

    commit 8c307e2f754dc2861bbc5632b501c8badc2dbcad
    Author: Román Martínez <rgmf@riseup.net>
    Date:   Sun Sep 25 18:02:36 2022 +0200

        Logotipos de Java añadidos al proyecto.

    commit c7afc494c637463732d56711e9cc0da5bd274127
    Author: Román Martínez <rgmf@riseup.net>
    Date:   Thu Sep 22 17:44:35 2022 +0200

        He añadido un fichero README a mi proyecto.

Elimina el fichero :file:`java.txt` y ejecuta un :command:`git status`. Verás la siguiente información:

.. code-block:: console

    En la rama main
    Cambios no rastreados para el commit:
        (usa "git add/rm <archivo>..." para actualizar a lo que se le va a hacer commit)
        (usa "git restore <archivo>..." para descartar los cambios en el directorio de trabajo)
            borrados:        src/txt/java.txt

    sin cambios agregados al commit (usa "git add" y/o "git commit -a")

Como ves nos indica que se ha borrado el fichero :file:`src/txt/java.txt` pero este cambio no tiene seguimiento en Git todavía. Tienes que hacer un :command:`git add` o :command:`git rm` como sigue:

.. code-block:: console

    $ git rm src/txt/java.txt

Ahora sí, si ejecutas de nuevo el :command:`git status` verás que el fichero :file:`java.txt` ha sido eliminado del repositorio de Git.

Finalmente, ya sabes, tienes que confirmar el cambio con un *commit*:

.. code-block:: console

    $ git commit -m "Elimando el fichero java.txt."

Paso 7: volver atrás, a un commit
=================================
Si ejecutas el comando :command:`log` de Git verás el siguiente histórico de *commits*:

.. code-block:: console

    commit 3e38219ddfdb09abd0a03a9d0e63eb24390a0e00 (HEAD -> main)
    Author: Román Martínez <rgmf@riseup.net>
    Date:   Sun Sep 25 19:01:36 2022 +0200

        Elimando el fichero java.txt.

    commit ccfa4ff42ec4682d0d352d92c1065c01e9ffd0b5
    Author: Román Martínez <rgmf@riseup.net>
    Date:   Sun Sep 25 18:08:44 2022 +0200

        Añadidos ficheros de texto con información sobre C y Java.

    commit 8c307e2f754dc2861bbc5632b501c8badc2dbcad
    Author: Román Martínez <rgmf@riseup.net>
    Date:   Sun Sep 25 18:02:36 2022 +0200

        Logotipos de Java añadidos al proyecto.

    commit c7afc494c637463732d56711e9cc0da5bd274127
    Author: Román Martínez <rgmf@riseup.net>
    Date:   Thu Sep 22 17:44:35 2022 +0200

        He añadido un fichero README a mi proyecto.

Imagina que quieres volver al commit **ccfa4ff42ec4682d0d352d92c1065c01e9ffd0b5**, es decir, al punto en el que tenías el fichero :file:`java.txt` en el repositorio, porque te has arrepentido y quieres recuperar dicho fichero.

Existen dos posibilidades:

Primera opción:
---------------
Si solo quieres recuperar el fichero borrado bastaría con ejecutar el comando:

.. code-block:: console
    
    $ git checkout ccfa4ff42ec4682d0d352d92c1065c01e9ffd0b5 .

No olvides el punto final.

Y, por último, tienes que realizar un commit con la opción **-a** para añadir los nuevos fichero (el eliminado):

.. code-block:: console

    $ git commit -am "Restaurado desde el commit."


Si haces un :command:`git log` verás que hay un nuevo commit, el que acabamos de crear:

.. code-block:: console

    commit 5b2d351658c4b47c874400c0332f35edd186cbf3 (HEAD -> main)
    Author: Román Martínez <rgmf@riseup.net>
    Date:   Sun Sep 25 19:15:53 2022 +0200

        Restaurado desde el commit.

    commit 3e38219ddfdb09abd0a03a9d0e63eb24390a0e00
    Author: Román Martínez <rgmf@riseup.net>
    Date:   Sun Sep 25 19:01:36 2022 +0200

        Elimando el fichero java.txt.

    commit ccfa4ff42ec4682d0d352d92c1065c01e9ffd0b5
    Author: Román Martínez <rgmf@riseup.net>
    Date:   Sun Sep 25 18:08:44 2022 +0200

        Añadidos ficheros de texto con información sobre C y Java.

    commit 8c307e2f754dc2861bbc5632b501c8badc2dbcad
    Author: Román Martínez <rgmf@riseup.net>
    Date:   Sun Sep 25 18:02:36 2022 +0200

        Logotipos de Java añadidos al proyecto.

    commit c7afc494c637463732d56711e9cc0da5bd274127
    Author: Román Martínez <rgmf@riseup.net>
    Date:   Thu Sep 22 17:44:35 2022 +0200

        He añadido un fichero README a mi proyecto.

Segunda opción:
---------------
En este caso sería la mejor opción de todas. Hacer un **hard reset** al commit al que quieres volver.

Recordemos el historial desde el que partimos:

.. code-block:: console

    commit 3e38219ddfdb09abd0a03a9d0e63eb24390a0e00 (HEAD -> main)
    Author: Román Martínez <rgmf@riseup.net>
    Date:   Sun Sep 25 19:01:36 2022 +0200

        Elimando el fichero java.txt.

    commit ccfa4ff42ec4682d0d352d92c1065c01e9ffd0b5
    Author: Román Martínez <rgmf@riseup.net>
    Date:   Sun Sep 25 18:08:44 2022 +0200

        Añadidos ficheros de texto con información sobre C y Java.

    commit 8c307e2f754dc2861bbc5632b501c8badc2dbcad
    Author: Román Martínez <rgmf@riseup.net>
    Date:   Sun Sep 25 18:02:36 2022 +0200

        Logotipos de Java añadidos al proyecto.

    commit c7afc494c637463732d56711e9cc0da5bd274127
    Author: Román Martínez <rgmf@riseup.net>
    Date:   Thu Sep 22 17:44:35 2022 +0200

        He añadido un fichero README a mi proyecto.

Queremos volver al *commit* identificado por **ccfa4ff42ec4682d0d352d92c1065c01e9ffd0b5**. Pues bien, para volver a él, basta con ejecutar el siguiente comando:

.. code-block:: console

    $ git reset --hard ccfa4ff42ec4682d0d352d92c1065c01e9ffd0b5

Por último, si haces un :command:`git log` para ver el historial, lo que vas a ver es que hemos vuelto al commit anterior, deshaciendo todo lo hecho en el último commit, en el que borramos el fichero :file:`java.txt`:

.. code-block:: console

    commit ccfa4ff42ec4682d0d352d92c1065c01e9ffd0b5 (HEAD -> main)
    Author: Román Martínez <rgmf@riseup.net>
    Date:   Sun Sep 25 18:08:44 2022 +0200

        Añadidos ficheros de texto con información sobre C y Java.

    commit 8c307e2f754dc2861bbc5632b501c8badc2dbcad
    Author: Román Martínez <rgmf@riseup.net>
    Date:   Sun Sep 25 18:02:36 2022 +0200

        Logotipos de Java añadidos al proyecto.

    commit c7afc494c637463732d56711e9cc0da5bd274127
    Author: Román Martínez <rgmf@riseup.net>
    Date:   Thu Sep 22 17:44:35 2022 +0200

        He añadido un fichero README a mi proyecto.
