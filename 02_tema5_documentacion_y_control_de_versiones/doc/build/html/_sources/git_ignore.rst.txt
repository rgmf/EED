Ignorar ficheros
****************
Puedes indicarle a Git que ignore ciertos ficheros a partir de patrones. Estos ficheros, Git los ignorará en el sentido de que nunca aparecerán cuando hagamos un :command:`git status` como ficheros a seguir o añadir a nuestro repositorio.

¿Por qué querrías hacer esto? A veces, tendrás algún tipo de archivo que no quieres que Git añada automáticamente o más aun, que ni siquiera quieras que aparezca como no rastreado. Este suele ser el caso de archivos generados automáticamente como trazas o archivos creados por tu sistema de compilación.

En estos casos, tienes que crear un fichero, dentro de la raíz de tu proyecto, llamado :file:`.gitignore` (atención al punto del principio del nombre). En este fichero escribirás patrones que indiquen a Git qué tipo de ficheros no tiene que añadir.

Patrones en el fichero .gitignore
=================================
A través de un serie de ejemplos te voy a explicar la sintaxis de este fichero, y cómo indicar a través de patrones qué ficheros ignorar:

- **Main.class**: ignora el fichero :file:`Main.class` que se encuentra en la raíz del proyecto.
- **bin/Main.class**: ignora el fichero :file:`Main.class` que hay dentro de la carpeta :file:`bin`.
- **\*.class**: ignora todos los ficheros :file:`.class` que hay en la raíz del proyecto.
- **bin/\*.class**: ignora todos los ficheros :file:`.class` que hayan en la carpeta :file:`bin`.
- **bin/**: ignora todos los ficheros de la carpeta :file:`bin`.
- **\*\*/\*.class**: ignora todos los ficheros :file:`.class` que estén dentro de la carpeta del proyecto, estén donde estén.
- **doc/\*\*/\*.txt**: ignora todos los ficheros :file:`.txt` que estén dentro de la carpeta :file:`doc` y todas sus subcarpetas.

Puedes añadir comentarios en el fichero :file:`.gitignore`. Todas las líneas que comiencen por una :file:`#` son un comentario.

GitHub mantiene una extensa lista de archivos :file:`.gitignore` adecuados a docenas de proyectos y lenguajes en `https://github.com/github/gitignore <https://github.com/github/gitignore>`__, en caso de que quieras tener un punto de partida para tu proyecto.

Ejemplo de fichero
==================
Aquí te muestro un ejemplo de fichero :file:`.gitignore`:

.. code-block:: console

    # Ejecutables
    *.apk
    *.ap_

    # Ficheros para la máquina virtual ART/Dalvik
    *.dex

    # Los ficheros class de Java
    *.class

    # Ficheros generados
    bin/
    gen/
    out/
    release/

    # Ficheros de Gradle 
    .gradle/
    build/
