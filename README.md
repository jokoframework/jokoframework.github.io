# Joko Framework
## Introducción
Este proyecto contiene los archivos para generar la página web de Joko Framework en ReadTheDocs.com (Hosting gratuito para proyectos Open Source), los archivos contenidos son la configuración para la herramienta Sphinx (Genera la página) y las páginas escritas en el lenguaje Markup "reStructuredText" tal que mediante Webhooks ReadTheDocs al detectar los cambios del proyecto se encarga de regenerar de su lado la página usando Sphinx y los archivos recientes.

## Instrucciones para agregar documentación
Antes que nada la documentación en ReadTheDocs <b>no debe contener especificaciones de código</b> de algún proyecto, eso se deja a cargo de los Javadocs, lo que <b>sí</b> va en esta página es todo lo demas como la Introducción del proyecto, Guía de Uso/Instalación, Ejemplos/Tutoriales, etc.
    
A continuación un paso a paso de <b>como</b> agregar nuevas páginas al proyecto:

1- Clonar el proyecto que contiene la página de ReadTheDocs
        
        https://github.com/jokoframework/jokoframework.github.io
  
2- El directorio /docs del proyecto es el que contiene todo lo relacionado a Sphinx y las páginas generadas, es lo que ReadTheDocs utilizará, si se quiere hacer una nueva página o modificar una vieja se debe utilizar el lenguaje reStructuredText, la generación de las páginas usando estos archivos es lo que Sphinx provee
    
    reStructuredText Cheatsheet:
        https://github.com/ralsina/rst-cheatsheet/blob/master/rst-cheatsheet.rst

3- Los archivos escritos en reStructuredText del proyecto deben terminar en la extensión “.rst”, si se desea modificar la página de entrada esta se especifica en el archivo /docs/index.rst mientras que el resto de las páginas están en el directorio /docs/joko-docs/*** tratando de mantener una estructura donde un archivo es una división (No necesariamente una página). Si quiere incluir imágenes debe poner las imagenes a referenciar en un subdirectorio de /docs/_static/*** (Es recomendado seguir una misma notación en el directorio _static/*** que en el de joko-docs/***).

4- Instalar Sphinx <b>solo si desea probar localmente como se va viendo la página</b>, ReadTheDocs genera con Sphinx de su lado usando solo los archivos fuente escritos en reStructuredText
    
    Instalación de Sphinx:
        http://www.sphinx-doc.org/en/master/usage/installation.html

4.1- Si quiere jugar con las configuraciones de Sphinx (No es necesario) se encuentran en /docs/conf.py (Archivo en Python, recuerde de indentar correctamente!)
    
    Opciones de configuración:
        http://www.sphinx-doc.org/en/master/config.html

4.2- Para probar lo que va escribiendo puede construir el proyecto con sphinx localmente, en particular puede utilizar un regenerador “sphinx-autobuild” que viene incluido con Sphinx (Vera su pagina y se actualizará cuando encuentra cambios en el directorio/s especificado/s), el autobuild sirve su pagina en el localhost puerto 8000 por defecto (En su navegador ponga "localhost:8000" como URL y podrá acceder a esta página servida).
    
    Sphinx Autobuild:        
        https://pypi.python.org/pypi/sphinx-autobuild


        
5- Una vez feliz con su página simplemente debe actualizar el repositorio (Si genero localmente con Sphinx <b>no suba la carpeta "_build"</b> donde se creo la página web, este proyecto solo contiene los archivos <b>para</b> generar no lo generado) con los nuevos cambios y mediante Webhooks se actualizará la página de ReadTheDocs en unos minutos (Verificar que lo hecho se vea como se quiere en ReadTheDocs, debido a que se reconstruye la página en su lado pueden haber opciones que no permanecen o que arman problemas, aunque esto solo ocurre cuando se entra a tocar cosas muy particulares)
    
    Página de Joko Framework en ReadTheDocs:
        http://joko-framework.readthedocs.io/en/latest/#
