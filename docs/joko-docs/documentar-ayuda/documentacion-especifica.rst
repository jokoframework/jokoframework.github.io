Documentación Específica (Javadocs)
###################################

Introducción
************
Lo ideal es que la documentación específica de cada proyecto esta disponible mediante Javadocs, donde cada proyecto debe de hacer lo mejor para estar bien documentado con el formato para generar Javadocs y así se pueda generar y hostear los Javadocs en su propia página de Github Pages.

Instrucciones para agregar documentación
****************************************
A continuación un paso a paso de como generar Javadocs y hostear en Github Pages:

1- Comentar el código de su proyecto en el formato usado para generar Javadocs y de forma completa:
    
    * Incluir Explicación
    * @param para explicar cada parámetro
    * @return para explicar lo que retorna
    * @throws para explicar porque tira dicho error
    * @see o @link para incluir referencias a librerias de terceros
    * etc.

    `Javadocs Cheatsheet <https://binfalse.de/2015/10/05/javadoc-cheats-sheet/>`_

2- Una vez se quiera levantar cambios al repositorio "master" se deben generar/regenerar los Javadocs del proyecto (No se olvide de seleccionar la codificación correcta a la hora de generar! Si el proyecto está en castellano los acentos o la “ñ” no se desplegaran bien con la codificación por defecto) y subir lo generado al directorio /docs (Reemplazando los archivos antiguos de existir).
    
    `Javadocs Generator <https://docs.oracle.com/javase/7/docs/technotes/tools/windows/javadoc.html>`_

3- Si su proyecto tiene habilitada su propia página de GitHub Pages se actualizará todo automáticamente al subir cambios a /docs del "master", pero si no tiene la página habilitada haga lo siguiente:
Una vez tenga creado el directorio /docs (Sino no le dejara elegir la opción!) en la raíz del proyecto con lo generado por Javadocs entrar a la página de GitHub del proyecto y de la página principal ir a “Settings” y en la sección de “GitHub Pages” de esta página debe seleccionar la opción “master branch /docs folder” en el campo "Source", tras un momento el link de su página será mostrado en esta sección una vez rellene el campo.

    Formato por defecto de las Github Pages: https://USUARIO.github.io/PROYECTO
