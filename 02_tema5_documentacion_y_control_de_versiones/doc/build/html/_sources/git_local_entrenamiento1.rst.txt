Práctica entrenamiento 1: Git en local
**************************************
Crea una carpeta en tu ordenador llamada :file:`gitrain`, entra en ella y sigue los pasos siguientes.

Antes, para el desarrollo de esta práctica necesitas tener instalado estos dos programas:

- Visual Studio Code.
- Git.

Paso 1: asegúrate que tienes configurado Git
============================================
Ya sabes que, antes de usar por primera vez Git, tienes que configurar, al menos:

- Tu nombre de usuario.
- Tu dirección de correo electrónico o e-mail.
- El editor de textos que usará Git cuando lo necesite.
- El nombre de la rama principal por defecto (nosotros vamos a usar siempre **main** como nombre de la rama principal).

Para comprobar que tienes Git ya configurado puedes ejecutar el siguiente comando:

.. code-block:: console

    $ git config --list

Y asegúrate que, dicho comando, muestra como resultado los cuatro atributos que hay que configurar, por ejemplo:

.. code-block:: console

    roman@t480:~$ git config --list
    user.email=rgmf@riseup.net
    user.name=Román Martínez
    init.defaultbranch=main
    core.editor=emacs

Paso 2: inicializa Git en la carpeta de tu proyecto (init)
==========================================================
Asegúrate que estás dentro de tu proyecto, es decir, dentro de la carpeta :file:`gitrain` y ejecuta el siguiente comando para inicializar Git:

.. code-block:: console

    $ git init

Tras este comando deberías ver una carpeta llamada :file:`.git` dentro de :file:`gitrain`.

.. note:: 
    Los ficheros y carpetas que empiezan por un punto, como es el caso de :file:`.git`, en GNU/Linux están ocultos y para verlas tienes que ejecutar el comando :command:`ls` con la opción :command:`-a`.

Paso 3: crear ficheros
======================
Abre la carpeta :file:`gitrain` con Visual Studio Code.

Crea un fichero de texto llamado :file:`README.md` con el siguiente contenido:

.. code-block:: markdown

    # Acerca de
    Proyecto de prueba con el objetivo de aprender cómo funciona Git.

    ## ¿Qués es Git?
    Git es un software de gestión de versiones muy utilizado en el mundo del desarrollo de aplicaciones.

Paso 4: ver el estado del repositorio (status)
==============================================
Para ver el estado en que se encuentra el repositorio, puedes ejecutar el siguiente comando (dentro de :file:`gitrain`):

.. code-block:: console

    $ git status

Verás un menaje como el siguiente:

.. code-block:: console

    En la rama main

    No hay commits todavía

    Archivos sin seguimiento:
      (usa "git add <archivo>..." para incluirlo a lo que se será confirmado)
	        README.md

    no hay nada agregado al commit pero hay archivos sin seguimiento presentes (usa "git add" para hacerles seguimiento)

Este mensaje nos indica que **hay un fichero nuevo sin seguimiento** por Git, el fichero que acabamos de crear :file:`README.md`.

En el siguiente paso te explico qué hacer para añadir estos ficheros al seguimiento de Git.

Paso 5: añadir ficheros nuevos al repositorio (add)
===================================================
Añade el fichero sin seguimiento :file:`README.md` al repositorio local de Git ejecutando este comando:

.. code-block:: console

    $ git add README.md

Si tuvieras muchos ficheros a añadir, divididos en carpetas, los podrías añadir todos puniendo un punto al final del :command:`git add`, tal que así:

.. code-block:: console

    $ git add .

Paso 6: ver el estado del repositorio (status)
==============================================
Ejecuta de nuevo el siguiente comando para ver el estado del repositorio:

.. code-block:: console

    $ git status

Verás la siguiente información:

.. code-block:: console

    En la rama main

    No hay commits todavía

    Cambios a ser confirmados:
    (usa "git rm --cached <archivo>..." para sacar del área de stage)
        nuevos archivos: README.md

Como ves, el nuevo fichero :file:`README.md` ya está dentro del siguimiento de Git pero no está confirmado.

En el siguiente paso te muestro cómo confirmar cambios.

Paso 7: confirmar cambios (commit)
==================================
Cuando quieres guarda una instantánea de tu proyecto, tal como está en ese momento, puedes confirmar los cambios con un *commit*. Ejecuta:

.. code-block:: console

    $ git commit

Y se abrirá el editor de textos que configuraste al principio para añadir un mensaje a dicha instantánea. Es **importante** que escribas mensajes en cada *commit* indicando brevemente qué cambios se han llevado a cabo desde la última instantánea o *commit*.

En este caso podrías escribir un mensaje como el siguiente: `He añadido un fichero README a mi proyecto.`.

Una pequeño atajo, cuando el mensaje va a ser tan corto como este es ejecutar el comando :command:`git commit` con la opción :command:`-m` seguido del mensaje entre comillas, tal que así:

.. code-block:: console

    $ git commit -m "He añadido un fichero README a mi proyecto."

Paso 8: ver estado del proyecto (status)
========================================
Ejecuta de nuevo el comando siguiente:

.. code-block:: console

    $ git status

Y verás que el repositorio está *limpio*, no hay nada nuevo:

.. code-block:: console

    En la rama main
    nada para hacer commit, el árbol de trabajo está limpio

Paso 9: ver el historial de cambios (log)
=========================================
Por último, otro comando básico de Git es el que nos permite ver el historial de cambios, es decir, el histórico de instantáneas o *commits* que hemos hecho. Ejecuta el comando siguiente:

.. code-block:: console

    $ git log

Y verás que solo hay un commit, puedes ver quién lo hizo, a qué hora, qué día, etc:

.. code-block:: console

    commit c7afc494c637463732d56711e9cc0da5bd274127 (HEAD -> main)
    Author: Román Martínez <rgmf@riseup.net>
    Date:   Thu Sep 22 17:44:35 2022 +0200

        He añadido un fichero README a mi proyecto.

Fíjate además en un dato muy importante, cada *commit* se lista con su suma de comprobación SHA-1, un código único para identificar cada *commit*. En este caso dicha suma de comprobación SHA-1 es `c7afc494c637463732d56711e9cc0da5bd274127`. En tu caso será diferente.
