CsvUtils (CSV - Comma Seperated Values)
---------------------------------------
Ejemplo del método **convertToCsv**

Los Inputs:

* Una lista de tipo indefinido que tendrá objetos de una misma clase y cuya clase tenga la propiedad de ser serializable.
* Una lista de Strings donde cada elemento es el nombre de una columna del texto CSV así como el nombre del atributo del objeto cuyo Getter se llamara (Como vera en el ejemplo no es Case-Sensitive).
* La clase de la lista de objetos.

Para el ejemplo usaremos la siguiente clase para nuestra lista de objetos, haciendo que sea serializable así como definiendo los Getters para usar los atributos:

.. image:: /_static/images/CsvUtils/convertToCsvEj1.png
   :scale: 100 %

Generamos los Objetos en este caso para luego crear las listas, llamar al método y escribir en un archivo el resultado:

.. image:: /_static/images/CsvUtils/convertToCsvEj2.png
   :scale: 100 %

El archivo generado por el ejemplo:

.. image:: /_static/images/CsvUtils/convertToCsvEj3.png
   :scale: 100 %

Algunos datos extra:

* El orden de la lista de cabeceras define el orden de columnas del archivo final
* Si no existe Getter para cierta cabecera definida se rellenara la columna con valores vacíos