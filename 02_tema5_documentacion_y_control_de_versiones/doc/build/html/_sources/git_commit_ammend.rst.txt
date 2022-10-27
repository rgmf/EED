Deshacer cosas
**************
Puedes leer la documentación de esta parte `en la web oficial de Git <https://git-scm.com/book/es/v2/Fundamentos-de-Git-Deshacer-Cosas#r_undoing>`__.

Cambiar último *commit*
========================
En esta parte te explico cómo deshacer un par de cosas habituales del último *commit*. 

Suele ser común que tras hacer un *commit* te des cuenta que has olvidado meter algunos cambios o que el mensaje que has añadido no es del todo bueno o lo has añadido con errores que quieres modificar.

En estos casos, hay una opción del comando :command:`git commit` que es :command:`--amend`.

Así, cuando quieras cambiar el último *commit* ejecuta el comando:

.. code-block:: console

    $ git commit --amend

Este comando añadirá los cambios al último *commit* y abrirá el editor de textos configurado para Git para que puedas modificar el mensaje. Si no hay cambios nuevos en el área de preparación o *stage* entonces simplemente podrás cambiar el mensaje del último *commit*.

.. important:: 

    Esta opción, en ningún caso, crea un nuevo *commit*, tan solo sobreescribe el último *commit*.

Por ejemplo, si confirmas y luego te das cuenta que olvidaste preparar los cambios de un archivo que querías incluir en esta confirmación, puedes hacer lo siguiente:

.. code-block:: console

    $ git commit -m "Cualquier mensaje"
    $ git add fichero_olvidado
    $ git commit --amend

Deshacer un fichero preparado
=============================
Aunque con el comando :command:`git status` puedes ver cómo hacerlo, no está de más recordarlo aquí.

Esta acción se realiza cuando hay ficheros en el área de preparación o *stage* que no quieres confirmar en tu siguiente *commit*. Por ejemplo, supongamos que has cambiado dos archivos y que quieres confirmarlos como dos cambios separados, pero accidentalmente has escrito :command:`git add .` y has preparado ambos. ¿Cómo puedes sacar del área de preparación uno de ellos? El comando git status te recuerda cómo:

.. code-block:: console

    $ git add .
    $ git status
    En la rama main
    Cambios a ser confirmados:
    (usa "git restore --staged <archivo>..." para sacar del área de stage)
        modificados:     README.md
        modificados:     CONTRIBUTING.md

Como ves, el comando :command:`git status` te dice cómo sacar del área de prearación o *stage* un fichero. Imagina que quieres sacar de dicha área el fichero :file:`CONTRIBUTING.md`, el comando a ejecutar será:

.. code-block:: console

    $ git restore --staged CONTRIBUTING.md

Tras este comando, el fichero :file:`CONTRIBUTING.md` está modificado pero no preparado para el siguiente *commit*.

.. code-block:: console

    $ git status
    En la rama main
    Cambios a ser confirmados:
    (usa "git restore --staged <archivo>..." para sacar del área de stage)
        modificados:     a.txt

    Cambios no rastreados para el commit:
    (usa "git add <archivo>..." para actualizar lo que será confirmado)
    (usa "git restore <archivo>..." para descartar los cambios en el directorio de trabajo)
        modificados:     b.txt

Deshacer cambios de un fichero
==============================
Si quieres descartar los cambios de un fichero, de nuevo, el comando :command:`git status` te dirá cómo hacerlo.

Primero lo tienes que sacar del área de preparación o *stage* y, a continuación, ejecutar el comando :command:`git restore`. Por ejemplo, imagina que quieres deshacer los cambios del fichero anterior :file:`CONTRIBUTING.md`. Ejecuta el comando:

.. code-block:: console

    $ git restore CONTCONTRIBUTING.md
