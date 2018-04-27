-----------
Excel Utils
-----------
Contiene utilidades para trabajar con archivos Excel.

**Ejemplo del método generateExcel**

El método utiliza los datos pasados para crear un archivo Excel en el directorio especificado con los datos especificados.

Inputs:

* Table<Integer, Integer, Object> que contenga los datos a escribir en el archivo final.
* Una lista de Strings que contiene las cabeceras de la tabla de datos.
* Un String que contiene el nombre del archivo incluyendo la ruta a este (/home/user/mi_excel.xls), el archivo puede o no existir a la hora de correr el método.

Generamos los tres inputs para luego llamar al método que escribirá el archivo resultante, debe modificar el campo "DIRECCION_DEL_ARCHIVO" con la dirección de su archivo (Ej: /home/usuario/Desktop/mi_excel.xls):

.. code-block:: java
        
    // Definimos el directorio donde se creara el archivo incluyendo su nombre (Terminando en .xls)
    final String fileName = "DIRECCION_DEL_ARCHIVO";

    // Para el ejemplo creamos la lista de cabeceras de la tabla con los nombres de las 
    // columnas deseadas
    List<String> header = Arrays.asList("Name", "LastName", "Email", "Cellphone");

    // Creamos y agregamos datos a la tabla
    Table<Integer, Integer, Object> data = HashBasedTable.create();
    for (int i = 0; i < 10; i++) {
        // data.put(n_fila, n_columna, dato)
        data.put(i, 0, "Joko " + i);
        data.put(i, 1, "Utils " + i);
        data.put(i, 2, "jokoutils" + i + "@gmail.com");
        data.put(i, 3, 123456*i);
    }

    // Hacemos una instancia de la clase ExcelUtils y usamos el método generateExcel pasando 
    // la tabla de datos, la lista de cabeceras y la dirección y nombre del archivo final
    ExcelUtils excelGenerator = new ExcelUtils();
    excelGenerator.generateExcel(data, header, fileName);

Vista previa del archivo generado por este ejemplo:

.. image:: /_static/images/joko-utils/ExcelUtils/generateExcel_img1.png
    :align: center
