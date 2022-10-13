Práctica entrenamiento 3: Git en local
**************************************
En esta práctica continuarás con el proyecto :file:`gitrain` que iniciaste en las prácticas de entrenamiento anteriores. Si no la tienes completada o quieres asegurarte que partes de donde lo debiste dejar, puedes descargar la segunda parte aquí: `segunda parte del proyecto gitrain <_static/gitrain2.zip>`__.

Recuerda hacer :command:`git status` y :command:`git log` cuando lo necesites.

Las **novedades** en esta parte son dos:

- Aprenderás a eliminar ficheros del repositorio de Git.
- Y, además, vas a ver cómo volver a un *commit* anterior.

Paso 1: eliminar fichero
========================
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

Paso 2: volver atrás, a un commit
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

Y, por último, tienes que realizar un commit con la opción **-a** para añadir los nuevos ficheros (el eliminado):

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
