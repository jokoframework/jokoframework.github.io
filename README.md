ReadTheDocs
Clonar el proyecto que contiene la página de ReadTheDocs
    Proyecto con archivos de Sphinx para generar página en ReadTheDocs:
https://github.com/jokoframework/jokoframework.github.io
  
El directorio /docs del proyecto es el que contiene todo lo relacionado a Sphinx y las páginas generadas, es lo que ReadTheDocs utilizará, si se quiere hacer una nueva página o modificar una vieja se debe utilizar el lenguaje reStructuredText, la generación de las páginas usando estos archivos es lo que Sphinx provee
    reStructuredText Cheatsheet:
https://github.com/ralsina/rst-cheatsheet/blob/master/rst-cheatsheet.rst

Los archivos escritos en reStructuredText del proyecto deben terminar en “.rst”, si desea modificar la página de entrada esta se especifica en el archivo /docs/index.rst y el resto de las páginas fueron metidas en el directorio /docs/joko-docs/*** tratando de mantener una estructura donde un archivo es una sección (No necesariamente una página). Si quiere incluir imágenes poner las imagenes a referenciar en un subdirectorio de /docs/_static/*** (Es recomendado seguir una misma notación en el directorio _static/*** que en el de joko-docs/***).

Instalar Sphinx solo si desea probar localmente como se va viendo la página, ReadTheDocs genera con Sphinx de su lado usando solo los archivos fuente escritos en reStructuredText
        Instalación de Sphinx:
        http://www.sphinx-doc.org/en/master/usage/installation.html

Si quiere jugar con las configuraciones de Sphinx (No es necesario) se encuentran en /docs/conf.py (Archivo en Python)
    Opciones de configuración:
http://www.sphinx-doc.org/en/master/config.html

Para probar lo que va escribiendo puede construir el proyecto con sphinx localmente, en particular puede utilizar un regenerador “sphinx-autobuild” que viene incluido (Vera su pagina y se actualizará cuando encuentra cambios en el directorio/s especificado/s), el autobuild sirve su pagina en el localhost puerto 8000 por defecto (En su browser ponga localhost:8000 como URL y podrá acceder a esta página servida).
Sphinx Autobuild:        
https://pypi.python.org/pypi/sphinx-autobuild


        
Una vez feliz con su página simplemente debe actualizar el repositorio con los nuevos cambios y mediante Webhooks se actualizará la página de ReadTheDocs en unos minutos (Verificar que lo hecho se vea como se quiere en ReadTheDocs, debido a que se reconstruye la página en su lado pueden haber opciones que no permanecen o que arman problemas, aunque esto solo ocurre cuando se entra a tocar cosas muy particulares)
    Página de Joko Framework en ReadTheDocs:
    http://joko-framework.readthedocs.io/en/latest/#