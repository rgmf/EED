Práctica entrenamiento 4: Git en local
**************************************
En esta práctica continuarás con el proyecto :file:`gitrain` que iniciaste en las prácticas de entrenamiento anteriores. Si no la tienes completada o quieres asegurarte que partes de donde lo debiste dejar, puedes descargar la tercera parte aquí: `tercera parte del proyecto gitrain <_static/gitrain3.zip>`__.

Recuerda hacer :command:`git status` y :command:`git log` cuando lo necesites.

La **novedad** en esta práctica guiada es que:

- Vas a aprender a cambiar los mensajes de un *commit*.

Paso 1: añadir nuevo fichero
============================
Añade un fichero :file:`src/txt/php.txt` con el texto siguiente::

    PHP es un lenguaje de programación de uso general que se adapta especialmente al desarrollo web.
    Fue creado inicialmente por el programador danés-canadiense Rasmus Lerdorf en 1994.
    En la actualidad, la implementación de referencia de PHP es producida por The PHP Group.

Paso 2: modificar un fichero
============================
Ahora, cambia el contenido de :file:`src/txt/python.txt` cuyo mensaje escribimos en inglés y lo vamos a pasar al español::

    Python es un lenguaje de alto nivel de programación interpretado cuya filosofía hace
    hincapié en la legibilidad de su código, se utiliza para desarrollar aplicaciones de todo tipo.
    Se trata de un lenguaje de programación multiparadigma, ya que soporta parcialmente la 
    orientación a objetos, programación imperativa y, en menor medida, programación funcional.
    Es un lenguaje interpretado, dinámico y multiplataforma.

Paso 3: preparar *commit*
=========================
Para preparar el *commit*, añade los cambios al área de preparación o *stage*.

Paso 4: hacer *commit*
======================
Ya puedes hacer el *commit* con el siguiente mensaje: `Algunos cambios.`

Paso 5: cambiar el mensaje del último *commit*
===============================================
Imagina que nos arrepentimos del mensaje del último *commit*, que hemos cometido un error al escribirlo o cualquier otra circunstancia que nos lleva a querer cambiar el mensaje. ¿Cómo lo hacemos? Te lo explico.

Git ofrece la opción :command:`--amend` para el comando :command:`git commit` que se utiliza cuando olvidas agregar algún cambio a tu último *commit* o quieres cambiar el mensaje de este último *commit*.

Este comando utiliza tu área de preparación para la confirmación. Si no has hecho cambios desde tu última confirmación (por ejemplo, ejecutas este comando justo después de tu confirmación anterior), entonces la instantánea lucirá exactamente igual y lo único que cambiarás será el mensaje de confirmación.

Ahora mismo, nosotros no tenemos cambios en el área de preparación desde el último *commit* pero queremos cambiar su mensaje. Si haces un :command:`git log` verás que tenemos un último *commit* con el mensaje "Algunos cambios." (mensaje que queremos cambiar):

.. code-block:: console

    commit cb7945702b25f0b396921cc6faa2fbfdd6fe3a24 (HEAD -> main)
    Author: Román Martínez <rgmf@riseup.net>
    Date:   Thu Oct 27 17:12:23 2022 +0200

        Algunos cambios.

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

El nuevo mensaje que queremos para este último *commit* es::

    Nuevo fichero done se explica qué es PHP.
    Traducido al español el fichero de Python.

Tenemos dos opciones para cambiar el mensaje:

- Con :command:`git commit --amend` se abrirá un editor de textos para cambiar el mensaje del último *commit*.
- Con :command:`git commit --amend -m "Nuevo mensaje"` que cambiaría el mensaje por "Nuevo mensaje".

¿Por qué opción optarías en este caso? Tienes que optar por la primera opción ya que el nuevo mensaje que queremos tiene dos líneas.

Paso 6: revisa el cambio de mensaje
===================================
¿Cómo puedes comprobar que el mensaje ha sido cambiado? Exactamente, con un :command:`git lot`.

Esto es lo que debería aparecer:

.. code-block:: console

    commit b1f80a9d4f67a7fe4b0d3070848c0e7bdc8b2e05 (HEAD -> main)
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
