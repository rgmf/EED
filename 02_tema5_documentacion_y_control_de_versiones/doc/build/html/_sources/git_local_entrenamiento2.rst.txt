Práctica entrenamiento 2: Git en local
**************************************
En esta práctica continuarás con el proyecto :file:`gitrain` que iniciaste en la práctica de entrenamiento 1.

Para desarrollar esta segunda parte necesitas haber completado la primera de las partes. Si no la tienes completada o quieres asegurarte que partes de donde lo debiste dejar, puedes descargar la primera parte aquí: `primera parte del proyecto gitrain <_static/gitrain1.zip>`__.

En esta segunda parte de entrenamiento voy a ser menos explícito, las instrucciones no van a venir acompañadas de los comandos ni los detalles a realizar.

Recuerda hacer :command:`git status` y :command:`git log` cuando lo necesites.

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
Descarga la siguiente imagen y guárdala en la carpeta :file:`jpg`:

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

- Fichero de texto con nombre :file:`java.txt` y el siguiente contenido:

.. code-block:: text

    Java es un lenguaje de programación y una plataforma informática que fue
    comercializada por primera vez en 1995 por Sun Microsystems.

Paso 5: añadir ficheros de texto
================================
Añade los dos ficheros de texto que acabas de crear al seguimiento de Git y crea un commit con el mensaje **Añadidos ficheros de texto con información sobre C y Java.**.

Paso 6: ver el estado del repositorio
=====================================
Si ejecutas un :command:`git log`, para ver el historial de cambios (de *commits*), verás la siguiente información (3 *commits*):

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
